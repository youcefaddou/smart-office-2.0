# Smart Office 2.0 — Infra/Cloud/DevOps (B3 INFRA)

## Équipe
- Youcef ADDOU — Chef de projet
- Kévin Scherrer — Cloud & DevOps
- Alexandre Coulaud — Réseau & Sécurité

## Périmètre
- Conception, maquette, documentation et déploiement d’une infra siège (4 étages) pour une startup (50 → 200+ employés, télétravail).
- Livrables : DAT, politiques de sécu (PF/ACL/VLAN/DMZ, VPN+MFA/NAC), POC réseau (EVE-NG/GNS3), POC app containerisée sur cloud (CI/CD, IaC), PCA/PRA + ITSM, monitoring/SIEM.

## Planning (6 séances de 3h, Déc 2025 – Avr 2026)
- S1 : repo/board, DAT squelette, plan IP v1, choix cloud/app POC, env lab.
- S2 : maquette réseau (VLAN, inter-VLAN, ACL de base), Docker/compose, CI (build/push).
- S3 : sécu & logs (PF/ACL affinées, VPN/MFA, SIEM/logs design), déploiement POC cloud.
- S4 : IaC Terraform, CI/CD déploiement cloud, tests sécu maquette.
- S5 : DB/stockage, backup/restore test, BIA + RTO/RPO, PCA/PRA procédures.
- S6 : finalisation livrables, runbooks, démo oraux.

## Structure attendue
- `/docs/DAT.md` : Dossier d’Architecture Technique (squelette + contenu).
- `/docs/decisions.md` : journal de décisions (choix techno, coûts, sécu).
- `/infra/` : maquette réseau (fichiers EVE-NG/GNS3 si exportables).
- `/app/` : code app POC + Dockerfile + docker-compose.
- `/iac/` : Terraform (réseau, compute, DB, registry…).
- `.github/workflows/ci.yml` : pipeline CI build/push image (GHCR).
- `runbooks/` : PCA/PRA, ITSM, procédures d’incident, checklists.

## Conventions Git
- Branches par livrable/feature : `feature/<nom>`, `doc/<nom>`.
- PR obligatoires, relecture croisée.
- Commits : prefix type (feat|fix|doc|chore|infra|sec|ci).

## Quickstart (local)
```bash
git clone https://github.com/youcefaddou/smart-office-2.0.git
cd app
docker compose up --build
```

## CI/CD
- CI : build/push image vers GHCR.
- CD (POC) : déploiement cloud (service managé ou VM+compose) déclenché sur branche main.

## Suivi projet
- Board Jira (tickets importés, étiquettes session-1…6).
- Preuves : PRs, issues, captures maquette, logs/alertes, tests backup/restore, RTO/RPO.
