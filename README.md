# Ansible
![Ansible](https://img.shields.io/badge/Ansible-EE0000?style=for-the-badge&logo=ansible&logoColor=white)  

Ansible is an open-source automation tool used for **configuration management, application deployment, and orchestration**.  

---

## 🔧 Installation on Ubuntu/Debian

### 1️ Update system packages

```bash
sudo apt update && sudo apt upgrade -y
```

---

### 2️ Install required dependencies

```bash
sudo apt install -y software-properties-common
```

---

### 3️ Add the Ansible PPA (official repository)

```bash
sudo add-apt-repository --yes --update ppa:ansible/ansible
```

---

### 4️ Install Ansible

```bash
sudo apt install -y ansible
```

---

### 5️ Verify installation

```bash
ansible --version
```

 You should see the installed version and configuration paths.

---

##  Optional: Install via Pip (latest version)

```bash
sudo apt install -y python3-pip
pip3 install ansible
```

---

##  Quick Start Example: Ansible Playbook

Once Ansible is installed, you can test it by running a simple playbook.

### Example: Install Nginx on a server

1. Create a file called `nginx-playbook.yml`:

```yaml
---
- name: Install Nginx Web Server
  hosts: localhost
  become: true

  tasks:
    - name: Install Nginx
      apt:
        name: nginx
        state: present
        update_cache: yes

    - name: Ensure Nginx is running
      service:
        name: nginx
        state: started
        enabled: true
```

2. Run the playbook:

```bash
ansible-playbook nginx-playbook.yml
```

This will install and start **Nginx** on your localhost.

---
