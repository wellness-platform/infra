# 🏗️ Infrastructure as Code (IaC) – Git Strategy & Practices

This repository contains all infrastructure code: EKS, IAM, VPC, Vault, Jenkins, GitHub OIDC, etc.

---

## 🧬 Git Structure

- Terraform modules
- Helm charts
- Cluster bootstrap scripts (for EKS Anywhere on VMware)
- GitHub Actions workflows

---

## 🚀 Branch Strategy

- `main`: Applied to production
- `dev`: Optional staging env
- `feature/*`: Infra updates
- `vault/*`, `eks/*`, `network/*`: Optional by scope

---

## ✅ CI/CD

- Terraform validate → plan → apply (manual or GitOps)
- Helm template/lint → upgrade
- GitHub Actions → Terraform Cloud / Self-Hosted Runner

---

## 🔐 Secrets

- Managed outside this repo (Vault / AWS Secrets Manager)
- Use of `terraform-provider-vault` or `aws_secretsmanager_secret`

---

## 🌐 GitOps

- Consider separate `cluster-config` repo for Argo
- Store Helm release state & kustomize overlays there

---

## 📘 Docs

- [`docs/eks-anywhere.md`](docs/eks-anywhere.md)
- [`docs/oidc.md`](docs/oidc.md)
- [`docs/vault-setup.md`](docs/vault-setup.md)
