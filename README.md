<p align="center">
  <img src="https://img.shields.io/badge/AmazonTech_DevLab-Backend_Cloud-orange?style=for-the-badge&logo=aws"/>
  <img src="https://img.shields.io/badge/FastAPI-Production-009688?style=for-the-badge&logo=fastapi"/>
  <img src="https://img.shields.io/badge/Docker-Containers-blue?style=for-the-badge&logo=docker"/>
  <img src="https://img.shields.io/badge/PostgreSQL-Database-336791?style=for-the-badge&logo=postgresql"/>
  <img src="https://img.shields.io/badge/Status-Online_Globally-green?style=for-the-badge"/>
</p>

<h1 align="center">⚡ AmazonTech DevLab — Cloud Backend em Produção</h1>
<p align="center">API real rodando na AWS EC2 — autenticação JWT, CRUD de notas, auditoria e administração.</p>

---

### 🌍 Deploy em Produção
🔗 **Swagger Docs:** http://100.26.73.245:8005/docs  
Acessível globalmente — sem localhost, sem VPN.

---

## 🧱 Stack
| Camada | Tecnologia |
|---|---|
| Linguagem | Python |
| Framework | FastAPI |
| Banco | PostgreSQL |
| Containers | Docker + Docker Compose |
| Deploy | AWS EC2 Ubuntu |
| Auth | JWT (Login/Signup/Protected Routes) |
| Auditoria | Logging interno |
| Segurança | SSH Key + Security Groups |

---

## 🔥 Recursos Implementados
- Registro e Login com geração de token JWT
- Rotas seguras para usuários autenticados
- CRUD completo de Notes
- Painel Admin com permissões elevadas
- Auditoria de ações
- Banco persistente em contêiner PostgreSQL
- Deploy real em EC2 com IP público
- API online e acessível mundialmente

---

## 📜 Diário Técnico — Deploy 08/12/2025

EC2 criada — Ubuntu 24.04 | t3.micro (Free Tier)
Chave SSH configurada: amazontech-key.pem

Instalação

sudo apt update && sudo apt upgrade -y
sudo apt install docker.io docker-compose -y

Deploy

git clone 
cd amazontech-devlab
sudo docker compose up –build -d

Serviços UP

API: 8005 -> 8000 internal
Postgres: 5432

Testado:
✔ /signup
✔ /login → JWT OK
✔ /notes CRUD
✔ /admin + /audit protegido
✔ healthcheck via curl externo

---

## 📊 Status Atual
| Módulo | Estado |
|---|---|
| Backend | ✔ Online |
| Auth JWT | ✔ |
| Notes CRUD | ✔ |
| Admin | ✔ |
| Auditoria | ✔ |
| Deploy AWS | ✔ Público |
| Bugs | 0 críticos |

---

## 🧭 Roadmap Futuro
- Domínio + HTTPS (Nginx + Certbot)
- Backup & Rotinas automáticas
- CI/CD com GitHub Actions
- Observabilidade (Grafana/Loki)
- Migração futura para RDS
- Dashboard Web (frontend React)

---

## 🧩 Arquitetura Simplificada

Mac → SSH → EC2 → Docker → FastAPI → PostgreSQL
│
└── Internet (porta 8005 pública)

---

## 👨‍💻 Autor
**Rafael Rodrigues**  
📩 rafael.amazontech@gmail.com  

Criador do AmazonTech DevLab — estudo ADS & Cloud, desenvolvendo soluções backend reais com deploy na AWS.
