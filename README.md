# Ansible AWS Lab – Docker & Linux Administration

Este repositório contém um laboratório prático de Ansible focado em administração Linux, instalação de Docker e deploy automatizado de uma aplicação containerizada em uma VM na AWS.

## 🎯 Objetivo
Demonstrar habilidades práticas em:
- Ansible (playbooks, variáveis, idempotência)
- Administração Linux
- Docker
- Automação de configuração
- Boas práticas de segurança

## 🧱 Arquitetura
- 1 VM Ubuntu (AWS EC2)
- Ansible Controller
- Ansible Target
- Docker Engine
- Aplicação Java containerizada

## 📁 Estrutura
ansible-aws-lab/
├── playbooks/
│ ├── basic-setup.yaml
│ ├── docker-api.yaml
│ └── user-setup.yaml
├── group_vars/
├── hosts.example
└── ansible.cfg


## 🚀 Playbooks

### 1️⃣ basic-setup.yaml
- Atualiza pacotes
- Instala utilitários básicos (htop, curl, git)

### 2️⃣ docker-api.yaml
- Instala Docker via repositório oficial
- Inicia serviço Docker
- Executa aplicação Java em container
- Expõe porta 8081

### 3️⃣ user-setup.yaml
- Cria usuário `devops`
- Configura permissões sudo e docker
- Cria diretórios `/opt/app` e `/opt/logs`
- Ajusta ownership e permissões

## ▶️ Como executar

```bash
ansible-playbook playbooks/basic-setup.yaml
ansible-playbook playbooks/docker-api.yaml
ansible-playbook playbooks/user-setup.yaml

🧪 Validações

docker ps
id devops
ls -l /opt
curl http://IP_DA_VM:8081

