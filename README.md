<div align="center">

# ⚡ AMAZONTECH DEVLAB  
**FastAPI • Docker • PostgreSQL • JWT • Auditoria • Admin • DevOps-Ready**

### 🟣 Backend profissional em containers  
### 🟦 Documentado para portfólio. Construído para nuvem.  
  
<br>

> *Visão neon: arquitetura limpa, interface técnica e estética futurista.*  
> *Sem firula. Sem gerador automático. Projeto real construído na prática.*

<br>

<img src="https://i.imgur.com/XvmYfDP.png" width="800"/>

</div>

---

## 📌 VISÃO GERAL

O **AmazonTech DevLab** é um backend moderno desenvolvido em **FastAPI**, com **autenticação JWT**, **PostgreSQL em Docker**, **módulo de notas com controle de usuário**, **trilha de auditoria persistente**, **painel admin**, e arquitetura preparada para **Cloud (AWS)**.

Criado como **laboratório real de Cloud/DevOps**, documentando toda evolução técnica sem esconder erros, ajustes e correções.  
Código limpo, modular e escalável.

---

## 🧭 SUMÁRIO

- VISÃO GERAL  
- LINHA DO TEMPO  
- HISTÓRICO TÉCNICO  
- ARQUITETURA  
- EXECUÇÃO DOCKER  
- MODELOS & SCHEMAS  
- AUTENTICAÇÃO  
- NOTAS  
- AUDITORIA  
- ADMIN  
- ERROS REAIS SOLUCIONADOS  
- STATUS ATUAL  
- ROADMAP  
- RODAR EM 30 SEGUNDOS  

---

## 🕒 LINHA DO TEMPO

| Data | Evento |
|---|---|
| **06/11/2025** | Ambiente pronto + estrutura inicial |
| **07/11/2025** | Docker + banco + erro bcrypt solucionado |
| **08/11/2025** | JWT + Notas + Auditoria |
| **11/11/2025** | Backend consolidado |
| **07/12/2025** | Documentação + ajustes finais API |

---

## 🔥 HISTÓRICO TÉCNICO DE DESENVOLVIMENTO

**DIA 1 — 06/11/2025**  
Instalação do ambiente, limpeza, pastas antigas removidas.  
Resultado: estrutura base pronta.

**DIA 2 — 07/11/2025**  
Erro no `/signup`: *"password cannot be longer than 72 bytes"*.  
Ajuste: **bcrypt → pbkdf2_sha256 (passlib)**.  
Resultado: autenticação segura e estável.

**DIA 3 — 08/11/2025**  
JWT finalizado, módulo de Notas implementado, logs iniciados.

> **Registro real de um dev construindo, errando, corrigindo e evoluindo.**

---

## 🏛 ARQUITETURA

AmazonTechDevLab/
├── main.py                → App principal
├── auth.py                → Login/Signup/Me
├── notes.py               → CRUD Notas
├── admin_routes.py        → Admin Panel
├── audit.py               → log_action()
├── audit_routes.py        → Logs restritos admin
├── security.py            → JWT + Hash
├── models.py              → ORM Models
├── schemas.py             → Pydantic
├── db.py                  → Engine + Session
├── docker-compose.yml     → API + PostgreSQL
├── Dockerfile             → Build
└── logs/                  → Auditoria Persistente

Arquitetura minimalista → fácil de escalar para **AWS EC2 + RDS + Nginx + CI/CD**.

---

## 🐳 EXECUÇÃO VIA DOCKER

API roda no container porta `8000` → exposta em `8005`.

```bash
docker compose up --build

Swagger aberto em:

http://localhost:8005/docs


⸻

🧬 MODELOS & SCHEMAS
	•	User → email, senha hash, admin flag
	•	Note → texto, dono
	•	AuditLog → ação, data, user_id

⸻

🔐 AUTENTICAÇÃO
	•	Hash com pbkdf2_sha256
	•	JWT com expiração
	•	Rotas protegidas por Bearer Token

Fluxo:
	1.	/signup
	2.	/login → recebe token
	3.	Authorize no Swagger
	4.	acessar /notes

⸻

📓 NOTAS
	•	GET /notes lista notas do usuário autenticado
	•	POST /notes adiciona new note

Simples, funcional e elegante.

⸻

📊 AUDITORIA

log_action() registra:
	•	login
	•	logout
	•	notas criadas
	•	ações sensíveis

Rota Admin: /audit/logs

⸻

🛡 ADMIN
	•	Listar usuários
	•	Promover user admin
	•	Rotas protegidas

Demonstra controle RBAC real.

⸻

🧯 ERROS REAIS SOLUCIONADOS

Address already in use (48)
→ Causa: serviços duplicados
→ Solução: rebuild + uso exclusivo do Docker

⸻

🏆 STATUS ATUAL

✔ Backend pronto
✔ Docker estável
✔ JWT seguro
✔ Auditoria funcional
✔ Código clean
🚀 Próxima etapa: Deploy AWS EC2 Free Tier

⸻

🗺 ROADMAP
	•	Deploy AWS (EC2)
	•	Banco remoto (RDS)
	•	HTTPS com Nginx
	•	CI/CD GitHub Actions
	•	IaC Terraform
	•	Observabilidade + Logging

⸻

🚀 RODAR EM 30 SEGUNDOS

git clone https://github.com/amazonroots/amazontech-devlab.git
cd amazontech-devlab
docker compose up --build
http://localhost:8005/docs


⸻


<div align="center">


⭐ Se gostou, deixe uma Star no repo

🔥 Projeto em evolução — DevSecCloud Journey

</div>
```
