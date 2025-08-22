# ansible_k3s
Script for installing and configuring k3s in Ansible

## Example

```yaml
---
- name: Install K3s HA Cluster
  hosts: all
  become: yes
  vars:
    vip: 192.168.0.10
    k3s_token_path: /var/lib/rancher/k3s/server/node-token
    k3s_token_file: /tmp/k3s_token
    k3s_version: "v1.29.1+k3s1"
    main_master: "master1"
    other_master: 
      - "master2"

  tasks:
    - name: Run install_k3s.yml
      include_tasks: ./task/ansible_k3s/playbook.yml
```