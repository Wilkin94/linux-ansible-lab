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
- [x] Ansible roles
- [x] Multi-server automation
- [x] Automated software management
- [x] Automated patch management

### Phase 3: Linux System Administration & RHCSA Preparation
- [x] User and group management (Natively verified labuser and labgroup accounts)
- [ ] File permissions and ownership (`chomd`, `chown`, plus SGID/Sticky Bits)
- [ ] Process and service management (`systemctl`, `ps`, `top`. and `nice` overrides)
- [ ] Software package management (Managing `/etc/yum.repos.d` repositories and `dnf`)
- [ ] Storage and filesystem management (`fdisk`/`parted` partition mapping, secure `/etc/fstab`)
- [ ] Logical Volume Management (Building physical volumes, volume groups, and extending LVs)
- [ ] Networking configuration and troubleshooting (`nmcli` control, static IPs, and connection checks)
- [ ] Basic container management (`podman` rootless runs, data persistence, and systemd intergration)
- [ ] Firewall configuration (Opening ports, assigning zones, and using rich rules in `firewall-cmd`)
- [ ] SELinux administration (Toggling booleans, using `semanage fcontext` / `restorecon`)
- [ ] Scheduled tasks (Automating triggers via `cron` and `at` daemons)
- [ ] System troubleshooting and boot target recovery (Interrupting GRUB to drop in with `rd.break`)
- [ ] Server health checks (Writing basic custon shell scripting for alert validation)
- [ ] Kickstart installation (Authoring automated configuration maps for unattended installs)
- [ ] Automated Kickstart deployment (Deploying fresh headless target instances cleanly)

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

### Milestone 5: Ansible Handlers

- Created `playbooks/handlers.yml`.
- Used the `ansible.builtin.copy` module to create a lab file on Ubuntu.
- Used notify to trigger a handler when the file changed.
- Used `ansible.builtin.debug` to display a message when the handler ran.
- Verified the handler executed successfully on the first run.
- Ran the playbook a second time and confirmed change=0, demostrating idempotency.
- Successfully tested the playbook against the Ubuntu managed server.

### Milestone 6: Ansible Templates

- Created `templates/lab-config.j2`.
- Created `playbooks/templates.yml`.
- Used Jinja2 variables to generate a configuration file.
- Used the `ansible.builtin.template` module to create /opt/ansible-template-lab.txt on Ubuntu. 
- Corrected the variable name to `deployment_environment` to avoid an Ansible reversed-variable warning.
- Verified the generated file contained the expected application name, environment, and managed server address.
- Ran the playbook a second time and confirmed chnaged=0, demonstrating idempotency.
- Successfully tested the playbook against the Ubuntu managed server.

### Milestone 7: Ansible Roles

- Created the `roles/lab_setup/` directory structure.
- Created `roles/lab_setup/tasks/main.yml` to define reuseable tasks.
- Created `playbooks/role_test.yml` to run the role against Ubuntu.
- Used `ansible.builtin.import_role` to import the lab_setup role.
- Used `become: true` to run the task with elevated privileges.
- Successfully created `/opt/ansible-role-lab` on Ubuntu managed server,
- Verified the directory exists with permissions `0755`.
- Comfirmed the playbook passed the syntax check and executed successfully.

### Milestone 8: Multi-Server Automation

- Created `playbooks/multi_server.yml`.
- Created the `linux_servers` parent inventory group.
- Used `ansible.builtin.file` to create `/opt/ansible-multi-server-lab`.
- Verified the directory exists on the Ubuntu managed server with permissions `0755`.
- Successfully ran the playbook with `failed=0`.
- Verified Ansible can target the parent group using an Ansible ping test.
- Note: Only one manager server is currently configured; testing across multiple machines requires adding a second server.

### Milestone 9: Automated Software Management

- Created `playbooks/software_management.yml`.
- Used the `ansible.builtin.package` module to manage software.
- Automated installation of the `tree` package on the Ubuntu managed server.
- Used `state: present` to ensure the package is installed.
- Passed the Ansible playbook syntax check.
- Verified the installed package by running `tree --version` remotely.
- Confirmed successful execution with zero failed hosts.

### Milestone 10: Automated Patch Management

- Created `playbooks/patch_management.yml`.
- Used the `ansible.builtin.apt` module to manage Ubuntu package updates.
- Refreshed the APT package cache before upgrading packages.
- Applied available safe package upgrades using `upgrade: safe`.
- Passed the Ansible playbook syntax check.
- Confirmed the first playbook run completed with zero failed or unreachable hosts.
- Reran the playbook and verified idempotent behavior with `changed-0`.
- Verified the one `rtkit` update remained phased by Ubuntu (80% rollout) and did not force the update.
- No automatic reboot was configured. 

### Milestone 11: User and Group Management

- Created `playbooks/user_management.yml`.
- Used the `ansible.builtin.user` module to create the `labuser` account.
- Used `state: present` to ensure the account exists.
- Passed the Ansible playbook syntax check.
- Ran the playbook successfully against the Ubuntu managed server.
- Verified the `labuser` account with the `id` command.
- Created the `labgroup` using `playbooks/group_management.yml`.
- Used the `ansible.builtin.group` module to manage group creation.
- Verified the group with `getent group labgroup`.
- Added `labuser` to `labgroup` and verified group membership.
- Confirmed the playbooks completed with zero failed or unreachable hosts.

### Milestone 12: RHEL Server01 Installation and Private Network Configuration

- Installed `Red Hat Enterprise Linux 10.2` on the additional `RHEL-Server01` VM.
- Created a dedicated RHEL environment for future RHCSA preparation and native Linux administration practice.
- Configured the second network interface, `enp0s8` for the VirtualBox host-only private network.
- Created a NetworkManager connection named `private-lab` using `nmcli`.
- Configured the static IPv4 address `192.168.56.20/24`.
- Activated the private network connection using `nmcli connection up private-lab`.
- Verified the assigned IP address using `ip addr show enp0s8`.
- Tested network connectivity to the original RHEL control node at `192.168.56.10` using `ping -c 4 192.168.56.10`.
- Confirmed successful connectivity with `0% packet loss`.
- Saved the VirtualBox snapshot `RHEL-Server01-Private-Network-Verified`.
- Preserved the existing RHEL control node and Ubuntu managed server configuration.
