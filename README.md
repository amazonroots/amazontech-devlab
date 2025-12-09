🏴‍☠️ AmazonTech DevLab — Backend em Produção (EC2 • Docker • FastAPI)

Projeto real publicado na AWS Free Tier.
Autenticação JWT • Notes API • Admin & Auditoria • Postgres persistente • Deploy com Docker Compose.
Zero simulação. Código rodando globalmente.

📌 Swagger Público:
🔗 http://3.235.187.206:8005/docs

⸻

🧩 Sobre o Projeto

AmazonTech DevLab é meu laboratório pessoal de backend & cloud, construído para prática profissional com foco em:

✔ FastAPI bem estruturado
✔ Auth com JWT
✔ Banco PostgreSQL rodando em container
✔ Deploy real em EC2 (Free Tier)
✔ Auditoria, admin, criação de notas
✔ Acesso público via IP externo
✔ Infra dockerizada e replicável

Não é app básico. É servidor rodando na nuvem.

⸻

⚙️ Stack Técnica

Componente	Uso
FastAPI	API principal
PostgreSQL	Banco de dados
Docker + Compose	Containers isolados
JWT Auth	Login / tokens / security
AWS EC2 Ubuntu	Hosting
Nginx Reverse Proxy	Porta 80 → API 8005
UFW + SG	Segurança e portas abertas
SwaggerUI	Docs públicas


⸻

🏗 Arquitetura Final em Produção

                 🌎 Internet
                      │
              ┌───────▼───────┐
              │    NGINX      │  Porta 80
              └───────┬───────┘
                      │ proxy_pass
                      ▼
            http://127.0.0.1:8005
         ┌─────────────────────────┐
         │      FastAPI + JWT      │
         │  Docker container API   │
         └───────────┬────────────┘
                     │ network
                     ▼
              PostgreSQL (5432)


⸻

📜 Histórico Técnico — (Tudo que foi feito)

🔥 Dia 1 – Estrutura, Docker e API
	•	Projeto montado com FastAPI
	•	Autenticação JWT construída
	•	CRUD Notes implementado
	•	Área admin com flag is_admin
	•	Auditoria e logs básicos
	•	Docker + docker-compose configurado
	•	Banco Postgres persistente
	•	Testes locais OK

🔥 Dia 2 – Upload para GitHub + Deploy AWS EC2
	•	Repositório criado + README inicial
	•	Push da base dockerizada para GitHub
	•	Instância EC2 t2.micro criada (Free Tier)
	•	Chave SSH amazontech-key.pem
	•	Security Groups com portas abertas:
	•	22 (SSH)
	•	8005 (API pública)
	•	Docker e Compose instalados no servidor
	•	docker compose up --build -d rodando containers
	•	Acesso externo validado via celular/browser

🔥 Dia 3 – Infra melhoria + Reverse Proxy + Porta 80
	•	Instalação e configuração do NGINX
	•	Criação de backup default.bak
	•	Criação do reverse proxy:

sudo tee /etc/nginx/sites-available/default > /dev/null << 'EOF'
server {
    listen 80 default_server;
    listen [::]:80 default_server;
    server_name _;
    location / {
        proxy_pass http://127.0.0.1:8005;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
EOF

	•	ufw allow 80/tcp liberado
	•	SG atualizado com porta 80 aberta
	•	nginx -t e reload bem sucedidos
	•	API funcionando via porta 80 (+ 8005 ativo)

Resultado final hoje:

✔ API funcionando globalmente
✔ Porta 80 liberada
✔ Reverse Proxy ativo
✔ Servidor pronto para HTTPS futuramente
✔ Infra estável sem custos (Free Tier)

⸻

Como rodar local

git clone https://github.com/amazonroots/amazontech-devlab
cd amazontech-devlab
docker compose up --build

Docs → http://localhost:8000/docs

⸻

Como atualizar README com commit change

git add README.md
git commit -m "docs: README completo + histórico técnico + arquitetura + deploy nginx reverse proxy"
git push origin main


⸻

Roadmap
	•	🔐 HTTPS com Certbot (quando apontar domínio)
	•	🗃 Backup/Postgres snapshot automático
	•	🚀 CI/CD GitHub Actions → deploy push-to-prod
	•	🛰 RDS no futuro
	•	📊 Monitoramento: Grafana + Loki
	•	🖥 Dashboard Admin React/Vue
	•	🐳 Possível migração para ECS/EKS

⸻

Autor

Rafael Rodrigues (Chinaman — nome artístico)
Cloud • DevOps • Backend
📧 rafael.amazontech@gmail.com



Qual vai ser?
