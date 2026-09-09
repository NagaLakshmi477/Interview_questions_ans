# DevOps Master Interview Question Bank

> **Focus:** AWS DevOps | Terraform | Kubernetes/EKS | CI/CD | Jenkins | Git | Docker | Linux | Ansible | Monitoring | Security | Production Support

---

# 1. DevOps Project & Experience

1. Tell me about yourself.
2. Tell me about your current project.
3. Walk me through your project flow.
4. Explain your project architecture from a DevOps perspective.
5. Explain the complete CI/CD flow that you built end-to-end.
6. What exactly was your role and responsibility in your project?
7. What was your role in the CI/CD pipeline?
8. What are your day-to-day responsibilities as a DevOps Engineer?
9. What third-party integrations have you worked on?
10. Explain an integration you implemented in your project.
11. What automation tasks have you done using Shell scripting?
12. Do you have Python experience? How much exposure do you have?
13. What type of applications have you deployed?
14. Have you worked on production support?
15. Have you handled on-call support?
16. Explain one production issue you handled.
17. How did you troubleshoot the production issue?
18. How did you minimize downtime?
19. What preventive measures did you implement after the incident?
20. Have you worked on any migration projects?
21. Have you worked on both on-premises and cloud environments?
22. Do you have hybrid cloud experience?

---

# 2. AWS – Core & Architecture

1. What AWS services have you worked on?
2. Design a highly available three-tier architecture in AWS.
3. Which AWS services would you use for a three-tier application?
4. Why do we use a VPC?
5. Why do we use multiple Availability Zones?
6. What is the purpose of an Internet Gateway?
7. What is the purpose of a NAT Gateway?
8. How does a NAT Gateway work internally?
9. What is the difference between an Internet Gateway and a NAT Gateway?
10. What is the difference between public and private subnets?
11. How do you identify whether a subnet is public or private?
12. How do public and private subnets route traffic?
13. When would you use public and private subnets?
14. How do two subnets communicate within the same VPC?
15. How would you design a highly available architecture across multiple Availability Zones?
16. What are the differences between ALB, NLB, and CLB?
17. What is AWS Elastic Load Balancer?
18. What is the purpose of an Application Load Balancer?
19. How do you create an Application Load Balancer?
20. How do you get the DNS URL of an ALB?
21. Which load balancer supports path-based routing?
22. Does an ALB have a static IP address?
23. If your application requires a static public IP address, what AWS service or solution would you use?
24. How would you provide static IPs for an HTTP/HTTPS application?
25. Can an NLB handle HTTPS/TLS traffic?
26. What is the difference between ALB and NLB?
27. At which OSI layers do ALB and NLB operate?
28. When would you use ALB instead of NLB?
29. What is the difference between On-Demand Instances and Spot Instances?
30. What happens when an EC2 instance in an Auto Scaling Group becomes unhealthy?
31. How does Auto Scaling work?
32. How would you troubleshoot connectivity issues between private and public subnets?
33. How would you troubleshoot an unreachable EC2 instance?
34. How do you provide cross-account access in AWS?
35. What is cross-account IAM access?
36. EC2 is in Account A and S3 is in Account B. How would you allow EC2 to access the S3 bucket?
37. How would you avoid storing AWS access keys on an EC2 instance?
38. What is Amazon S3?
39. How do you provide access to an S3 bucket?
40. What permissions and policies need to be configured for S3 access?
41. How would you provide temporary access to an S3 object?
42. How would you share an S3 object with an external customer who does not have an AWS account?
43. What is Amazon DynamoDB?
44. Why would you use DynamoDB instead of a relational database?
45. Why is DynamoDB used for Terraform remote state locking?
46. What is Amazon Route 53?
47. Explain the different Route 53 routing policies.
48. How does Route 53 perform failover during a disaster recovery scenario?
49. How do you redirect traffic to another AWS region during DR?
50. How do you optimize AWS infrastructure costs?
51. How would you investigate a sudden increase in AWS cloud costs?

---

# 3. AWS Networking

1. What is VPC Peering?
2. How would you enable communication between EC2 instances in private subnets across two different AWS accounts?
3. Why would you choose VPC Peering for this scenario?
4. What are the steps involved in configuring VPC Peering?
5. Have you worked on VPC Peering in a production environment?
6. Have you worked with AWS Client VPN?
7. Have you worked with AWS Transit Gateway?
8. After creating a Transit Gateway attachment, is that enough for traffic to flow?
9. What additional configurations are required after creating a Transit Gateway attachment?
10. What is AWS WAF?
11. Why do we use AWS WAF with an ALB?
12. What are the differences between Security Groups and Network ACLs?
13. How would you troubleshoot connectivity between AWS resources?

---

# 4. AWS IAM & Security

1. What is IAM?
2. What is the difference between IAM Users, Groups, and Roles?
3. Why do we use IAM Roles?
4. How do you provide cross-account access using IAM Roles?
5. How does EKS integrate with IAM?
6. What is the difference between RBAC and IRSA?
7. What is AWS Organizations?
8. What is an SCP?
9. What is the use of SCP in an AWS enterprise environment?
10. Is it possible to create both Allow and Deny rules in SCP?
11. How do Permission Boundaries work?
12. How do IAM Roles, Permission Boundaries, and SCP work together?
13. How would you manage user access across multiple AWS accounts?
14. What are Permission Sets in AWS IAM Identity Center?
15. How would you provide the same permissions to a DevOps engineer across multiple AWS accounts?
16. How do you ensure that an AWS cloud environment is secure?
17. What AWS tools or services do you use for security and compliance?
18. How do you securely manage secrets in AWS?

---

# 5. AWS Monitoring & Logging

1. What is AWS CloudWatch?
2. What is the use of CloudWatch?
3. Which CloudWatch metrics do you use for troubleshooting?
4. How would you configure CloudWatch alarms?
5. How would you configure custom metrics for an application?
6. What is AWS CloudTrail?
7. What is the difference between CloudWatch and CloudTrail?
8. How would you monitor an application running in AWS?
9. How would you troubleshoot high application latency using AWS monitoring tools?
10. Which ALB metrics do you monitor regularly?
11. What monitoring tools have you used?
12. Have you used CloudWatch for production monitoring?

---

# 6. Terraform – Fundamentals

1. What is Infrastructure as Code?
2. What are the benefits of Infrastructure as Code?
3. What is Terraform?
4. What is Terraform Apply?
5. Explain the Terraform lifecycle.
6. What happens during `terraform init`?
7. Does `terraform init` create an EC2 instance?
8. What are Terraform providers?
9. How do Terraform providers work after `terraform init`?
10. Can we use multiple providers in the same Terraform deployment?
11. What are Terraform meta-arguments?
12. What is the difference between `count` and `for_each`?
13. What is indexing in Terraform?
14. What are Terraform variables?
15. What are Terraform locals?
16. What is the difference between Terraform variables and locals?
17. What is a Terraform data source?
18. What are dependencies in Terraform?
19. Explain implicit and explicit dependencies in Terraform.
20. How does Terraform build and execute its dependency graph?
21. What is immutable infrastructure?
22. How does Terraform support immutable infrastructure?
23. What is the difference between Terraform and AWS CloudFormation?

---

# 7. Terraform – State & Backend

1. What is the Terraform State File?
2. Why is Terraform state required?
3. What is Terraform remote state?
4. Which remote backend have you used with Terraform?
5. How did you configure the Terraform remote backend?
6. How did you configure S3 for Terraform remote state?
7. Where are Terraform state and locking details stored when using S3 and DynamoDB?
8. Why are state files stored in S3?
9. Why is DynamoDB used for Terraform state locking?
10. How does Terraform state locking work with S3 and DynamoDB?
11. What happens if two engineers run `terraform apply` at the same time?
12. How do you prevent two people from running `terraform apply` simultaneously?
13. What happens if the Terraform state file is accidentally deleted?
14. How would you recover a deleted Terraform state file?
15. What happens if the Terraform state file becomes corrupted?
16. How would you recover from Terraform state corruption?
17. How would you manage existing infrastructure without unnecessarily recreating resources after state problems?
18. How would you identify whether existing infrastructure can be imported into Terraform state?
19. What is Terraform Import?
20. How do you manage existing AWS resources using Terraform?

---

# 8. Terraform – Drift & Troubleshooting

1. What is Terraform Drift?
2. What is configuration drift?
3. How does Terraform detect infrastructure drift?
4. How do you overcome Terraform drift?
5. If you manually add a tag to an EC2 instance from the AWS Console, what happens when you run `terraform apply`?
6. Your Terraform pipeline is failing because Terraform State is locked. What would you do?
7. Terraform Apply is stuck for a long time. How would you troubleshoot it?
8. What common Terraform issues have you faced?
9. Terraform partially created infrastructure before failing. How would you recover safely?
10. An Infrastructure-as-Code deployment partially succeeds and then fails. How would you safely recover without causing infrastructure drift?
11. If a Terraform state file is large and taking a long time to load, what could be the issue?
12. How would you optimize a large Terraform state file?

---

# 9. Terraform – Modules & Project Structure

1. What is a Terraform Module?
2. Why do we use Terraform modules?
3. How do you create an EC2 instance using a Terraform module?
4. How do you call a Terraform module from a root module?
5. How do you call one Terraform module from another module?
6. What is the `source` argument inside a Terraform module block?
7. What are the common inputs/variables for an EC2 module?
8. What is a Terraform Registry module?
9. What is the difference between a Terraform Registry module and a local module?
10. How do you use a specific or previous version of a Terraform module?
11. What Terraform modules have you worked on?
12. What is the recommended folder structure for a production-grade Terraform project?
13. How did you structure your Terraform folders?
14. How do you maintain Terraform files for Dev and Production environments?
15. How do you manage Terraform code across multiple environments?
16. If you have Dev, QA, and Production environments, how would you use the same Terraform code?
17. What are Terraform Workspaces?
18. When would you use Terraform Workspaces instead of separate folders?
19. How do you manage Terraform state for multiple environments?
20. How would you create EC2 instances in multiple AWS regions using Terraform?
21. What are Terraform provider aliases?
22. How would you create multiple EC2 instances with unique names and instance types?
23. How would you delete only one specific EC2 instance using Terraform?
24. If you have 50 EC2 instances created using Terraform, how would you reduce them to 10?
25. If you use `count` and delete the fifth instance, what problem can occur?
26. Why would you prefer `for_each` over `count` for stable resources?

---

# 10. Terraform – Hands-on

1. Write Terraform code to create 5 EC2 instances with unique names and instance types.
2. Delete only one specific EC2 instance using Terraform.
3. Write Terraform code to create an EKS cluster.
4. Implement conditional resource creation in Terraform.
5. How would you generate a random number in Terraform?
6. What is the Random provider?
7. Which Terraform block would you use to execute a shell command during `terraform apply`?
8. What is the difference between `local-exec` and `remote-exec` provisioners?
9. How would you increase an existing Linux volume from 500 GB to 750 GB using Terraform?

---

# 11. Kubernetes – Architecture & Fundamentals

1. Explain Kubernetes Architecture.
2. What are the Control Plane components in Kubernetes?
3. What are the Worker Node components in Kubernetes?
4. What is the role of `containerd`?
5. What is the role of `kube-proxy`?
6. What is a Kubernetes Pod?
7. What is a Kubernetes Service?
8. Why do we use Services in Kubernetes?
9. What are the different types of Kubernetes Services?
10. What is the difference between ClusterIP, NodePort, and LoadBalancer?
11. When would you use ClusterIP, NodePort, and LoadBalancer?
12. What is a Kubernetes Namespace?
13. What is a Custom Resource Definition (CRD)?
14. Why do we need CRDs?
15. How do you create and use a Custom Resource after defining a CRD?
16. What is CNI?
17. Which CNI plugin have you used?
18. How did you implement the CNI?
19. What is Service Discovery in Kubernetes?
20. What are Taints and Tolerations?
21. What is Node Affinity?
22. Explain Taints, Tolerations, and Node Affinity.
23. What is the difference between Deployment and StatefulSet?
24. What are the differences between Deployment, StatefulSet, and DaemonSet?
25. What are Requests and Limits in Kubernetes?

---

# 12. Kubernetes – EKS

1. Explain your Amazon EKS experience.
2. What kind of applications have you deployed in EKS?
3. How do you deploy applications to EKS?
4. What Kubernetes resources do you use while deploying applications?
5. What are the prerequisites for EKS cluster setup?
6. How do you connect to an EKS cluster?
7. Which commands do you use to connect to EKS?
8. How do developers connect to the EKS cluster?
9. How does Jenkins connect to the EKS cluster?
10. How do you connect to EKS worker nodes?
11. What do you do after connecting to an EKS worker node?
12. How do you upgrade an EKS cluster?
13. Explain the process of upgrading an EKS cluster.
14. Have you worked on the EKS control plane upgrade process?
15. What is the trade-off between AWS-managed node groups and self-managed node groups?
16. How does EKS integrate with IAM?
17. What type of applications do you deploy on EKS?
18. When would you choose EC2 over EKS?
19. What operations have you performed in Kubernetes apart from deployments?

---

# 13. Kubernetes – Deployment & Scaling

1. What is a Kubernetes Deployment?
2. What is the Kubernetes Deployment flow?
3. How do you manually scale a Kubernetes Deployment?
4. How can you increase the number of replicas using the CLI?
5. What is Horizontal Pod Autoscaler (HPA)?
6. How does HPA work?
7. On which metrics does HPA scale Pods?
8. What is Cluster Autoscaler?
9. How does Cluster Autoscaler work?
10. What is the difference between HPA and Cluster Autoscaler?
11. Explain Min, Desired, and Max node settings in an EKS node group.
12. How does Kubernetes ensure high availability and scalability?
13. How do you achieve zero downtime in Kubernetes?
14. How would you optimize CPU and memory requests and limits in production?
15. How do you determine the desired, minimum, and maximum pod count for a microservice?
16. How do you test an application to determine the minimum and maximum pod count?
17. How do you implement autoscaling when production traffic fluctuates heavily?

---

# 14. Kubernetes – Deployment Strategies

1. What deployment strategies are you currently using?
2. What is a Rolling Deployment?
3. What is a Blue-Green Deployment?
4. What is a Canary Deployment?
5. What is the difference between Rolling, Blue-Green, and Canary deployments?
6. Which deployment strategy do you use most frequently and why?
7. Have you implemented all three deployment strategies?
8. Have you implemented different deployment strategies for microservices?
9. Are you using Rolling Updates for critical services such as payment services?
10. How do Kubernetes Rolling Updates work?
11. How do Kubernetes Rollbacks work?
12. How would you implement Blue-Green deployment using Terraform and Jenkins?
13. How would you design a zero-downtime deployment?
14. How would you roll back a failed production deployment?
15. How do you prepare a rollback strategy before deployment?
16. A production deployment fails halfway through. How would you perform a rollback while minimizing downtime?

---

# 15. Kubernetes – Troubleshooting

1. If a Pod is down, how do you debug it?
2. What happens when a container crashes in Kubernetes?
3. What is CrashLoopBackOff?
4. What are the common reasons for CrashLoopBackOff?
5. How do you troubleshoot CrashLoopBackOff?
6. A Pod is in Pending state. How do you troubleshoot it?
7. What are the common reasons for a Pod to remain in Pending state?
8. Which command do you use first to troubleshoot a Pending Pod?
9. What does `kubectl describe pod` show?
10. If 6 Pods are running and 4 Pods are not running, how would you troubleshoot?
11. If only 20 out of 40 Pods were created after deployment, how would you investigate?
12. If a node becomes NotReady, what do you check?
13. You have three nodes and one node is not receiving traffic. How would you identify, troubleshoot, and fix the issue?
14. An application is accessible inside the cluster but not from outside. How would you troubleshoot it?
15. Your application is deployed and exposed, but traffic is not reaching backend Pods. How would you troubleshoot?
16. A service becomes inaccessible after an Ingress update. What components would you verify?
17. How would you troubleshoot an application returning 502 or 503 errors?
18. How would you troubleshoot intermittent 503 errors in Kubernetes?
19. How would you verify whether the issue is with the Pod, Service, Ingress, or Load Balancer?
20. What logs and metrics do you check during Kubernetes troubleshooting?
21. Why should Pod-related issues be investigated in Kubernetes rather than Jenkins?

---

# 16. Kubernetes – Networking & Request Flow

1. Explain the complete request flow from a client to a Kubernetes Pod.
2. How does a request travel from a browser to a Kubernetes Pod?
3. Explain the request flow for an application in Kubernetes.
4. What is the role of DNS in Kubernetes application access?
5. What is the role of Ingress?
6. What is the role of a Kubernetes Service?
7. How does Ingress route traffic to applications?
8. How does traffic flow from an external user/laptop to a Kubernetes application?
9. Can you bypass Ingress? Explain `kubectl port-forward`.
10. How would you restrict Pod-to-Pod communication in Kubernetes?
11. How would you restrict an EKS Pod so it can communicate only with a database and nothing else?
12. Write a NetworkPolicy for restricting Pod communication.
13. How would you troubleshoot an application that is accessible inside the cluster but not externally?
14. How would you troubleshoot an HTTP 503 Service Unavailable issue in production?
15. What is Istio?
16. Why do we use a Service Mesh?

---

# 17. Kubernetes – Storage & Secrets

1. Explain PV and PVC in Kubernetes.
2. How would you handle persistent storage for a stateful application running in Kubernetes?
3. What is a Kubernetes Secret?
4. Is Kubernetes Secret encrypted by default?
5. How do you manage secrets in Kubernetes?
6. How would you securely manage secrets in production?
7. How would you handle a database password in Kubernetes?
8. How would you integrate AWS Secrets Manager with Kubernetes?
9. How would you integrate AWS Secrets Manager with GitHub Actions?
10. How would AKS access Azure Key Vault without storing secrets in the cluster?
11. How would you rotate database credentials without causing application downtime?

---

# 18. Kubernetes – Probes

1. What is a Readiness Probe?
2. What is a Liveness Probe?
3. What is a Startup Probe?
4. Explain the difference between Readiness, Liveness, and Startup Probes.
5. How do Readiness and Liveness Probes work?
6. Write a Kubernetes Deployment YAML with requests, limits, readiness probe, and liveness probe.
7. Why would a Pod be Running but the application still be unavailable?

---

# 19. Kubernetes – YAML & Commands

1. Write a Kubernetes Deployment YAML file.
2. Write a Deployment YAML with requests and limits.
3. Write a Deployment YAML with readiness and liveness probes.
4. Write a Kubernetes Deployment YAML including error handling.
5. How do you check whether a Pod is running?
6. How do you open/access a Kubernetes Pod?
7. Which `kubectl` commands do you use regularly?
8. What troubleshooting commands do you use first?
9. How do you automate application validation after deployment?
10. How would you fail a deployment automatically if the health check fails?

---

# 20. Docker – Fundamentals

1. Explain Docker.
2. Why do we need containers?
3. What is the use of Docker?
4. What is the difference between a Container and a VM?
5. Explain Docker Architecture.
6. What are the components of Docker Architecture?
7. Explain the process of creating a Docker image from a microservice.
8. What are Docker Image Layers?
9. Why does every Docker instruction create a new layer?
10. Where are changes stored while a Docker container is running?
11. What is Docker Compose?
12. What is Docker Swarm?
13. What is Podman?
14. What are Docker networking options?
15. Explain Docker networking.
16. What are Docker volumes?
17. How do you inspect a running Docker container?
18. What does `docker inspect` do?

---

# 21. Docker – Dockerfile & Optimization

1. What are the components of a Dockerfile?
2. Write a Dockerfile for an application.
3. Write a Dockerfile for a Node.js application.
4. What is the difference between CMD and ENTRYPOINT?
5. Which one can be overridden: CMD or ENTRYPOINT?
6. What is the difference between Docker COPY and ADD?
7. When would you use COPY and ADD?
8. Explain Docker Multi-Stage Builds.
9. How do Multi-Stage Builds optimize production images?
10. What Docker best practices do you follow while creating Docker images?
11. A Docker image is very large. How would you optimize it?
12. A Docker image works locally but fails in production. How would you identify the root cause?
13. How do you optimize a Docker image for Kubernetes?
14. How do you push a Docker image to Amazon ECR?
15. Which container registry do you use to store Docker images?

---

# 22. Git

1. Explain your Git branching strategy.
2. What is the difference between Git Merge and Git Rebase?
3. Which one do you use in your development environment, Merge or Rebase? Why?
4. What is Git Rebase?
5. What is Git Squash?
6. What are Git Stash operations?
7. How do you resolve Git merge conflicts?
8. How do you revert changes in a remote repository?
9. How do you recover a deleted Git branch?
10. What is `git reflog`?
11. How do you recover a deleted commit using `git reflog`?
12. What is `git reset --hard`?
13. What is Git Cherry-pick?
14. When do you use Cherry-pick?
15. What branching strategy do you use in your organization?
16. How do you promote changes between environments?

---

# 23. Jenkins – Fundamentals & Architecture

1. Explain Jenkins.
2. Explain Jenkins Architecture.
3. What type of Jenkins pipeline have you worked on?
4. What is the difference between Declarative and Scripted pipelines?
5. What is Groovy syntax?
6. Have you created Jenkins pipelines from scratch?
7. Explain the Jenkins pipeline you worked on.
8. What is Jenkins Master-Agent architecture?
9. How does Jenkins execute stages in parallel?
10. What are Jenkins Shared Libraries?
11. Why are Jenkins Shared Libraries important in enterprise CI/CD?
12. How does Jenkins build triggering work?
13. How do you give developers access to specific Jenkins builds?
14. How do you provide access to the Jenkins server?
15. How do you configure SonarQube with Jenkins?
16. How do you configure the SonarQube Quality Gate?
17. What happens if the SonarQube Quality Gate fails?
18. How do you add security scanning to a Jenkins pipeline?
19. How do you integrate GitHub with Jenkins?
20. What is the integration layer between GitHub and Jenkins?

---

# 24. Jenkins – Pipeline & Troubleshooting

1. Explain your complete Jenkins CI/CD pipeline.
2. What happens after developers push code?
3. What happens after a code commit in your pipeline?
4. How would you design a reusable CI/CD workflow for Python, Node.js, and Java applications?
5. How would you set up reusable workflows for multiple microservices?
6. How would pipelines trigger only for changed microservices?
7. What type of tests do you perform in pipelines?
8. What metrics and SLAs do you define for pipeline health?
9. How do you troubleshoot a failed Jenkins pipeline?
10. If Jenkins is working locally but is not accessible through the URL, how would you troubleshoot it?
11. If a Jenkins deployment fails, how do you identify the root cause?
12. Which Jenkins logs do you check first?
13. How do you troubleshoot a Jenkins pipeline that suddenly starts failing without code changes?
14. A Jenkins pipeline is failing with a NullPointerException while accessing a JSON property. How would you troubleshoot it?
15. How would you reduce a CI/CD pipeline from 30 minutes to under 5 minutes?
16. How would you prevent two production deployments from running simultaneously?

---

# 25. CI/CD

1. What is the CI/CD process in your project?
2. What is the difference between Continuous Integration, Continuous Delivery, and Continuous Deployment?
3. Explain CI/CD with a real-world example.
4. Explain the complete CI/CD pipeline architecture.
5. How would you implement DevOps practices in a project that currently has manual deployments?
6. How would you design a multi-stage CI/CD pipeline with separate environments?
7. How do you manage Dev, SIT, UAT, and Production deployments?
8. Do you use a single CI/CD pipeline for multiple environments or separate pipelines?
9. How do you manage environment-specific configurations?
10. How do you prevent configuration drift between environments?
11. How do you implement approval workflows in CI/CD?
12. How many levels of approval are there before Production?
13. Who approves infrastructure changes?
14. What approval gates exist before Production deployment?
15. What happens if someone accidentally approves the wrong pipeline?
16. How would you handle an incorrect Terraform deployment caused by a wrong approval?
17. What rollback strategy would you follow?
18. What preventive controls would you implement to avoid deployment mistakes?
19. How would you design a zero-downtime CI/CD pipeline?
20. How would you design a GitOps workflow for multiple teams with independent release cycles?

---

# 26. SonarQube & Code Quality

1. What is SonarQube and what is its use?
2. Explain the end-to-end SonarQube flow in a CI/CD pipeline.
3. What is a code smell?
4. What is code coverage?
5. Give an example of a code smell detected by SonarQube.
6. Give an example of a security vulnerability detected by SonarQube.
7. How is SonarQube integrated into Jenkins?
8. What metrics does SonarQube check?
9. How do you troubleshoot a Jenkins pipeline failure caused by a SonarQube Quality Gate?
10. Did you only trigger SonarQube scans, or did you review and triage violations?
11. Give an example where you helped resolve a SonarQube finding.
12. What types of findings does SonarQube report?

---

# 27. Security Scanning – Checkmarx & Checkov

1. What is Checkmarx?
2. How did you integrate Checkmarx into Jenkins?
3. Did you review and triage Checkmarx violations?
4. Give an example where you helped resolve a Checkmarx finding.
5. What types of vulnerabilities does Checkmarx detect?
6. What is Checkov?
7. Why would you use Checkov for Terraform, Kubernetes, and Docker?
8. What common Checkov errors have you encountered?
9. After receiving a Checkov scan report, what steps do you follow before deployment?

---

# 28. Linux

1. How comfortable are you with Linux?
2. What Linux activities do you perform regularly?
3. What are the top Linux commands every DevOps Engineer should know?
4. How do you troubleshoot a Linux server?
5. How do you check Linux logs?
6. How do you access a Linux server?
7. How do you troubleshoot port-related issues in Linux?
8. How do you monitor CPU utilization in Linux?
9. How do you monitor context switches in Linux?
10. Write a Shell script to monitor CPU utilization.
11. Write a Shell script to send an email when CPU usage exceeds 90%.
12. Write a Shell script to monitor a service and automatically restart it if it goes down.
13. Write a Shell script to check whether a Kubernetes Pod is running.
14. Write a Shell script for weekly log cleanup.
15. How would you schedule a cleanup script every week?
16. What is the meaning of `-mtime +7`?
17. What is the output of:

```bash
echo hi || echo hello
```

18. Explain the `sort` command in Linux.
19. How do you find a particular file from the root level of a Linux server?
20. How do you search for errors or exceptions in a file along with line numbers?

---

# 29. Linux – Permissions & File Transfer

1. What do Linux file permissions 755 and 555 mean?
2. How do you interpret numeric Linux permissions such as 7, 5, 4, and 0?
3. If a script has permissions 755 and you execute `chmod 7444 script.sh`, what will happen?
4. What is the default SFTP port?
5. How would you securely transfer a file from one Linux server to another?
6. What is the difference between SFTP, SCP, and FTP?

---

# 30. Linux – Filesystems

1. How do you mount a filesystem in Linux?
2. How would you configure a filesystem so that it is automatically mounted after reboot?
3. How do you fix an `/etc/fstab` entry permanently?
4. How do you identify the correct UUID for a filesystem?
5. Which command identifies the filesystem UUID?

---

# 31. Ansible

1. What have you used Ansible for?
2. Have you created Ansible playbooks?
3. What is an Ansible Playbook?
4. What is an Ansible Role?
5. What is the difference between an Ansible Playbook and Role?
6. Why are Ansible Roles reusable?
7. How can one playbook call multiple roles?
8. Explain the structure of an Ansible Role.
9. What specific Ansible playbook have you created?
10. How did your Ansible playbook help reduce deployment time?
11. How do you handle errors in Ansible?
12. How do you manage secrets in Ansible?
13. What is the use of Jinja2 templates?
14. What is an Ansible inventory?

---

# 32. Monitoring – Prometheus & Grafana

1. What is Prometheus?
2. What is Grafana?
3. What is the use of Prometheus and Grafana?
4. What kind of data and metrics are collected by Prometheus?
5. What is the exact role of Grafana?
6. What monitoring dashboards/tools are you using?
7. Have you configured Grafana dashboards?
8. How do you monitor your applications?
9. How do you configure monitoring and alerting for application response time?
10. Prometheus is not receiving application metrics. How would you troubleshoot it?
11. How would you configure alerts when service response time exceeds a threshold?
12. How do you design SLO-based alerting while minimizing alert fatigue?
13. How do you correlate logs, metrics, and traces during a production incident?
14. What is the difference between logs, metrics, and traces?

---

# 33. Production Support & Incident Management

1. Do you have production support experience?
2. Do you have incident-management experience?
3. Explain Incident Management.
4. Explain Problem Management.
5. Explain Change Management.
6. Explain your incident response process.
7. What do you do after receiving an alert from Prometheus, Grafana, or CloudWatch?
8. How do you assess impact and severity?
9. How do you verify whether an alert is genuine?
10. What steps do you follow until service restoration and RCA?
11. How do you perform RCA after a production incident?
12. A production incident occurs at 2 AM. How would you lead the troubleshooting process?
13. How would you communicate with stakeholders during a critical incident?
14. How do you handle SLA requirements during incidents?
15. What is Business Impact Analysis?
16. What factors do you consider in Business Impact Analysis?
17. What is IT Risk Management?
18. What is an Operational Service Book?
19. How do you handle a P1 incident?
20. Explain the most challenging production incident you have handled.
21. What architectural improvements did you make after a production incident?
22. How do you handle cascading failures across multiple microservices?

---

# 34. Production Troubleshooting Scenarios

1. Users report that the application is running slowly. How would you troubleshoot the issue end-to-end?
2. Application response time suddenly increases after a release. How would you identify the root cause?
3. A deployment succeeds, but the application fails in Production. How would you troubleshoot it?
4. A production deployment fails halfway through. How would you recover safely?
5. A database migration fails during deployment. What would your recovery plan be?
6. A CI/CD pipeline suddenly starts failing without any code changes. Where would you begin?
7. A container works perfectly in Development but repeatedly crashes in Production. How would you isolate the issue?
8. An application cannot communicate with another microservice. How would you troubleshoot it?
9. Monitoring alerts indicate high CPU usage across multiple Pods. How would you investigate?
10. SSL certificates have expired in Production. How would you renew and validate them safely?
11. Secrets need to be rotated without causing application downtime. How would you approach it?
12. A cloud resource is causing unexpected costs. How would you identify and optimize it?
13. Your production deployment succeeds but users receive intermittent 5xx errors. How would you investigate?
14. A deployment introduces a severe performance regression. Would you immediately roll back or investigate first?
15. How would you design safeguards for production deployments?
16. How would you handle a production deployment triggered incorrectly?
17. How would you recover from infrastructure failure?
18. What recovery strategy do you follow for your application?
19. How do you handle application recovery after an infrastructure failure?

---

# 35. High Availability, DR & Scalability

1. How does Kubernetes ensure high availability and scalability?
2. How would you design a multi-region Kubernetes architecture for high availability?
3. How do you set up disaster recovery for microservices?
4. How does Route 53 perform failover during a DR scenario?
5. How would you redirect traffic to another AWS region during DR?
6. What are RTO and RPO?
7. How would you design a disaster recovery strategy with defined RTO and RPO requirements?
8. How would you migrate a stateful application to Kubernetes with minimal downtime?
9. How would you perform a zero-downtime Kubernetes cluster upgrade?
10. What happens to Pods when a Kubernetes node suddenly goes down?
11. How would you design a self-healing platform for critical production services?

---

# 36. Microservices

1. What are the key differences between Monolithic and Microservices architecture from a DevOps perspective?
2. How would you approach migrating a monolithic application to microservices?
3. What steps would you follow during a monolith-to-microservices migration?
4. What challenges would you expect during migration?
5. How do you decide whether a monolithic application should be converted into microservices?
6. Before moving to microservices, what foundational setup is important?
7. How would you design CI/CD for multiple microservices?
8. How would you set up reusable workflows for multiple microservices?
9. How would you handle cascading failures across multiple microservices?

---

# 37. Cloud Migration

1. Have you worked on any migration projects?
2. How would you migrate an on-premises application to AWS?
3. What migration strategy would you follow?
4. How would you plan rollback during a cloud migration?
5. What challenges can occur during on-premises to AWS migration?
6. Have you worked with on-premises infrastructure?
7. Have you worked with VMware vSphere?
8. Have you worked in both on-premises and cloud environments?

---

# 38. Performance & Capacity

1. How do you troubleshoot application performance degradation?
2. What kind of performance testing tools and services have you used?
3. How frequently do you perform performance testing?
4. How do you determine minimum and maximum Pod counts?
5. How do you perform capacity planning for Kubernetes?
6. How do you optimize CPU and memory resources?
7. How would you investigate a sudden increase in application latency?
8. How would you identify whether high latency is caused by the application or infrastructure?
9. A deployment succeeds but latency increases from 80 ms to 2 seconds. Walk through your debugging approach.
10. Your CI/CD pipeline takes 40 minutes instead of 5 minutes. How would you identify and optimize the bottleneck?

---

# 39. SRE & Operational Excellence

1. What is SRE?
2. What are the four pillars of SRE?
3. How do you define SLOs and SLAs?
4. How do you design SLO-based alerting?
5. How do you reduce alert fatigue?
6. How do you handle production incidents from an SRE perspective?
7. How do you correlate logs, metrics, and traces?
8. How do you design a self-healing platform?
9. How do you improve reliability after a production incident?

---

# 40. Kafka & Event-Driven Systems

1. What is Apache Kafka?
2. What are the major advantages of Kafka?
3. Explain a major Kafka production incident you have handled.
4. How does a Kafka consumer read messages/events from Kafka?
5. What are the commonly used Kafka ports?
6. How does a database application consume events from Kafka and process/update the database?
7. What is Confluent Cloud?
8. What is Confluent Platform?
9. What is the difference between Confluent Cloud and Confluent Platform?
10. How are Kafka credentials/secrets securely retrieved when establishing a connection to Kafka?
11. What is Azure Event Hubs?
12. What are the primary use cases of Azure Event Hubs?
13. What are the major limitations of Azure Event Hubs?
14. How is Azure Event Hubs different from Apache Kafka?
15. What common production issues can occur with Azure Event Hubs?

---

# 41. General Cloud Concepts

1. What is IaaS?
2. What is PaaS?
3. What is SaaS?
4. Explain the difference between IaaS, PaaS, and SaaS.
5. What is the difference between EC2 and EKS?
6. What is the difference between AWS VM-based deployment and container-based deployment?

---

# 42. Azure – Interview Questions

1. What Azure services have you worked with?
2. What is an Azure Virtual Machine?
3. What is an Azure Virtual Machine Scale Set?
4. What is the difference between Azure VM and VMSS?
5. When would you use Azure VM vs VMSS?
6. What Azure container services have you worked with?
7. Have you used Azure Container Instances?
8. Have you used Azure Container Apps?
9. How do you ensure high availability for applications in Azure and Kubernetes?
10. What configuration-level considerations do you take care of while implementing applications in Azure?
11. What monitoring and alerting mechanisms have you implemented in Azure?
12. Have you implemented Azure-native automation services?
13. Have you worked with Azure Automation Runbooks?
14. How would AKS access Azure Key Vault without storing secrets in the cluster?

---

# 43. Application & Build Tools

1. What is the difference between `mvn clean install` and `mvn clean package`?
2. What type of tests do you perform in CI/CD pipelines?
3. What is UAT?
4. What is the purpose of unit testing in a CI/CD pipeline?
5. What happens when a build fails during the pipeline?

---

# 44. Scripting & Programming

1. Do you have exposure to Python scripting?
2. How comfortable are you with Python?
3. What is the difference between Shell scripting and Python?
4. What repetitive tasks have you automated using Bash/Shell scripting?
5. Give a real-time example of automation you implemented.
6. What kind of automation scripts have you created?
7. Have you automated anything to make operations easier?
8. Were your automations built using native tools or third-party tools?
9. Write a Shell script to monitor CPU utilization.
10. Write a Shell script to monitor a Kubernetes Pod.
11. Write a Shell script to restart a service if it goes down.
12. Write a Shell script for log cleanup.

---

# 45. Advanced DevOps Architecture Scenarios

1. How would you design a multi-tenant EKS cluster with network, service, RBAC, and cost isolation?
2. How would you design a multi-region Kubernetes architecture for high availability?
3. How would you design GitOps for 20+ teams with independent release cycles?
4. How would you design reusable Terraform modules for enterprise projects?
5. How would you design highly secure CI/CD architecture using least privilege?
6. How would you secure secrets for 100+ microservices?
7. How would you implement runtime security beyond image vulnerability scanning?
8. How would you design SLO-based monitoring with minimal alert fatigue?
9. How would you design a self-healing platform for critical production services?
10. How would you design disaster recovery with defined RTO and RPO?
11. How would you prevent configuration drift across multiple environments?
12. How would you prevent race conditions when multiple teams trigger Production deployments?
13. How would you design a reliable rollback mechanism for Production?
14. How would you handle cascading failures across multiple microservices?
15. How would you optimize a large Terraform state and slow Terraform plan?
16. How would you optimize a slow CI/CD pipeline?

---

# 46. Frequently Repeated High-Priority Questions

These questions appeared repeatedly across the interview experiences:

1. Explain your project and your role.
2. Explain your complete CI/CD pipeline.
3. How do you troubleshoot a failed CI/CD pipeline?
4. What is Terraform State?
5. How do you manage Terraform State in a team?
6. What is Terraform State Locking?
7. What happens if Terraform State is deleted or corrupted?
8. What is Terraform Drift?
9. How do you handle Terraform Drift?
10. What is the difference between `count` and `for_each`?
11. What are Terraform Modules?
12. How do you manage Terraform across multiple environments?
13. Explain Kubernetes Architecture.
14. Explain the complete request flow from browser to Kubernetes Pod.
15. What is CrashLoopBackOff?
16. How do you troubleshoot CrashLoopBackOff?
17. What happens when a Pod is Pending?
18. How do you troubleshoot a Pending Pod?
19. What is the difference between Deployment and StatefulSet?
20. What are Taints, Tolerations, and Node Affinity?
21. What is HPA and how does it work?
22. How do you achieve zero downtime in Kubernetes?
23. How do you troubleshoot 502/503 errors?
24. What is the difference between ALB and NLB?
25. What is the difference between public and private subnets?
26. What is the difference between Security Groups and Network ACLs?
27. How do you troubleshoot an unreachable EC2 instance?
28. How do you manage AWS secrets securely?
29. How do you implement Blue-Green deployment?
30. How do you roll back a failed Production deployment?
31. Explain your production incident and RCA.
32. How do you monitor applications using Prometheus, Grafana, and CloudWatch?
33. How do you troubleshoot high application latency?
34. How do you manage Kubernetes Secrets?
35. How do you connect EKS with IAM?
36. How do you perform an EKS cluster upgrade?
37. How do you troubleshoot an application accessible inside Kubernetes but not externally?
38. How do you design highly available AWS infrastructure?
39. How do you handle production incidents and SLA requirements?
40. How do you secure CI/CD, Kubernetes, Terraform, and AWS?

---

# 47. Hands-On Questions to Practice

1. Write Terraform code to create 5 EC2 instances with unique names.
2. Delete one specific EC2 instance using Terraform.
3. Write Terraform code to create an EKS cluster.
4. Write a Dockerfile for a Node.js application.
5. Write a Kubernetes Deployment YAML.
6. Write a Kubernetes Deployment with requests and limits.
7. Write a Kubernetes Deployment with readiness and liveness probes.
8. Write a Kubernetes NetworkPolicy to restrict Pod communication.
9. Write a Jenkins Declarative Pipeline for Checkout, Build, Deploy, and Post actions.
10. Write a Shell script to monitor CPU utilization.
11. Write a Shell script to send an email when CPU usage exceeds 90%.
12. Write a Shell script to monitor whether a Kubernetes Pod is running.
13. Write a Shell script for weekly log cleanup.
14. Explain a Jenkins Groovy pipeline.
15. Explain Terraform code for multiple environments.
16. Explain the Terraform structure of your project.

---

# 48. Interview Preparation Focus

## Highest Priority

* AWS
* Terraform
* Kubernetes/EKS
* CI/CD
* Jenkins
* Docker
* Git
* Linux
* Monitoring
* Production Troubleshooting

## Important Supporting Topics

* Ansible
* AWS IAM & Security
* Secrets Management
* SonarQube
* Checkov
* Checkmarx
* Shell Scripting
* Networking
* Route 53
* ALB/NLB
* Disaster Recovery
* SRE

## Scenario Pattern to Practice

For scenario-based questions, structure your thinking around:

**Detect → Investigate → Identify Root Cause → Mitigate → Recover → Prevent Recurrence**
