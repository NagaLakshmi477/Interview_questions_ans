# Kubernetes Interview Notes

## Pod is stuck in CrashLoopBackOff

So our application can run on Pods.

```text
Pod starts
   ↓
Container starts
   ↓
Application crashes
   ↓
Container stops
   ↓
Kubernetes restarts it
   ↓
Application crashes again
   ↓
Kubernetes restarts it again
```

This process of restarting and failing happens again and again. After seeing some crashes, Kubernetes will not restart immediately. Sometimes it will wait a little longer between attempts.

This waiting is called `CrashLoopBackOff`.

In our project we used a Java application.

```text
Pod
 └── Container
      └── Java application
```

Here application tries to connect to the database through an API call.

```text
Application → Database
```

So here password may be the issue. There may be a space after the password.

The application starts → tries to connect → connection fails → application exits.

```text
Start
 ↓
DB connection fails
 ↓
Application exits
 ↓
Restart
 ↓
DB connection fails
 ↓
Application exits
```

## How do we troubleshoot it?

### 1. Check the Pod

```bash
kubectl get pods
```

```text
NAME                    READY   STATUS             RESTARTS
myapp-7d8f9c6d5-xk2p4   0/1     CrashLoopBackOff   8
```

### 2. Check the logs

```bash
kubectl logs myapp-7d8f9c6d5-xk2p4
```

```text
ERROR: Unable to connect to database
Connection refused
```

### 3. If the container is restarted, then check the previous logs

```bash
kubectl logs myapp-7d8f9c6d5-xk2p4 --previous
```

`--previous` means it will show the logs from the previous container instance that crashed.

---

# Zero-downtime deployment

Suppose we have an application running in Kubernetes with 3 Pods:

```text
Application
   ↓
Pod 1  → Running
Pod 2  → Running
Pod 3  → Running
```

Users are continuously accessing the application.

Now we have a new version of the application and we want to deploy it.

The problem is:

If we stop all the old Pods first and then start the new Pods, users will get downtime.

```text
Stop old Pods
    ↓
No Pods available
    ↓
Users get errors ❌
    ↓
Start new Pods
```

In our project we used a Blue-Green deployment strategy.

```text
BLUE  → Current/old version
GREEN → New version
```

Currently users are accessing BLUE:

```text
Users
  ↓
Load Balancer
  ↓
BLUE
 ├── Pod 1 (v1)
 ├── Pod 2 (v1)
 └── Pod 3 (v1)
```

Now you want to deploy version 2.

```text
BLUE                    GREEN
v1                      v2
├── Pod 1               ├── Pod 1
├── Pod 2               ├── Pod 2
└── Pod 3               └── Pod 3
```

```text
GREEN
  ↓
Health checks
  ↓
Application testing
  ↓
Everything looks good ✅
```

Then you switch traffic:

Before:

```text
Users → BLUE
```

After:

```text
Users → GREEN
```

So instead of rebuilding or redeploying the old version, you can simply switch traffic back:

```text
GREEN has issue
      ↓
Switch traffic back
      ↓
Users → BLUE (v1)
```

## How would you implement zero-downtime deployments in Kubernetes?

I would implement zero-downtime deployment using Blue-Green deployment.

Suppose the current application version is running in the BLUE environment:

```text
Users
  ↓
Load Balancer
  ↓
BLUE
 ├── Pod 1 → v1
 ├── Pod 2 → v1
 └── Pod 3 → v1
```

Users are continuously using the application.

Now we have a new version, v2.

Instead of directly replacing the BLUE Pods, I would create a separate GREEN environment with v2.

Because BLUE was never stopped while we were deploying GREEN, users don't experience downtime.

I would also keep BLUE available for some time. If there is an issue with v2 after the traffic switch, I can quickly switch traffic back.

---

# Service is not accessible externally

Suppose my application is running inside the cluster:

```text
Pod 1 → Running
Pod 2 → Running
Pod 3 → Running
```

Inside the cluster, the application is working.

For example, another Pod can access it.

But when a user tries to access it from outside:

```text
User → Internet → Kubernetes Service → ❌
```

### Check the Pods

```bash
kubectl get pods
```

I would make sure the Pods are actually Running and Ready.

If the Pods themselves aren't healthy, I would fix that first.

### Check the Services

```bash
kubectl get svc
```

```text
NAME     TYPE           CLUSTER-IP     EXTERNAL-IP
myapp    LoadBalancer   10.0.10.20     xxxxx.elb.amazonaws.com
```

Here I check the Service type.

If I want external access, depending on the architecture, I might use:

### Check the Service endpoints

```bash
kubectl get endpoints myapp
```

I want to see whether the Service is actually pointing to the application Pods.

Usually I would then check the Service selector and the Pod labels.

Service selector:

```text
app: myapp
```

Pod label:

```text
app: myapp
```

They need to match.

### Check the ports

```text
Service is not accessible externally
              ↓
        Check the Pods
              ↓
        Check the Service
              ↓
      Check the Service type
              ↓
      Check the Endpoints
              ↓
 Check Service selector + Pod labels
              ↓
        Check the ports
```

---

# Failed deployment rollout

Suppose we have an application running with 3 Pods:

```text
v1
├── Pod 1 → Running
├── Pod 2 → Running
└── Pod 3 → Running
```

Now we deploy a new version, v2.

Kubernetes starts replacing the old Pods with new Pods.

```text
Old version → v1
New version → v2
```

But suppose the new Pods are not becoming healthy:

```text
v2
├── Pod 1 → Running
├── Pod 2 → CrashLoopBackOff
└── Pod 3 → Pending
```

Kubernetes cannot complete the rollout.

That's what we mean by a failed deployment rollout.

## How would I troubleshoot it?

### I will check the Deployments

```bash
kubectl get deployments
```

### Then I will check the Pods

```bash
kubectl get pods
```

### Check the rollout status

```bash
kubectl rollout status deployment/<deployment-name>
```

If the new version is giving errors, I will roll back to the previous version.

```bash
kubectl rollout undo deployment/<deployment-name>
kubectl rollout status deployment/<deployment-name>
```

### Deployment rollout troubleshooting flow

```text
Deployment rollout failed
        ↓
kubectl rollout status
        ↓
Check Pods
        ↓
Check logs
        ↓
Check previous logs if required
        ↓
kubectl describe pod <pod-name>
        ↓
Check Events
        ↓
Find the actual reason
        ↓
Fix the problem
        ↓
Check rollout again
```

---

# Resource optimization

Suppose we have an application running in Kubernetes:

```text
Pod 1
Pod 2
Pod 3
```

---

# How would you implement auto-scaling when production traffic fluctuates heavily?

Imagine our application normally has 3 Pods.

## Normal traffic

```text
Pod 1
Pod 2
Pod 3
```

Now suddenly production traffic increases:

```text
Normal traffic → 100 users
             ↓
Traffic spike → 1000 users
```

If we continue running only 3 Pods, the Pods may start consuming high CPU/memory and the application can become slow.

So we use Kubernetes HPA (Horizontal Pod Autoscaler).

HPA continuously checks the resource usage of the Pods.

```text
3 Pods
   ↓
CPU usage increases
   ↓
HPA detects high CPU
   ↓
Increase replicas
   ↓
5 Pods
```

If traffic comes down:

```text
Traffic decreases
   ↓
CPU usage decreases
   ↓
HPA detects lower usage
   ↓
Reduce replicas
   ↓
3 Pods
```

---

# What would be your strategy for backing up and restoring a Kubernetes cluster?

In my project, I was mainly involved with the application deployment and Kubernetes workloads. PV, PVC, and StorageClass were handled by the senior developers/platform team, so I didn't directly manage the persistent storage configuration.

For Kubernetes backup, my understanding is that we need to back up the Kubernetes resources such as Deployments, Services, ConfigMaps, and Secrets. For persistent application data, the storage/database backup would be handled separately by the responsible team.

If the cluster had to be restored, we would recreate the cluster and restore the required Kubernetes resources, then make sure the application and its data are available again.

---

# How would you handle database credential rotation in Kubernetes?

In Kubernetes, database credentials can be stored in Secrets instead of hardcoding them. During rotation, the database credential and Kubernetes Secret need to be updated, and the application needs to pick up the new credential. In my project, I was not directly responsible for database credential rotation; this was handled by the senior/platform team.

---

# What happens to the Pods running on a node that suddenly goes down?

```text
Node 1
 ├── Pod 1
 └── Pod 2

Node 2
 ├── Pod 3
 └── Pod 4

Node 3
 ├── Pod 5
 └── Pod 6
```

Now suddenly Node 1 goes down.

```text
Node 1 ❌
 ├── Pod 1 ❌
 └── Pod 2 ❌
```
