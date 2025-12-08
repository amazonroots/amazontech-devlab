🚀 README.md Profissional — AmazonTech DevLab

<p align="center">
  <img src="https://img.shields.io/badge/AMAZONTECH%20DEVLAB-8A2BE2?style=for-the-badge&logo=amazonaws&logoColor=white" alt="AmazonTech DevLab Logo"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.12-8A2BE2?style=for-the-badge&logo=python&logoColor=white" alt="Python 3.12 Badge"/>
  <img src="https://img.shields.io/badge/FastAPI-⚡-8A2BE2?style=for-the-badge&logo=fastapi&logoColor=white" alt="FastAPI Badge"/>
  <img src="https://img.shields.io/badge/Docker-READY-000000?style=for-the-badge&logo=docker&logoColor=white" alt="Docker Badge"/>
  <img src="https://img.shields.io/badge/PostgreSQL-15-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL Badge"/>
  <img src="https://img.shields.io/badge/JWT-AUTH-8A2BE2?style=for-the-badge&logo=jsonwebtokens&logoColor=white" alt="JWT Badge"/>
  <img src="https://img.shields.io/badge/STATUS-DEV_ACTIVE-8A2BE2?style=for-the-badge" alt="Status Badge"/>
</p>

<h1 align="center">AmazonTech DevLab</h1>

<p align="center">
  Backend profissional com FastAPI, Docker e PostgreSQL —  
  segurança por JWT, auditoria e painel administrativo.  
  Preparado para deploy na nuvem, com documentação clara e estrutura robusta.
</p>

---

## 🧭 Índice

1. [Visão Geral](#-visão-geral)  
2. [Funcionalidades Principais](#-funcionalidades-principais)  
3. [Stack & Tecnologias](#-stack--tecnologias)  
4. [Estrutura do Projeto](#-estrutura-do-projeto)  
5. [Como Rodar Localmente](#-como-rodar-localmente)  
6. [Endpoints Disponíveis](#-endpoints-disponíveis)  
7. [Segurança & Auditoria](#-segurança--auditoria)  
8. [Fluxo de Desenvolvimento & Histórico (Changelog)](#-fluxo-de-desenvolvimento--histórico)  
9. [Roadmap / Próximos Passos](#-roadmap--próximos-passos)  
10. [Sobre o Autor](#-sobre-o-autor)  

---

## 📌 Visão Geral

O **AmazonTech DevLab** é um backend completo construído para ser:

- Modular — fácil de estender, testar e manter.  
- Seguro — com autenticação JWT e logs de auditoria.  
- Containerizado — roda com Docker + Docker Compose.  
- Portátil — pronto para rodar localmente ou ser implantado na nuvem (AWS, VPS, etc.).  
- Documentado — arquitetura clara, README completo, endpoints definidos.  

Ideal para portfólio, testes, protótipos ou base para MVPs.

---

## ✅ Funcionalidades Principais

- Registro e login de usuários com senha hasheada  
- CRUD de notas vinculadas a usuários autenticados  
- Auditoria persistente: registro de ações como login, criação de nota, etc.  
- Painel administrativo: listar usuários, promover para admin  
- API limpa e enxuta, sem endpoints “experimentais” expostos  
- Docker + Postgres configurados para fácil deploy  
- Estrutura pensada para escalar e evoluir  

---

## 🧰 Stack & Tecnologias

| Camada        | Tecnologia / Ferramenta         |
|---------------|----------------------------------|
| Linguagem     | Python 3.12                     |
| Framework     | FastAPI                         |
| Banco         | PostgreSQL 15 (via Docker)      |
| Containers    | Docker + Docker Compose         |
| Autenticação  | JWT + pbkdf2_sha256 (via passlib)|
| ORM / DB      | SQLAlchemy / SQLModel ou equivalente |
| Documentação  | OpenAPI / Swagger (via FastAPI) |

---

## 📁 Estrutura do Projeto

AmazonTechDevLab/
├── auth.py
├── notes.py
├── audit.py / audit_routes.py
├── admin_routes.py
├── models.py / schemas.py
├── security.py / db.py
├── Dockerfile
├── docker-compose.yml
├── requirements.txt
└── logs/

Módulos bem separados e nomeados, seguindo boas práticas de organização e legibilidade.

---

## ▶️ Como Rodar Localmente

```bash
git clone https://github.com/amazonroots/amazontech-devlab.git
cd amazontech-devlab
docker compose down -v --remove-orphans
docker compose up --build

✅ A API estará disponível em http://localhost:8005
➡️ Swagger / Docs: http://localhost:8005/docs
➡️ Health-check: http://localhost:8005/health

⸻

⚙️ Endpoints Principais

Rota	Método	Acesso	Descrição
/signup	POST	Público	Criar novo usuário
/login	POST	Público	Autenticar + obter token JWT
/me	GET	Authenticated	Obter dados do usuário
/notes	GET	Authenticated	Listar notas do usuário
/notes	POST	Authenticated	Criar nota
/admin/users	GET	Admin	Listar todos usuários
/admin/promote/{id}	POST	Admin	Promover usuário a admin
/audit/logs	GET	Admin	Obter logs de auditoria
/health	GET	Público	Status da API


⸻

🔐 Segurança & Auditoria
	•	Senhas armazenadas com hash seguro (pbkdf2_sha256, passagem por passlib)
	•	Uso de JWT para autenticação e autorização
	•	Dependências de rota configuradas para proteger endpoints sensíveis
	•	audit.log persistente registrando ações importantes

⸻

📆 Fluxo de Desenvolvimento & Histórico (Changelog)

Veja um resumo histórico do desenvolvimento, com datas e decisões importantes, facilitando entendimento e rastreabilidade da evolução. (Exemplo: migração de bcrypt para pbkdf2, ajustes no Docker, estrutura final, etc.)

⸻

🚀 Roadmap — Próximos Passos / Evoluções
	•	Preparar deploy em AWS EC2 / RDS / ECS ou EKS
	•	Adicionar pipeline CI/CD (tests + deploy automatizado)
	•	Expandir com testes automatizados (unit / integration)
	•	Incluir logging estruturado / monitoramento / métricas
	•	Documentar exemplos de uso e fluxo completo para usuário/admin

⸻

👤 Sobre o Autor

Rafael Rodrigues — AmazonTech
Desenvolvedor focado em backend, infraestrutura e boas práticas.
Criando ferramentas limpas, confiáveis e prontas para produção.

⸻

“Código limpo, infraestrutura pensada, documentação que fala por si.”
