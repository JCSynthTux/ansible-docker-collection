# Ansible Collection: Docker

An ansible collection focused around Docker and centered around production-ready roles instead of individual modules.

## Setup

This collection expects you to have these two groups:
- 'docker__swarm_managers'
- 'docker__swarm_workers'

### docker__swarm_managers
Managers belong in this group. This group has to have at least one member

### docker__swarm_workers
Workers belong in this group.
Even if the swarm consists of no worker, it is recommended to define this group in inventory.

## Roles

### docker_plugins
This role manages plugins on the Docker hosts.

### swarm_configs
This role is meant to manage config files in a swarm native fashion with 'docker config'.

### swarm_node_availability
This role is meant to manage the state of Docker nodes in a swarm and should validate if a drain was successfull.

### swarm_node_labels
This role is meant to manage labels of Docker nodes in a swarm. Labels can be assigned on a all, group and host level in inventory.

### swarm_node_remove
This role will safely remove a single node from the swarm. Currently the roles expects there to be at least one master node after removal.

### swarm_secrets
This role is meant to manage secrets and password in a swarm native fashion with 'docker secret'.

### swarm_stacks
This role should deploy docker stacks without having to copy any compose files over to the swarm.
