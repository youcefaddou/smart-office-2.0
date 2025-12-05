# Dossier d'Architecture Technique (DAT) — Smart Office 2.0

## 1. Contexte et objectifs
- Contexte métier, effectifs, croissance, contraintes temporelles
- Objectifs techniques et périmètre

## 2. Exigences et contraintes
- Fonctionnelles (télétravail, disponibilité)
- Non fonctionnelles (sécu, perf, coût, scalabilité)
- Contraintes budget simulé, calendrier (Déc 2025–Avr 2026, 6 séances)

## 3. Architecture réseau
- Schéma physique (core/distribution/access, WAN primaire/backup, DMZ)
- Schéma logique (VLANs, sous-réseaux, routage, QoS)
- Plan d'adressage IPv4/IPv6, DHCP, DNS
- Wi-Fi (SSID, segmentation, sécurité)
- Flux réseau clés (app, DB, admin)

## 4. Sécurité
- Segmentation (VLANs, DMZ), ACLs, pare-feu (règles)
- Accès distants (VPN + MFA), NAC / Zero Trust (posture, identité)
- Bastion / Jump host, gestion des comptes et secrets
- Journalisation, SIEM, alerting

## 5. Infrastructure Cloud & Systèmes
- Choix cloud (comparatif + TCO), modèle hybride
- Services déployés (IaaS/PaaS), réseau cloud (VNet/VPC, peering/VPN)
- Images, durcissement, patch management

## 6. Stockage et Bases de Données
- Besoins (fichiers, sauvegardes, logs), choix SAN/NAS/Objet
- Modèle de données (app POC), DB (SQL/NoSQL), HA/backup/restore
- Sécurité DB (comptes, chiffrement, audit)

## 7. DevOps, Containerisation et CI/CD
- Docker/compose, registre (GHCR), pipeline CI (build/test/push)
- Déploiement cloud (K8s ou service managé / VM), IaC (Terraform)
- Runbooks de déploiement

## 8. Supervision, Logs et Détection
- Stack (ELK/Graylog, Grafana/Prometheus)
- Sources (FW, app, système), tableaux de bord, alertes
- Scénario d'anomalie simulée

## 9. PCA / PRA et ITSM
- BIA, RTO/RPO par service
- Scénarios (panne FAI, cyberattaque, panne serveur)
- Procédures PRA/PCA, tests, rôles
- Processus incidents (ticketing, escalade, SLA)

## 10. Gestion de projet et traçabilité
- Méthodo (Scrum/Kanban), sprints, jalons
- Backlog, board, PRs/branches
- Journal de décisions

## 11. Budget/TCO (simulé)
- Estimation POC mensuelle cloud
- Comparatif On-Prem vs Cloud (3 ans)

## 12. Annexes
- Glossaire, liste des versions/outils
- Captures maquette (EVE-NG/GNS3), exports Terraform
- Checklists (sécurité, déploiement, PRA)
