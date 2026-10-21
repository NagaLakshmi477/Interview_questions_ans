# Pull vs Push Model in Configuration Management

Configuration management helps us install software, manage configurations, and maintain multiple servers automatically.

There are two common approaches to delivering configurations to servers:

- **Pull Model:** Nodes request configurations from a central server.
- **Push Model:** A central server initiates configuration tasks on the nodes.

---

## 1. Pull-Based Model (e.g., Chef)

In the pull model, configurations are stored on a central configuration management server. Each node checks that server periodically to see whether any new configurations are available.

### Architecture

```text
       Control Server (e.g., GitHub)
                    |
                    | Configuration updates
                    v
              CM Server (Chef)
             /       |       \
            v        v        v
         Node 1    Node 2    Node 3
         (Agent)   (Agent)   (Agent)
             |        |        |
             +--------+--------+
             Pull configurations
```

### Architecture Overview

**1. Control Server (e.g., GitHub)**

- Acts as the source of truth for configuration files.
- Stores version-controlled configuration code.
- Developers update the files whenever changes are required.

**2. CM Server (Configuration Management Server)**

- Stores and manages configuration instructions.
- Receives configuration updates from the source repository or deployment workflow.
- Makes the configurations available to managed nodes.

**3. Nodes (Managed Servers)**

- These are the servers where we install software or apply configurations.
- In Chef's traditional architecture, a Chef client runs on each node.
- The client periodically checks the Chef Server for updates and applies the required configurations.

### Disadvantages of the Pull Model

1. **Unnecessary network traffic:** Nodes may contact the server even when there are no configuration changes.
2. **Resource usage:** Periodic checks consume some CPU, memory, and network resources.
3. **Delayed updates:** Changes may not be applied until the next client run.
4. **Agent installation:** Managed nodes generally require client software, such as Chef Infra Client.
5. **Additional management:** Client software and its communication with the central server must be maintained.

---

## 2. Push-Based Model (e.g., Ansible)

In the push model, the administrator initiates the configuration process from a central control machine. The control machine connects to the target nodes and executes the required configuration tasks.

Ansible is a common example of this approach.

### Architecture

```text
       Ansible Control Node
       (Playbooks + Inventory)
                  |
          Secure SSH Connection
                  |
           +------+------+ 
           |      |      |
           v      v      v
        Node 1  Node 2  Node 3
```

### Architecture Overview

**1. Ansible Control Node**

- Stores or accesses Ansible playbooks, roles, and inventory.
- Defines what needs to be installed or configured.
- Initiates tasks and connects to the target servers.

**2. SSH (Secure Shell)**

- Ansible commonly uses SSH to connect securely to Linux and Unix-based managed nodes.
- It executes the required tasks remotely.
- Windows nodes can be managed through other connection methods, such as WinRM or PSRP.

**3. Nodes (Managed Servers)**

- These are the servers where configurations are applied.
- They generally do not need a permanently installed Ansible agent.
- They need appropriate connectivity, authentication, and the required software for the tasks being performed.

### Advantages of the Push Model

1. **No dedicated Ansible agent required:** Managed nodes generally do not need an Ansible agent installed.
2. **On-demand execution:** The administrator can initiate configuration changes whenever needed.
3. **Less polling traffic:** Nodes do not need to contact a configuration server periodically just to check for updates.
4. **Centralized management:** One control node can manage multiple servers.
5. **Efficient automation:** A single playbook can apply the same configuration across multiple servers.

---

## 3. Pull vs Push: Key Differences

| Feature | Pull Model | Push Model |
|---|---|---|
| Who initiates? | Managed node | Control node |
| How does it work? | Nodes request configurations | Control node initiates tasks |
| Example | Chef | Ansible |
| Agent requirement | Usually requires a client agent | Usually agentless |
| Execution | Often periodic | Usually on demand or scheduled |
| Update timing | Depends on client run frequency | Starts when the control node initiates the run |
| Communication | Depends on the tool's architecture | Commonly SSH in Ansible for Linux/Unix nodes |

## 4. Easy Way to Remember

**Pull Model:** Nodes check the central server to see whether new configurations are available.

**Push Model:** The control server initiates configuration tasks on the managed nodes.

**In simple words:**

- **Pull = Nodes ask for updates.**
- **Push = The control server initiates updates on nodes.**
