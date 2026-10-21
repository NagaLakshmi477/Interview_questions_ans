# Pull vs Push Model in Configuration Management

## Pull-Based Model (e.g., Chef)

- Configuration scripts are available on the **CM Server**.
- Nodes (agents) check the CM server every 30 minutes for new configurations.
- If new configurations are found, they are downloaded and executed on the node.

### Architecture:

```
Control Server  --->  CM Server (Stores Configurations / Playbooks)
                           ^
                           |
                     -----------------
                     |       |       |
                  Node 1  Node 2  Node 3
                  (Agent)(Agent) (Agent)

```
# Architecture Overview

## 1. Control Server (e.g., GitHub)
- Acts as the **source of truth** for all Ansible files (playbooks, roles, inventories).

## 2. CM Server (Configuration Management Server)
- Intermediary repository between Control Server and nodes.
- **Gets updated files from the Control Server** (e.g., GitHub).
- Nodes **fetch configuration files** from the CM Server.

## 3. Nodes (Agents)
- Each node has an **agent installed**.
- Agent **polls the CM Server every 30 minutes**.
- Downloads and executes updates if found.



### Disadvantages:

1. Unnecessary traffic (nodes poll every 30 minutes even if no changes)
2. Wasted system resources
3. Increased power usage
4. Requires agent software
5. Protocols developed for agent communication

---

## Push-Based Model (e.g., Ansible)

- Ansible Server contains both the configurations and acts as the control/master node.
- Ansible uses **SSH protocol** to push configurations directly to nodes.

### Architecture:

```plaintext
Ansible Server (Config) ----SSH----> Node 1
                                    Node 2
                                    Node 3
```

### Advantages:

1. Uses secure SSH protocol
2. No agent software required
3. No unnecessary resource usage
4. Easier to manage and scale

---
