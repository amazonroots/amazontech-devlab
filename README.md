AmazonTech DevLab — Backend FastAPI + Docker + PostgreSQL + JWT + Auditoria + Admin

Autor: Rafael Rodrigues (AmazonTech)
Stack: FastAPI · Python · Docker · Docker Compose · PostgreSQL · JWT · Auditoria · Infra DevOps-ready
Sistema de desenvolvimento: macOS + VS Code + Zsh
Diretório base: ~/AmazonTechDevLab

⸻

Visão Geral

O AmazonTech DevLab é um backend profissional construído em FastAPI, com autenticação via JWT, módulo de notas por usuário, trilha de auditoria persistente e módulo administrativo para gestão de usuários.
Todo o ambiente roda em containers Docker orquestrados por Docker Compose, com PostgreSQL como banco principal e arquitetura preparada para evolução futura em Cloud (AWS, Terraform, EKS, GitOps).

⸻

Linha do Tempo
	•	Início do projeto: 06/11/2025
	•	Backend estável consolidado: 11/11/2025
	•	Sessões seguintes focadas em auditoria, permissões e limpeza arquitetural até 07/12/2025

⸻

Dia 1 — 06/11/2025

Tema: montar ambiente, limpar lixo antigo e fazer o projeto abrir certo.

Infra inicial preparada

Ferramentas checadas/instaladas:
	•	Docker Desktop
	•	Docker Compose
	•	Python 3.12
	•	VS Code + extensões principais

Problemas encontrados
	•	Conflito de diretórios antigos (AmazonTechDevLab velho x novo).
	•	VS Code abrindo pasta errada.
	•	Docker não encontrando docker-compose.yml.
	•	Resquícios de containers, imagens e configs antigas no macOS.

Ações tomadas
	•	Limpeza manual de containers, volumes e imagens antigas.
	•	Ajuste do settings.json do VS Code para abrir sempre na pasta correta.
	•	Criação/recriação dos arquivos base do projeto.

Situação ao final do dia
	•	Projeto abrindo na pasta certa.
	•	Arquivos principais criados.
	•	Autenticação e build ainda instáveis, mas o esqueleto do backend já existia.

⸻

Dia 2 — 07/11/2025

Tema: Docker, banco e o bug do hash de senha.

Dockerfile e docker-compose alinhados

Base da arquitetura:
	•	API em FastAPI
	•	DB com PostgreSQL 15
	•	Comunicação via DATABASE_URL

Bug crítico no /signup
	•	/signup retornando 500 Internal Server Error por causa do bcrypt.
	•	Erro:

ValueError: password cannot be longer than 72 bytes
	•	Causa: limitação do bcrypt e uso inadequado na camada de hash de senha.

Situação ao final do dia
	•	Infra toda OK (Docker + PostgreSQL conversando).
	•	Bug isolado na lógica de segurança, não no Docker nem no banco.

⸻

Dia 3 — 08/11/2025

Tema: refatorar segurança, arrumar hash de senha e deixar JWT redondo.

Refatoração da camada de segurança
	•	Saiu: bcrypt (limite de 72 bytes).
	•	Entrou: pbkdf2_sha256 via passlib em security.py.

Arquivos ajustados:
	•	security.py — nova estratégia de hash + geração/validação de JWT.
	•	auth.py — uso correto de hash_password e verify_password.
	•	schemas.py — LoginIn, UserCreate, Token, etc.
	•	models.py — modelos User e Note bem definidos.
	•	notes.py — CRUD autenticado de notas.

Comandos de rebuild executados
	•	docker compose down -v --remove-orphans
	•	docker compose up --build

Resultados
	•	API sobe limpa.
	•	/signup funcionando.
	•	/login gera token JWT.
	•	/me retorna o usuário autenticado.
	•	/notes protegido com JWT, vinculando notas ao usuário.
	•	Início do módulo de auditoria (audit.py):
	•	Função log_action criada para logar ações como signup, login, notes.
	•	Integração completa viria nas sessões seguintes.

⸻

Arquitetura Atual (Visão Geral)

Estrutura base em ~/AmazonTechDevLab:
	•	auth.py — rotas /signup, /login, /me + dependências de autenticação.
	•	audit.py — função log_action para registrar eventos sensíveis.
	•	audit_routes.py — rotas de consulta de logs (admin).
	•	admin_routes.py — rotas administrativas (/admin/*).
	•	db.py — engine, SessionLocal, get_db, Base.
	•	docker-compose.yml — orquestra API + PostgreSQL.
	•	Dockerfile — build da imagem da API.
	•	main.py — app FastAPI principal + include_router.
	•	models.py — User, Note, AuditLog e relacionamentos.
	•	notes.py — rotas de notas autenticadas.
	•	requirements.txt — dependências Python.
	•	schemas.py — Pydantic (UserCreate, UserOut, LoginIn, Token, Note*, AuditLog*).
	•	security.py — hash PBKDF2-SHA256 + JWT.
	•	start.sh — script de entrada do container.
	•	logs/ — pasta reservada para logs/auditoria.

Pontos-chave da arquitetura:
	•	Autenticação: auth.py + security.py + schemas.py + models.py.
	•	Persistência: db.py + models.py.
	•	Notas do usuário: notes.py + modelo Note (1:N com User).
	•	Auditoria: audit.py + audit_routes.py (apenas admin).

⸻

Docker & Infra

Dockerfile (conceito)
	•	Base: python:3.12-slim
	•	Passos gerais:
	1.	Copiar requirements.txt.
	2.	Rodar pip install -r requirements.txt.
	3.	Copiar o código para /app.
	4.	Definir WORKDIR /app.
	5.	Comando padrão: uvicorn main:app --host 0.0.0.0 --port 8000 --reload.

docker-compose.yml (ambiente local)

Serviços principais:
	•	db
	•	Imagem: postgres:15
	•	container_name: amazontech_db
	•	Variáveis de ambiente:
	•	POSTGRES_USER=postgres
	•	POSTGRES_PASSWORD=postgres
	•	POSTGRES_DB=amazontech_db
	•	Portas: 5432:5432
	•	Volume: postgres_data:/var/lib/postgresql/data
	•	api
	•	build: .
	•	container_name: amazontech_api
	•	command: uvicorn main:app --host 0.0.0.0 --port 8000 --reload
	•	volumes: .:/app
	•	depends_on: db
	•	environment: DATABASE_URL=postgresql+psycopg2://postgres:postgres@db:5432/amazontech_db
	•	ports: "8005:8000" → container na 8000, host acessa em 8005.

Volumes:
	•	postgres_data

Status:
	•	Sobe limpo com docker compose up --build.
	•	Banco e API conversando via hostname db.
	•	Swagger disponível em http://localhost:8005/docs.

⸻

Modelos (models.py)

User
	•	Tabela: users
	•	Campos:
	•	id (PK)
	•	username (único, obrigatório)
	•	email (único, obrigatório)
	•	hashed_password (obrigatório)
	•	created_at (timestamp, default NOW())
	•	is_admin (Boolean, default False, obrigatório)
	•	Relacionamentos:
	•	notes — relação 1:N com Note (cascade delete).
	•	audit_logs — relação 1:N com AuditLog.

Note
	•	Tabela: notes
	•	Campos:
	•	id (PK)
	•	text
	•	created_at
	•	owner_id (FK → users.id)
	•	Relacionamento:
	•	owner — volta para User.

AuditLog
	•	Tabela: audit_logs
	•	Campos:
	•	id (PK)
	•	action (string)
	•	detail (texto opcional)
	•	ip (string opcional)
	•	user_id (FK opcional → users.id)
	•	created_at (timestamp)
	•	Relacionamento:
	•	user — opcional, aponta para User.

⸻

Schemas (schemas.py)

Principais esquemas Pydantic:
	•	UserCreate — username, email, password.
	•	UserOut — dados públicos do usuário (sem senha).
	•	LoginIn — username, password.
	•	Token — access_token, token_type.
	•	NoteCreate — text.
	•	NoteOut — dados da nota.
	•	NoteList — lista de NoteOut.
	•	AuditLogOut — id, action, detail, ip, user_id, created_at.
	•	AuditLogList — logs: List[AuditLogOut].

⸻

Segurança (security.py)

Decisões
	•	Remoção do bcrypt (limite de 72 bytes).
	•	Adoção de pbkdf2_sha256 via passlib.context.CryptContext.

Funções principais
	•	hash_password(plain_password) → retorna hash seguro.
	•	verify_password(plain, hashed) → compara senha com hash.
	•	create_access_token(data) → gera JWT com expiração.
	•	decode_token(token) → valida o token e retorna payload.

Resultado:
	•	Bug crítico do /signup resolvido.
	•	JWT funcionando, integrado com get_current_user.

⸻

Autenticação (auth.py)

Rotas
	•	POST /signup
	•	Recebe UserCreate.
	•	Verifica se username/email já existem.
	•	Salva usuário com hashed_password.
	•	Retorna UserOut.
	•	POST /login
	•	Recebe LoginIn.
	•	Valida credenciais.
	•	Gera token do tipo Bearer (Token).
	•	GET /me
	•	Lê Authorization: Bearer <token>.
	•	Retorna o usuário autenticado.

Dependências
	•	oauth2_scheme = OAuth2PasswordBearer(tokenUrl="/login")
	•	get_current_user usando decode_token + consulta no banco.

Status: fluxo completo testado no Swagger.

⸻

Notas (notes.py / main.py)

Rotas
	•	GET /notes
	•	Requer usuário autenticado.
	•	Lista notas do usuário (owner_id = current_user.id).
	•	POST /notes
	•	Requer usuário autenticado.
	•	Cria nota vinculada ao usuário logado.

Uso: módulo simples e prático para testar JWT na prática.

⸻

Auditoria (audit.py + audit_routes.py)

Função log_action

log_action(db, action, detail, user=None, ip=None) registra em audit_logs eventos como:
	•	signup
	•	login_success
	•	login_failed
	•	note_created
	•	Outros eventos sensíveis.

Rotas de auditoria
	•	GET /audit/logs
	•	Retorna logs em ordem do mais recente para o mais antigo.
	•	Protegida: apenas is_admin = True.
	•	Usa require_admin().

⸻

Admin (admin_routes.py)

Rotas principais:
	•	GET /admin/users
	•	Lista todos os usuários do sistema.
	•	Acesso exclusivo para admin.
	•	POST /admin/promote/{user_id}
	•	Promove um usuário comum para admin.
	•	Protegida por require_admin().

⸻

Comandos Oficiais

Dentro da pasta AmazonTechDevLab:

Subir ambiente do zero (rebuild completo)
	•	docker compose down -v --remove-orphans
	•	docker compose up --build

Apenas subir (sem rebuild)
	•	docker compose up

Parar tudo (sem apagar volume)
	•	docker compose down

⸻

Como qualquer dev pode continuar
	1.	Ter Docker + Docker Compose instalados.
	2.	Clonar/copiar a pasta AmazonTechDevLab com todos os arquivos.
	3.	Na raiz do projeto, rodar:
	•	docker compose up --build
	4.	Acessar:
	•	Swagger: http://localhost:8005/docs
	5.	Fluxo de teste recomendado:

	•	POST /signup
	•	POST /login
	•	Copiar token retornado
	•	GET /me
	•	POST /notes
	•	GET /notes
	•	GET /audit/logs (se usuário admin)
	•	GET /admin/users

⸻

Sessão — Erro 48 (Address already in use)

Data: 12/11/2025
Problema: OSError: [Errno 48] Address already in use.

Causas reais
	1.	Container Docker já usando a API
	•	amazontech_api já estava rodando.
	•	Tentativa de rodar uvicorn local fora do Docker → conflito de porta.
	2.	Execução de uvicorn na pasta errada
	•	Projeto atualizado estava em AmazonTechDevLab.
	•	Rodar uvicorn em diretório antigo gerava confusão e erros.

Solução
	•	Limpeza total de containers, redes e volumes.
	•	Reconstrução com docker compose up --build.
	•	Decisão: rodar sempre via Docker, sem subir uvicorn solto em paralelo.

Resultado
	•	API respondendo em:
	•	curl http://localhost:8005/health
	•	Resposta: { "status": "ok" }
	•	Erro 48 resolvido.
	•	Ambiente estável.

⸻

Sessão — 11/11/2025

Tema: consolidar o backend em nível profissional.

O que foi feito
	1.	Organização e unificação da base:
	•	Arquivos centrais:
main.py, auth.py, notes.py, audit.py, audit_routes.py,
admin_routes.py, models.py, schemas.py, db.py,
security.py, start.sh.
	•	Infra de suporte: Dockerfile, docker-compose.yml, .env, requirements.txt alinhados.
	2.	Banco e ORM:
	•	Base.metadata.create_all() criando:
	•	users
	•	notes
	•	audit_logs
	•	Testes via psql dentro do container.
	3.	Autenticação JWT completa:
	•	/signup, /login, /me funcionando.
	•	OAuth2 + Swagger testados.
	4.	Auditoria:
	•	audit_logs gravando ações sensíveis.
	•	/audit/logs listando trilha de ações (apenas admin).
	5.	Elevação de privilégios (admin):
	•	No psql do container:
	•	UPDATE users SET is_admin = true WHERE username = 'admin';
	•	Confirmado is_admin = true para o usuário.
	6.	Testes completos via Swagger:
	•	/signup, /login, /me, /notes, /audit/logs, /health, /dbstatus
— todos OK.

⸻

Sessão — 17/11/2025

Tema: corrigir definitivamente permissões, admin e fluxo de autenticação.

Problemas encontrados
	•	Usuário admin não era reconhecido como admin (is_admin = false).
	•	Erros 401/403 em rotas protegidas (/admin/*, /audit/logs).
	•	Login retornava token, mas backend tratava usuário como comum.

Solução
	1.	Acesso ao banco:
	•	docker exec -it amazontech_db psql -U postgres -d amazontech_db
	2.	Consulta de usuários:
	•	SELECT id, username, is_admin FROM users;
	3.	Ajuste do admin:
	•	UPDATE users SET is_admin = true WHERE username = 'admin';
	4.	Novo login, uso do token no Swagger (Authorize).
	5.	Testes:
	•	/admin/users — lista de usuários.
	•	/audit/logs — histórico de auditoria.
	•	Rotas protegidas respeitando is_admin.

Estado após 17/11:
	•	Autenticação 100% redonda.
	•	Admin funcional.
	•	Auditoria plugada no fluxo real de uso.

⸻

Sessão — 07/12/2025

Tema: limpeza arquitetural e enxugamento da API pública.

Objetivo

Deixar o Swagger / OpenAPI 100% coerente com o que deve aparecer externamente:
	•	Autenticação
	•	Notas
	•	Admin
	•	Auditoria
	•	Healthchecks

E remover qualquer resto de feature experimental antiga.

Ações
	1.	Revisão de main.py:
	•	Apenas:
	•	from auth import router as auth_router
	•	from notes import router as notes_router
	•	from audit_routes import router as audit_router
	•	from admin_routes import router as admin_router
	•	app.include_router(auth_router)
	•	app.include_router(notes_router)
	•	app.include_router(audit_router)
	•	app.include_router(admin_router)
	•	Nenhuma rota “solta” ou experimental registrada.
	2.	Revisão de arquivos:
	•	Confirmado que todos os endpoints visíveis batem com o código.
	3.	Rebuild total do Docker:
	•	docker compose down -v --remove-orphans
	•	docker system prune -a -f
	•	docker compose build --no-cache
	•	docker compose up
	4.	Verificação via curl no OpenAPI:
	•	curl http://localhost:8005/openapi.json
	•	Conferido que só existem as rotas esperadas:
	•	/signup
	•	/login
	•	/me
	•	/notes
	•	/admin/users
	•	/admin/promote/{user_id}
	•	/audit/logs
	•	/health
	•	/dbstatus
	•	/

Resultado
	•	API pública enxuta, limpa e profissional.
	•	Sem rota experimental sobrando.
	•	Pronta para:
	•	Portfólio
	•	GitHub
	•	Entrevista técnica
	•	Deploy em nuvem.

⸻

Observação Operacional

Regra de ouro:

Sempre que iniciar um dia pesado de trabalho no DevLab:
	•	copiar e colar todos os códigos,
	•	revisar com IA,
	•	só depois sair mexendo.

Motivo:
	•	Ferramentas de IA às vezes “viajam”.
	•	Projeto é grande e sério o bastante para não ter código experimental perdido.
	•	O backend hoje já está em nível de empresa — precisa ser tratado como tal.

⸻

Status Final do AmazonTech DevLab (pós 07/12/2025)
	•	Autenticação: estável, com JWT e controle de acesso.
	•	Auditoria: trilha de ações persistente, exposta via /audit/logs apenas para admin.
	•	Admin: gerenciamento de usuários e promoção para admin funcionando.
	•	Notas: CRUD autenticado por usuário.
	•	Docker: ambiente local sólido, pronto para ser espelhado na nuvem.
	•	Infra-as-Code: plano definido (Terraform + GitHub Actions + ArgoCD).
	•	Pronto para a próxima fase: deploy em AWS e exposição como peça central de portfólio Dev/Cloud/DevOps.

⸻

AmazonTech DevLab — Deploy AWS EC2 (Plano)

Motivação

Subir o backend profissional do AmazonTech DevLab em ambiente AWS (Free Tier), usando Docker em uma instância EC2, para demonstrar experiência real em Cloud/DevOps.

Arquitetura alvo

Cliente → Internet → EC2 Ubuntu → Docker Compose → API + PostgreSQL

Passos gerais
	1.	Configuração da conta AWS
	•	Criar conta AWS com Free Tier.
	•	Configurar faturamento e alertas de custo.
	2.	Criação de usuário IAM com MFA
	•	Usuário específico para uso de CLI.
	•	Políticas mínimas para EC2, VPC, CloudWatch.
	•	MFA habilitado.
	3.	Configuração da AWS CLI local
	•	aws configure com Access Key / Secret Key do usuário IAM.
	•	Região padrão definida.
	4.	Provisionamento EC2 (Free Tier)
	•	Instância t2.micro ou t3.micro (Ubuntu).
	•	Security Group liberando:
	•	Porta 22 (SSH) para IP específico.
	•	Porta 8005 (HTTP da API) para acesso público (ou via ALB no futuro).
	5.	Instalação do Docker/Compose via SSH
	•	Acesso SSH à instância.
	•	Instalação do Docker Engine e Docker Compose.
	6.	Deploy da aplicação
	•	git clone do repositório amazontech-devlab.
	•	Ajuste de variáveis de ambiente (.env).
	•	docker compose up --build -d.
	7.	Teste do endpoint público
	•	Acessar:
	•	http://<ip-da-ec2>:8005/docs
	•	Testar:
	•	/signup, /login, /me, /notes, /admin/users, /audit/logs.
	8.	Monitoramento básico
	•	Logs via docker logs.
	•	Verificação de uso de CPU/Memória na EC2.
	•	Planejamento futuro de CloudWatch Logs/Alarms.

Próximos passos planejados
	•	CI/CD com GitHub Actions (build + push de imagem + deploy).
	•	HTTPS com Nginx + Certbot (reverse proxy na frente da API).
	•	Migração do banco do container para RDS PostgreSQL gerenciado.
	•	Infraestrutura como código com Terraform (VPC, EC2/EKS, RDS, Security Groups).
	•	GitOps com ArgoCD para gerenciamento declarativo do estado do cluster em nuvem.
