
# DevOps Mastery — Dashboard

**Goal:** Land a Cloud/DevOps Engineer role as fast as possible
**Timeline:** 7-day intensive bootcamp ✅ → Interview prep ongoing
**Server:** bumblebee (192.168.1.18) | devops-labs (192.168.56.101)
**GitHub:** https://github.com/aakash-1004

---

## Progress Overview

| #   | Module                          | Status     | Lab Completed                   |     |
| --- | ------------------------------- | ---------- | ------------------------------- | --- |
| 01  | [[Bash-Strict-Mode.md]]         | ✅ Done     | [[Health-Check-Script.md]]      |     |
| 02  | [[Subprocess.md]]               | ✅ Done     | [[Python-DevOps-Scripts.md]]    |     |
| 03  | [[Git-Workflow.md]]             | ✅ Done     | taskmanager repo on GitHub      |     |
| 04  | [[Docker-Core-Concepts.md]]     | ✅ Done     | [[Taskmanager-Docker.md]]       |     |
| 05  | [[Kubernetes-Core-Concepts.md]] | ✅ Done     | [[Kubernetes-Manifests-Lab.md]] |     |
| 06  | [[AWS-Core-Services.md]]        | ✅ Done     | [[EC2-Deployment-Lab.md]]       |     |
| 07  | [[GitHub-Actions.md]]           | ✅ Done     | [[Taskmanager-CICD-Lab.md]]     |     |
| 08  | [[Terraform-Core-Concepts.md]]  | ✅ Done     | [[Terraform-AWS-Lab.md]]        |     |
| 09  | [[Prometheus-Grafana.md]]       | ✅ Done     | [[Monitoring-Lab.md]]           |     |
| 10  | System Design                   | 🔲 Pending | —                               |     |
| 11  | Interview Prep                  | 🔲 Pending | —                               |     |

---

## The Golden Thread Project

**Taskmanager REST API** — Flask + MongoDB

| Stage | Status | Details |
|-------|--------|---------|
| Built locally | ✅ | Flask + MongoDB, full CRUD |
| Dockerized | ✅ | Dockerfile + Docker Compose |
| Kubernetes | ✅ | 2 replicas, NodePort :30000 |
| AWS EC2 | ✅ | Deployed via Docker Compose |
| Terraform | ✅ | Full infra as code |
| CI/CD | ✅ | GitHub Actions → Docker Hub |
| Monitoring | ✅ | /metrics → Prometheus → Grafana |

**Repo:** https://github.com/aakash-1004/taskmanager
**Docker Hub:** https://hub.docker.com/r/aakash0908/taskmanager

---

## End-to-End Pipeline

```
git push → GitHub Actions → pytest → docker build → Docker Hub → K8s → Prometheus → Grafana
```

---

## Repos

| Repo | Visibility | Stack |
|------|-----------|-------|
| [taskmanager](https://github.com/aakash-1004/taskmanager) | Public | Python, Docker, K8s, GitHub Actions |
| [terraform-aws](https://github.com/aakash-1004/terraform-aws) | Private | Terraform, AWS, HCL |

---

## Interview Prep Status

| Topic | Confidence | Notes |
|-------|-----------|-------|
| Bash scripting | 🟡 Medium | Review trap, lock files, awk |
| Docker | 🟢 Good | Layers, compose, networking |
| Kubernetes | 🟡 Medium | Review RBAC, Helm, HPA |
| AWS | 🟡 Medium | Review EKS, Lambda, RDS |
| Terraform | 🟡 Medium | Review modules, remote state |
| CI/CD | 🟢 Good | GitHub Actions pipeline done |
| Monitoring | 🟡 Medium | Review PromQL alerting rules |
| System Design | 🔴 Not started | Next focus |

---

## Key Commands — Quick Reference

```bash
# Start minikube
minikube start

# Port-forward Grafana
kubectl port-forward -n monitoring svc/prometheus-grafana 3000:80 --address=0.0.0.0 &

# Port-forward Prometheus
kubectl port-forward -n monitoring svc/prometheus-kube-prometheus-prometheus 9090:9090 --address=0.0.0.0 &

# Scale up monitoring
kubectl scale deployment prometheus-grafana --replicas=1 -n monitoring
kubectl scale deployment prometheus-kube-prometheus-operator --replicas=1 -n monitoring
kubectl scale deployment prometheus-kube-state-metrics --replicas=1 -n monitoring
kubectl scale statefulset alertmanager-prometheus-kube-prometheus-alertmanager --replicas=1 -n monitoring
kubectl scale statefulset prometheus-prometheus-kube-prometheus-prometheus --replicas=1 -n monitoring

# Run taskmanager locally
cd ~/aakash/devops/taskmanager
source venv/bin/activate
docker compose up -d
python3 app.py

# AWS CLI check
aws sts get-caller-identity

# Terraform
cd ~/aakash/devops/bootcamp/terraform-aws
terraform init && terraform plan
```

---

## Next Steps

- [ ] System Design — scalability, reliability, cloud-native patterns
- [ ] Interview prep — scenario-based Q&A
- [ ] Resume update with project descriptions
- [ ] LinkedIn optimization
- [ ] Mock interviews

---

## Notes Index

### 01 — Linux & Bash
- [[Bash-Strict-Mode.md]]
- [[Logging-Trap-Lock-Files.md]]
- [[Log-parsing.md]]
- [[Cron-Jobs.md]]
- [[Health-Check-Script.md]]

### 02 — Python DevOps
- [[Subprocess.md]]
- [[JSON-YAML-Parsing.md]]
- [[Requests.md]]
- [[Python-DevOps-Scripts.md]]
- [[Flask-MongoDB-API.md]]

### 03 — Git
- [[Git-Workflow.md]]

### 04 — Docker
- [[Docker-Core-Concepts.md]]
- [[Docker-Compose.md]]
- [[Taskmanager-Docker.md]]

### 05 — Kubernetes
- [[Kubernetes-Core-Concepts.md]]
- [[Kubernetes-Core-Concepts.md]]

### 06 — AWS
- [[AWS-Core-Services.md]]
- [[EC2-Deployment-Lab.md]]

### 07 — CI/CD
- [[GitHub-Actions.md]]
- [[Taskmanager-CICD-Lab.md]]

### 08 — Terraform
- [[Terraform-Core-Concepts.md]]
- [[Terraform-AWS-Lab.md]]

### 09 — Monitoring
- [[Prometheus-Grafana.md]]
- [[Monitoring-Lab.md]]