
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
> Acessível globalmente — sem localhost. Deploy real, 24/7.

---

## 📷 Swagger em Produção

<p align="center">
  <img src="Imagem 09-12-2025 às 02.18.png" width="100%" alt="Swagger AmazonTech DevLab"/>
</p>

---

## 🧭 Sobre o Projeto

O **AmazonTech DevLab** é meu laboratório real de **Cloud + Backend + DevOps**, criado para aprender infraestrutura **na marra**, resolvendo erro real, debug real e deploy real.

Aqui construí a jornada completa:

**Código → Containers → Banco persistente → Deploy na AWS → Proxy Nginx → Elastic IP → CI/CD → API global.**

Este repositório é **meu case oficial** para portfólio Cloud/DevOps.

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
| Observabilidade | (Em construção) |
| CI/CD | GitHub Actions → SSH → Appleboy → Deploy Automático |

---

## 🛠 Rodando Local

```bash
git clone https://github.com/amazonroots/amazontech-devlab.git
cd amazontech-devlab
docker-compose up --build


⸻

📘 HISTÓRICO TÉCNICO REAL (DIÁRIO OFICIAL DO PROJETO)

Toda a evolução do DevLab, registrada como aconteceu:
erro → diagnóstico → correção → avanço real.

⸻

🗓 07/12/2025 — Backend pronto localmente
	•	CRUD Notes funcional
	•	JWT Auth configurado
	•	Docker + PostgreSQL rodando estável
	•	Estrutura sólida do microserviço

⸻

🗓 08/12/2025 — Deploy completo na AWS EC2

Infra criada do zero:
	•	EC2 Ubuntu 24.04 LTS
	•	Docker + Docker Compose instalados
	•	API rodando via container
	•	PostgreSQL persistente
	•	Porta 8005 liberada no SG
	•	Testes concluídos com sucesso
	•	API disponível publicamente

curl http://3.235.187.206:8005/health


⸻

🗓 09/12/2025 — Estabilização de produção

Elastic IP configurado

Agora o servidor não perde mais IP após reboot.
IP fixo:

100.26.73.245

Proxy reverso configurado (Nginx)

Porta 80 → Porta 8005
Infra pronta para HTTPS (Certbot).

Segurança ajustada
	•	Porta 80 liberada
	•	Porta 22 restringida
	•	API funcional via http://IP/docs

⸻

🗓 10/12/2025 — CI/CD PROFISSIONAL implantado

Este foi o dia em que o AmazonTech DevLab virou profissional de verdade.

✔ Pipeline cd.yml criado

GitHub Actions agora:
	1.	Conecta via SSH na EC2
	2.	Reseta o repositório para o origin/main
	3.	Rebuilda os containers
	4.	Sobe a versão nova automaticamente

✔ Secrets configurados
	•	EC2_HOST
	•	EC2_USER
	•	EC2_KEY (chave corrigida manualmente no macOS)

✔ Problemas resolvidos

Primeiras execuções falharam por causa de uma chave privada mal formatada.
Diagnóstico feito → Chave corrigida no nano → Permissão chmod 600 aplicada → Segredo revalidado.

✔ Resultado final

🟢 CD Pipeline #6 — SUCCESS

Agora, sempre que quiser fazer deploy:

📌 Clica em Run Workflow → EC2 atualiza sozinha.

⸻

🗺 Roadmap
	•	✔ CI/CD finalizado
	•	✔ Proxy Nginx
	•	✔ Elastic IP
	•	✔ Deploy completo
	•	⏳ HTTPS + Certbot
	•	⏳ Observabilidade (Prometheus/Grafana/Loki)
	•	⏳ RDS
	•	⏳ Terraform + Kubernetes

⸻

🔥 Por que este projeto é valioso no meu portfólio?

✔ É Cloud real, com servidor real
✔ Tem deploy real, não simulado
✔ Usa Docker + PostgreSQL
✔ Possui CI/CD funcional
✔ Tem proxy reverso configurado
✔ É replicável para empresas
✔ Mostra maturidade DevOps
✔ É o tipo de entrega que empresa vê e respeita

Cloud não é teoria.
Cloud é resolver problemas até ficar verde.

⸻

👤 Autor

Rafael Rodrigues – AmazonTech
📩 rafael.amazontech@gmail.com
Backend | Cloud | DevOps

