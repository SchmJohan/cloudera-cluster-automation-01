# Cloudera Cluster Automation 
This is a working ansible example accompanying the article [CLOUDERA CLUSTER AUTOMATION MIT ANSIBLE (TEIL 1)](https://blog.ordix.de/technologien/cloudera-cluster-automation-mit-ansible-teil-1-1-1).

## Disclaimer

This repository is only intended for testing and show casing purposes.
Do not use any of the provided components in a production environment.

## General
The playbook in this repository imports a Cloudera Cluster Template via the Cloudera Manager API.
After successful import, the cluster and its configured services are available for usage.
This playbook expects an existing and running Cloudera Manager Instance at the in the inventory specified host.
The following services are created and configured with the current version of the provided template:


| Zookeeper | Oozie | Hue | HDFS | YARN | HIVE |
| --- | --- | --- | --- | --- | --- |

## Usage
**1. Create Inventory**

Edit the inventory file **inventory.yml** and replace `<hostname>`, `<ip_address>`, `<user>` with the ones of your destination host.

**2. Execute Ansible Playbooks**

```shell script
ansible -i inventory.yml playbook.yml
```

**3. Monitor Import Process**

After starting the execution of the ansible playbook, you can monitor the import process in the Cloudera Manager.
The Cloudera Manager WebUI can be accessed under:
---
- http://<ip_address>:7180
- user: admin
- password: admin
---