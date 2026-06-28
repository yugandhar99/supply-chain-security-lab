# Container Supply Chain Security Lab

> **Stage 10 of 12 — Career Progression Project**  
> Portfolio project by **Yugandhar Ethamukkala**.

Local and CI-based DevSecOps lab for container image scanning, SBOM generation, and image signing concepts using Trivy, Syft, Cosign, Docker, and GitHub Actions.

## Career Progression Story

DevSecOps step: I added supply-chain security practices like image scanning, SBOM generation, and image signing concepts.

This repo is part of my 12-project DevOps portfolio path. The goal is to show steady growth from CI/CD foundations into AWS cloud, Kubernetes, GitOps, observability, DevSecOps, progressive delivery, and AI-enabled deployments.

## What This Project Demonstrates

- Modern DevSecOps project that recruiters will recognize.
- Low-cost and easy to run locally.
- Good for explaining SBOM, vulnerability gates, image signing, and CI security controls.

## Tech Stack

`Docker` `Trivy` `Syft` `SBOM` `Cosign` `GitHub Actions` `Node.js` `DevSecOps`

## Architecture

```mermaid
flowchart LR
  Code[App Source] --> Build[Docker Build]
  Build --> Trivy[Trivy Scan]
  Build --> Syft[SBOM Generation]
  Build --> Cosign[Image Signing]
  Trivy --> Gate[Security Gate]
  Syft --> Artifacts[Security Artifacts]
  Cosign --> Registry[Trusted Image Registry]
```

## Repository Structure

```text
.
├── Makefile
├── README.md
├── REPO_UPLOAD_CHECKLIST.md
├── app/
├── docs/
├── project.yaml
├── scripts/
```

## Prerequisites

- Git
- Docker where containers are used
- Cloud CLI/tools only when deploying cloud resources
- `kubectl`, `kind`, `terraform`, `sam`, `maven`, `npm`, or `python` depending on the project
- Never commit real `.env` files, API keys, access keys, kubeconfigs, private keys, or tokens

## Local Run

```bash
make up
curl http://localhost:8080/health
make scan
```

## GitHub Actions Note

The security workflow is configured as manual only using `workflow_dispatch`, so it will not run automatically on every push. Run it manually from the Actions tab after the repo is uploaded.

## Validation Before GitHub Upload

Run these checks before pushing major changes:

```bash
make validate
```

## Deployment Overview

1. Run local syntax validation.
2. Build the demo container image.
3. Run Trivy vulnerability scanning.
4. Generate SBOM output with Syft and optionally sign images with Cosign.

## Screenshots to Add

This project did not include ready project snapshots in the uploaded folder, so I prepared a screenshot folder for you.

Add these after you run the project:

- `docs/screenshots/local-container-running.png`
- `docs/screenshots/trivy-scan-output.png`
- `docs/screenshots/sbom-generated.png`
- `docs/screenshots/github-actions-security-success.png`
- `docs/screenshots/docker-cleanup-proof.png`

Do not add screenshots with account IDs, IP addresses, tokens, billing pages, or private URLs.

## Cleanup / Cost Control

Run cleanup commands after testing so cloud resources do not keep charging:

```bash
make down
docker image rm supply-chain-demo:local || true
rm -f sbom.spdx.json trivy-report.json || true
```

## Security Notes

- Use GitHub Actions OIDC, Jenkins credentials, AWS Secrets Manager, Vault, or Kubernetes Secrets instead of hard-coded keys.
- Keep `.env` files local and commit only `.env.example` with safe placeholders.
- Review Terraform plans before apply/destroy.
- Do not publish account IDs, private IPs, public IPs from your lab, billing pages, or credential screenshots.

## How I Would Explain This in an Interview

I built this project as part of my DevOps portfolio to show hands-on experience with the tools used in real delivery environments. The focus is not only on writing code, but also on creating a repeatable workflow for build, validation, deployment, security, monitoring, and cleanup.

In a real project, I would connect this type of setup with environment-specific variables, approval gates, secrets management, monitoring dashboards, and rollback steps so teams can release safely and troubleshoot faster.

---

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0F2027,50:2C5364,100:00C9FF&height=120&section=footer&text=Let's%20Connect&fontColor=ffffff&fontSize=32&fontAlignY=70" />
</p>

<h2 align="center">🤝 Connect With Me</h2>

<p align="center">
  <em>
    Thanks for visiting this project! I’m continuously building hands-on DevOps, Cloud, Automation, and AI-enabled engineering projects to improve real-world deployment, monitoring, and infrastructure skills.
  </em>
</p>

<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=22&duration=2500&pause=800&color=00C9FF&center=true&vCenter=true&width=650&lines=DevOps+%7C+Cloud+%7C+Automation;CI%2FCD+%7C+Docker+%7C+Kubernetes+%7C+Terraform;Building+real-world+projects+one+commit+at+a+time" alt="Typing SVG" />
</p>

<p align="center">
  <a href="https://github.com/yugandhar99" target="_blank" rel="noopener noreferrer">
    <img src="https://img.shields.io/badge/GitHub-Follow-181717?style=flat&logo=github&logoColor=white" alt="GitHub" />
  </a>
  <a href="https://www.linkedin.com/in/yugandhar-devops" target="_blank" rel="noopener noreferrer">
    <img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat&logo=linkedin&logoColor=white" alt="LinkedIn" />
  </a>
  <a href="https://yugandhar-portfolio-psi.vercel.app/" target="_blank" rel="noopener noreferrer">
    <img src="https://img.shields.io/badge/Portfolio-View%20My%20Work-FF5722?style=flat&logo=vercel&logoColor=white" alt="Portfolio" />
  </a>
  <a href="mailto:yugandharethamukkala1999@gmail.com">
    <img src="https://img.shields.io/badge/Email-Contact%20Me-D14836?style=flat&logo=gmail&logoColor=white" alt="Email" />
  </a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Focus-DevOps%20Engineering-blue?style=flat-square" />
  <img src="https://img.shields.io/badge/Cloud-AWS%20%7C%20Azure%20%7C%20GCP-orange?style=flat-square" />
  <img src="https://img.shields.io/badge/IaC-Terraform-purple?style=flat-square" />
  <img src="https://img.shields.io/badge/Containers-Docker%20%7C%20Kubernetes-2496ED?style=flat-square" />
</p>

---

<p align="center">
  ⭐ If this project added value, feel free to star the repository and connect with me!
</p>

<p align="center">
  <strong>Built with ❤️ using modern DevOps practices</strong>
</p>

