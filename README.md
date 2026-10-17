# Linux Ansible Lab

Hands-on Linux system administration and Ansible automation lab using RHEL and Ubuntu virtual machines.

## Environment

- RHEL - Ansible control node
- Ubuntu - Managed server
- VirtualBox
- SSH
- Ansible Core 2.16.16

## Progress

- [x] RHEL configured
- [x] Ubuntu configured
- [x] Private network configured 
- [x] SSH connectivity established 
- [x] Ansible installed
- [x] Ansible inventory
- [x] Ansible ping
- [x] First playbook
- [ ] Multiple-server automation
- [ ] Software management 
- [ ] Patch management
- [ ] Security hardening
- [ ] Server scanning

### First Ansible Playbok
- Created `/opt/ansible-lab` on the ubuntu managed server.
- Used Ansible privilege escalation (`become`) to run the task as a root.
- Verified the directory exists on Ubuntu.
