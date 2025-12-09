<p align="center">
  <img src="https://img.shields.io/badge/AmazonTech_DevLab-Backend_Cloud-orange?style=for-the-badge&logo=aws"/>
  <img src="https://img.shields.io/badge/FastAPI-Production-009688?style=for-the-badge&logo=fastapi"/>
  <img src="https://img.shields.io/badge/Docker-Containerized-blue?style=for-the-badge&logo=docker"/>
  <img src="https://img.shields.io/badge/PostgreSQL-Database-336791?style=for-the-badge&logo=postgresql"/>
  <img src="https://img.shields.io/badge/Status-Online_Globally-green?style=for-the-badge"/>
</p>

---

<h1 align="center">⚡ AmazonTech DevLab — API Cloud Production</h1>
<p align="center"><strong>Backend real rodando em produção na AWS EC2</strong> — autenticação JWT, banco PostgreSQL, auditoria, notas e módulo admin. Totalmente em contêiner.</p>

---

### 🚀 Deploy Online (Public Cloud)
📍 Swagger Docs → **http://100.26.73.245:8005/docs**

Acessa de qualquer lugar.  
Sem localhost, sem tunelamento — **publicamente disponível**.

---

## 🏗 Stack & Infra

| Layer | Tech |
|---|---|
| Language | **Python** |
| Framework | **FastAPI** |
| Auth | **JWT + Roles (admin/user)** |
| DB | **PostgreSQL** |
| Infra | **Docker + Docker Compose** |
| Cloud | **AWS EC2 Ubuntu 24.04 (Free Tier)** |
| Ports | **8005 → 8000 (API)** / **5432 (DB)** |
| Monitoring | Logs + Healthcheck externo |

---

## 🔥 Features implementadas

✔ Registro e Login com JWT  
✔ Refresh e Bearer Token autenticado  
✔ CRUD de Notes com usuário logado  
✔ Sistema **Admin real com permissões**  
✔ **Auditoria completa de ações**  
✔ Banco PostgreSQL persistente em container  
✔ Deploy rodando 24/7 na AWS EC2  
✔ Testada via celular e acesso externo real  

---

## 📜 Diário Técnico — Deploy Cloud

📅 **08/12/2025 → API em Produção Global**

### 1. EC2 Provisionada
- Ubuntu 24.04 | t3.micro Free Tier  
- Security Group liberado: **22 SSH / 8005 API**
- Acesso via Key `.pem`

```bash
ssh -i ~/.ssh/amazontech-key.pem ubuntu@100.26.73.245

2. Setup Ambiente

sudo apt update && sudo apt upgrade -y
sudo apt install docker.io docker-compose -y

3. Build & Run

git clone <repo>
cd amazontech-devlab
sudo docker compose up --build -d

4. Containers Online

sudo docker ps

Serviço	Porta	Status
API	8005 → 8000 interno	✔ UP
PostgreSQL	5432	✔ UP

5. Testes

Endpoint	Status
/signup	✔
/login	✔ Token OK
/me	✔ Autenticado
/notes	✔ CRUD OK
/admin & /audit	✔ apenas admin


⸻

📍 Status atual

Módulo	Situação
Backend API	Online
JWT Auth	OK
Notes CRUD	OK
Auditoria	OK
Admin	OK
Deploy AWS	Ativo
Bugs	Nenhum crítico

Não é demo — é produto real em produção.

⸻

🧭 Roadmap Evolução

🔹 Domínio + DNS
🔹 HTTPS com Certbot + NGINX
🔹 CI/CD GitHub Actions
🔹 Monitoramento com Grafana / Loki
🔹 Migração para RDS
🔹 Dashboard Web (React)

⸻

🖥 Arquitetura Simplificada

Local Dev → GitHub → SSH → AWS EC2 → Docker → FastAPI → PostgreSQL
                               │
                               └── Public Internet (8005)


⸻

👤 Autor

Rafael Rodrigues
📧 rafael.amazontech@gmail.com

Cloud & Backend Developer em construção.
Criador do AmazonTech DevLab — API real rodando na nuvem.
