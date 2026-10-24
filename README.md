# Linux Ansible Lab

Hands-on Linux system administration and Ansible automation lab using RHEL and Ubuntu virtual machines.

## Environment

- RHEL - Ansible control node
- Ubuntu - Managed server
- VirtualBox
- SSH
- Ansible Core 2.16.16

## Progress

### Phase 1: Linux Foundation
- [x] RHEL configured
- [x] Ubuntu configured
- [x] Private network configured
- [x] SSH connectivity established
- [x] Ansible installed
- [x] Ansible inventory configured
- [x] Ansible ping successful

### Phase 2: Ansible Automation
- [x] First Ansible playbook
- [x] Multi-task playbooks
- [x] Variables and facts
- [x] Handlers and templates
- [ ] Ansible roles
- [ ] Multi-server automation
- [ ] Automated software management
- [ ] Automated patch management

### Phase 3: Linux System Administration
- [ ] User and group management
- [ ] File permissions and ownership
- [ ] Process and service management
- [ ] Package management
- [ ] Storage and filesystem management
- [ ] Networking configuration and troubleshooting
- [ ] Firewall configuration
- [ ] SELinux administration
- [ ] Scheduled tasks
- [ ] System troubleshooting
- [ ] Server health checks
- [ ] Kickstart installation
- [ ] Automated Kickstart deployment

### Phase 4: Security and Vulnerability Management
- [ ] Linux security hardening
- [ ] SSH security hardening
- [ ] Least-privilege access controls
- [ ] Logging and auditing
- [ ] Security configuration baselines
- [ ] Vulnerability scanning
- [ ] Vulnerability remediation
- [ ] Security monitoring
- [ ] Ansible security automation

### Phase 5: Git and GitHub
- [x] Create GitHub repository
- [x] Commit and push project files
- [x] Document project progress in README
- [ ] Practice Git branching
- [ ] Practice merging changes
- [ ] Learn pull requests
- [ ] Document project milestones

### Phase 6: Docker and Containers
- [ ] Install Docker
- [ ] Build and run containers
- [ ] Create Dockerfiles
- [ ] Manage container images
- [ ] Configure volumes and networking
- [ ] Practice container security
- [ ] Integrate Docker with Git

### Phase 7: Terraform and Infrastructure as Code
- [ ] Install and configure Terraform
- [ ] Learn providers and resources
- [ ] Use variables and outputs
- [ ] Understand Terraform state
- [ ] Create reusable modules
- [ ] Provision infrastructure
- [ ] Integrate Terraform with Ansible

### Phase 8: CI/CD
- [ ] Learn GitHub Actions
- [ ] Automate configuration validation
- [ ] Validate Ansible playbooks
- [ ] Integrate security scanning
- [ ] Automate container builds
- [ ] Build a basic CI/CD pipeline

### Phase 9: DevSecOps Capstone
- [ ] Combine Linux administration and Ansible
- [ ] Integrate GitHub and version control
- [ ] Integrate Docker and Terraform
- [ ] Implement automated security checks
- [ ] Build an end-to-end automation workflow
- [ ] Document architecture and deployment
- [ ] Publish final project documentation

## Project Milestones

### Milestone 1: First Ansible Playbook
- Created `/opt/ansible-lab` on Ubuntu.
- Used Ansible privlege escalation with `become: true`.
- Verified the directory existed.

### Milestone 2: Multi-Task Ansible Playbook
- Created `/opt/ansible-lab/lab-notes.txt`.
- Applied file permissions of `0644`.
- Verified the file remotely from RHEL.

### Milestone 3: Ansible Variables

- Created `playbooks/variables_facts.yml`.
- Defined a reusable `lab_directory` variable. 
- Used Ansible's file module to create `/opt/ansible-variables-lab`.
- Applied directory permissions of `0755`.
- Verified the directory remotely fromt RHEL control node.
- Confirmed successful execution on the Ubuntu manged server.

### Milestone 4: Ansible Facts

- Created `playbooks/facts.yml`.
- Enabled automatic fact gathering with `gather_facts: true`.
- Used Ansible's `ansible.builtin.debug` module to display system information.
- Retrieved the Ubuntu distribution and operating system version.
- Verified the playbook passed the syntax check.
- Successfully executed the playbook against the Ubuntu managed server.

### Milestone 5: Ansible Facts

- Created `playbooks/handlers.yml`.
- Used the ansible.builtin.copy module to create a lab file on Ubuntu.
- Used notify to trigger a handler when the file changed.
- Used ansible.builtin.debug to display a message when the handler ran.
- Verified the handler executed successfully on the first run.
- Ran the playbook a second time and confirmed change=0, demostrating idempotency.
- Successfully tested the playbook against the Ubuntu managed server.

