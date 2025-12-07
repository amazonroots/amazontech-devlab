🚀 AmazonTech DevLab

Backend profissional com FastAPI + Docker + PostgreSQL + JWT + Auditoria + Admin Panel

Autor: Rafael Rodrigues (AmazonTech)
Stack: FastAPI · Python · Docker · Docker Compose · PostgreSQL · JWT · Auditoria · Infra DevOps-ready
Sistema de desenvolvimento: macOS + VS Code + Zsh
Diretório base: ~/AmazonTechDevLab

⸻

📌 Visão Geral

O AmazonTech DevLab é um backend profissional construído em FastAPI, com:

✔ Autenticação via JWT
✔ Módulo de Notas vinculado por usuário
✔ Trilha de Auditoria persistente
✔ Admin Panel para gerenciar usuários
✔ Banco PostgreSQL rodando via Docker
✔ Arquitetura estável e pronta para deploy em cloud (AWS)

Toda operação roda em containers Docker orquestrados por Docker Compose.
O foco do projeto é profissionalismo arquitetural e evolução contínua para ambientes Cloud-native.

⸻

🧭 Sumário
	1.	Visão Geral
	2.	Linha do Tempo do Desenvolvimento
	3.	Histórico Técnico (Diário Completo)
	4.	Arquitetura Atual
	5.	Docker & Execução
	6.	Modelos e Schemas
	7.	Autenticação e Segurança JWT
	8.	Módulo de Notas
	9.	Auditoria
	10.	Admin Panel
	11.	Solução de Erros e Casos Reais
	12.	Status Atual
	13.	Roadmap (Próximas Etapas)
	14.	Como rodar o projeto em 30 segundos

⸻

🕒 Linha do Tempo

• Início do projeto: 06/11/2025
• Backend estável consolidado: 11/11/2025
• Limpeza arquitetural final e auditoria completa: 07/12/2025

⸻

🔥 HISTÓRICO TÉCNICO COMPLETO (DIÁRIO DE DESENVOLVIMENTO)

Dia 1 — 06/11/2025

Tema: montar ambiente, limpar lixo antigo e estruturar o projeto do zero.

Ferramentas preparadas: Docker Desktop, Docker Compose, Python 3.12, VS Code + extensões.

Problemas: diretórios antigos, VS Code abrindo pasta errada, Docker sem .yml, imagens antigas.
Ações: limpeza geral, ajustes no VS Code, recriação dos arquivos base.

Resultado: projeto abriu corretamente. Backend existia, mas instável.

⸻

Dia 2 — 07/11/2025

Tema: Docker + banco + bug crítico do bcrypt.

Erro encontrado ao usar /signup:

ValueError: password cannot be longer than 72 bytes

→ Causa: limitação do bcrypt.

Solução: migração da camada de hash para pbkdf2_sha256 com passlib.

Resultado: ambiente rodando, bug isolado na segurança.

⸻

Dia 3 — 08/11/2025

Tema: refatoração de segurança + JWT estável.

Alterações realizadas:
• bcrypt removido
• pbkdf2_sha256 ativado
• auth.py, security.py, schemas.py reorganizados
• /signup, /login, /me funcionando
• Módulo de notas vinculado a usuários
• Início da auditoria com log_action

Resultado: JWT 100% funcional.

⸻

🏛 Arquitetura Atual (Improved Visual)

AmazonTechDevLab/
├── auth.py              → login/signup/me
├── notes.py             → CRUD de notas do usuário
├── admin_routes.py      → /admin (promote, list users)
├── audit.py             → log_action()
├── audit_routes.py      → /audit/logs (admin only)
├── security.py          → JWT + Hash PBKDF2-SHA256
├── models.py            → User, Note, AuditLog
├── schemas.py           → Pydantic (User, Token, Note…)
├── db.py                → SessionLocal, engine, Base
├── docker-compose.yml   → API + PostgreSQL
├── Dockerfile           → Build da API
├── main.py              → FastAPI principal
└── logs/                → auditoria persistente


⸻

🐳 Docker & Execução

Base da arquitetura:

API → container porta 8000
Host → porta 8005

Banco rodando como container Postgres 15.

⸻

🧬 Modelos

User: id, username, email, hashed_password, is_admin
Note: id, texto, owner_id
AuditLog: ação, detail, ip, user_id, data

⸻

🔐 Segurança JWT

• Hash seguro com PBKDF2-SHA256
• JWT com expiração
• OAuth2PasswordBearer no /login

⸻

📓 Notas

Rotas: /notes GET e POST
Somente autenticado.

⸻

📊 Auditoria

log_action() grava:

signup
login_success
login_failed
note_created
… e eventos sensíveis.

Rota admin-only: /audit/logs

⸻

🛡 Admin Panel

• Listar usuários
• Promover usuário
• Só admin acessa /admin/*

⸻

🧯 Caso real: erro OSError 48

Causa: container já usando porta
Solucionado após limpeza + rebuild

⸻

🔥 Status Atual

✔ Backend estável
✔ JWT está redondo
✔ Auditoria completa
✔ Admin funcional
✔ Docker pronto para cloud
⚙ Próximo passo: deploy AWS

⸻

🏆 Roadmap Futuro

– Deploy AWS EC2 (Free Tier)
– GitHub Actions CI/CD
– HTTPS com Nginx + Certbot
– Banco migrado para RDS
– Terraform + IaC completo
– ArgoCD + GitOps

⸻

🚀 Como rodar em 30 segundos

git clone https://github.com/amazonroots/amazontech-devlab.git
cd amazontech-devlab
docker compose up --build
http://localhost:8005/docs

(Coloque um print do Swagger abaixo para impacto visual)

📌 → Inserir imagem aqui depois
📸 Swagger UI rodando localmente na porta 8005
