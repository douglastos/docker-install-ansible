# Ansible Docker Installer

This project uses Ansible to install Docker on any supported Linux distribution (Debian/Ubuntu/CentOS/RHEL/AlmaLinux/Rocky).

## ✅ Requirements

- Python 3
- Ansible installed on the control machine
- SSH access to target machines (with sudo privileges)

## 📦 Project Structure

```
docker-install/
├── install_docker.yml         # Main playbook
├── hosts                      # Inventory file
└── roles/
    └── docker/
        ├── tasks/
        │   ├── main.yml
        │   └── repos/
        │       ├── debian.yml
        │       └── redhat.yml
        └── vars/
            ├── debian.yml
            └── redhat.yml
```

## ⚙️ How to use

1. **Clone or copy the files to a local folder**:
   ```bash
   mkdir -p ~/docker-install && cd ~/docker-install
   ```

2. **Edit the `hosts` file with the IPs or hostnames of your machines**.

3. **Run the playbook**:
   ```bash
   ansible-playbook -i hosts install_docker.yml
   ```

4. **Done! Docker will be installed and started.**

## 📝 Inventory example (hosts)

```ini
[docker_hosts]
192.168.1.100 ansible_user=ubuntu ansible_ssh_private_key_file=~/.ssh/id_rsa
```

## 🛠 Local testing (optional)

```ini
[docker_hosts]
localhost ansible_connection=local
```
