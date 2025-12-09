
<p align="center">
  <img src="da348e15a643411f3e3d6eb8be4613bff71d1e8cd1398ef2d6527de13467c096.png" width="100%"/>
</p>

<h1 align="center">☁️ AmazonTech DevLab</h1>
<h3 align="center">Backend rodando em produção real na AWS · FastAPI · Docker · PostgreSQL · JWT · Nginx</h3>

<p align="center">
  <img src="https://img.shields.io/badge/Status-Online-success?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/AWS-Cloud-orange?style=for-the-badge&logo=amazonaws"/>
  <img src="https://img.shields.io/badge/FastAPI-Backend-00ffc8?style=for-the-badge&logo=fastapi"/>
  <img src="https://img.shields.io/badge/Docker-Containers-blue?style=for-the-badge&logo=docker"/>
  <img src="https://img.shields.io/badge/PostgreSQL-Database-0277bd?style=for-the-badge&logo=postgresql"/>
  <img src="https://img.shields.io/badge/JWT-Auth-critical?style=for-the-badge"/>
</p>

---

### 🔗 API em Produção  
📍 http://100.26.73.245:8005/docs  
> Acessível globalmente — sem localhost

---

## 📷 Swagger em Produção

<p align="center">
  <img src="Imagem 09-12-2025 às 02.18.png" width="100%" alt="Swagger AmazonTech DevLab"/>
</p>

---

## 🧭 Sobre o Projeto

O **AmazonTech DevLab** é meu laboratório real de **Cloud + Backend + DevOps**, criado para aprender **infraestrutura fazendo — não só lendo.**  
Aqui construí a jornada completa:

**Código → Containers → Banco persistente → Deploy na AWS → Proxy → API disponível no mundo todo.**

É meu **case oficial para portfólio cloud** e o primeiro alicerce para projetos maiores como **Sentinel-21**.

---

## ⚙ Stack Técnica

| Item | Tecnologia |
|---|---|
| Linguagem | Python 3.11 |
| Framework | FastAPI |
| DB | PostgreSQL (persistente via Docker Volume) |
| Infra | Docker + Docker Compose |
| Cloud | AWS EC2 Linux |
| Rede | Elastic IP + Security Groups |
| Proxy | Nginx reverse (porta 80 → 8005) |
| Auth | JWT Token |
| Deploy | Produção real na AWS |

---

## 🛠 Rodando Local

``bash
git clone https://github.com/amazonroots/amazontech-devlab.git
cd amazontech-devlab
docker-compose up --build


⸻

📊 Histórico Técnico (Diário real)

Data	Evento
07/12/2025	Backend funcional local + JWT + CRUD Notes + Docker + PostgreSQL
08/12/2025	Deploy AWS EC2 • Security Group • Docker Compose • API Pública • Testes
09/12/2025	Elastic IP atualizado • Correção SSH timeout • docker ps validado • README atualizado com prints

Nada de teoria — deploy real, com erros, correção e aprendizado prático.

⸻

🗺 Roadmap
	•	Domínio + HTTPS (Certbot)
	•	CI/CD (GitHub Actions)
	•	Observabilidade (Prometheus/Grafana/Loki)
	•	Migração para RDS
	•	Escalonamento ECS/EKS

⸻

🔥 Por que isso é valioso no meu portfólio?

✔ Cloud real (AWS EC2)
✔ Deploy completo feito à mão
✔ Banco persistente, nada de “localzinho”
✔ API pública que QUALQUER UM pode acessar
✔ Base perfeita para CI/CD + escalabilidade

Cloud não se aprende lendo. Se aprende deployando.

⸻

👤 Autor

Rafael Rodrigues — AmazonTech
📩 rafael.amazontech@gmail.com
Backend | Cloud | DevOps
