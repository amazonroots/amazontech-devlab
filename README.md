
<p align="center">
  <img src="da348e15a643411f3e3d6eb8be4613bff71d1e8cd1398ef2d6527de13467c096.png" width="100%"/>
</p>

<h1 align="center">☁️ AmazonTech DevLab</h1>
<h3 align="center">Backend rodando em produção real na AWS · FastAPI · Docker · PostgreSQL · JWT · Nginx · CI/CD Pipeline</h3>

<p align="center">
  <img src="https://img.shields.io/badge/Status-Online-success?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/AWS-Cloud-orange?style=for-the-badge&logo=amazonaws"/>
  <img src="https://img.shields.io/badge/FastAPI-Backend-00ffc8?style=for-the-badge&logo=fastapi"/>
  <img src="https://img.shields.io/badge/Docker-Containers-blue?style=for-the-badge&logo=docker"/>
  <img src="https://img.shields.io/badge/PostgreSQL-Database-0277bd?style=for-the-badge&logo=postgresql"/>
  <img src="https://img.shields.io/badge/JWT-Auth-critical?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/CI%2FCD-GitHub%20Actions-blueviolet?style=for-the-badge&logo=githubactions"/>
</p>

---

### 🔗 API em Produção  
📍 **http://100.26.73.245:8005/docs**  
> Acessível globalmente — deploy real, 24/7.

---

## 📷 Swagger em Produção

<p align="center">
  <img src="Imagem 09-12-2025 às 02.18.png" width="100%" alt="Swagger AmazonTech DevLab"/>
</p>

---

## 🧭 Sobre o Projeto

O **AmazonTech DevLab** é meu laboratório real de **Cloud + Backend + DevOps**, criado para aprender infraestrutura **na prática**, lidando com erros reais, diagnósticos reais e deploy real.

Aqui construí toda a jornada:

**Código → Containers → Banco persistente → Deploy na AWS → Proxy Nginx → Elastic IP → CI/CD → API global.**

Este é meu **case oficial** para portfólio Cloud/DevOps.

---

## ⚙ Stack Técnica

| Item | Tecnologia |
|---|---|
| Linguagem | Python 3.11 |
| Framework | FastAPI |
| DB | PostgreSQL (Docker Volume persistente) |
| Infra | Docker + Docker Compose |
| Cloud | AWS EC2 Linux |
| Rede | Elastic IP + Security Groups |
| Proxy | Nginx (porta 80 → 8005) |
| Auth | JWT Token |
| CI/CD | GitHub Actions + SSH + Appleboy |
| Observabilidade | (Em construção) |

---

## 🛠 Rodando Local

```bash
git clone https://github.com/amazonroots/amazontech-devlab.git
cd amazontech-devlab
docker-compose up --build


⸻

📘 HISTÓRICO TÉCNICO REAL (DIÁRIO OFICIAL)

Toda a evolução: erro → diagnóstico → correção → sucesso real.

⸻

🗓 07/12/2025 — Backend local estável
	•	CRUD Notes ✔
	•	JWT Auth ✔
	•	Docker + PostgreSQL ✔
	•	Estrutura sólida

⸻

🗓 08/12/2025 — Deploy completo na AWS EC2

Infra criada do zero:
	•	EC2 Ubuntu 24.04
	•	Docker + Compose instalados
	•	API rodando em container
	•	DB persistente
	•	Porta 8005 liberada

Health:

curl http://3.235.187.206:8005/health


⸻

🗓 09/12/2025 — Estabilização de produção

Elastic IP configurado

Agora o servidor não perde mais IP:

100.26.73.245

Nginx configurado

Reverse proxy:
	•	Porta 80 → 8005
	•	Infra pronta para HTTPS

Security Group ajustado.

⸻

🗓 10/12/2025 — CI/CD profissional implantado

Esse foi o dia em que o DevLab virou projeto profissional de verdade.

✔ Pipeline GitHub Actions (cd.yml) criado

Agora o GitHub:
	1.	Conecta via SSH na EC2
	2.	Atualiza o repo
	3.	Rebuilda os containers
	4.	Sobe nova versão automaticamente

✔ Secrets configurados
	•	EC2_HOST
	•	EC2_USER
	•	EC2_KEY (RSA corrigida no nano + chmod 600)

✔ Problema resolvido: chave privada inválida
	•	Diagnóstico: erros ssh.ParsePrivateKey
	•	Solução: limpeza manual, permissão corrigida
	•	Secrets revalidados

✔ Resultado final:

🟢 CD Pipeline #6 — SUCCESS

📌 Agora Run Workflow = Deploy automático.

⸻

🗺 Roadmap
	•	✔ CI/CD GitHub Actions
	•	✔ Proxy Nginx
	•	✔ Elastic IP
	•	✔ Deploy completo
	•	⏳ HTTPS + Certbot
	•	⏳ Observabilidade (Prometheus/Grafana/Loki)
	•	⏳ RDS
	•	⏳ Terraform/K8s

⸻

🔥 Por que este projeto é valioso no meu portfólio?

✔ Cloud real (AWS)
✔ Deploy real, não simulado
✔ Pipeline CI/CD funcional
✔ Proxy reverso configurado
✔ Banco persistente
✔ API pública documentada
✔ Padrão de engenharia profissional

Cloud não se aprende lendo.
Cloud se aprende deployando.

⸻

👤 Autor

Rafael Rodrigues – AmazonTech
📩 rafael.amazontech@gmail.com
🔗 LinkedIn: https://www.linkedin.com/in/rafael-rodrigues-916258399

Backend | Cloud | DevOps
