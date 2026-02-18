# **Cahier des charges — Projet Smart Office 2.0**



##### Contexte et identification

##### Titre du projet : Smart Office 2.0

##### Formation / UF : Bachelor 3 — INFRA (Ynov Informatique)

##### Groupe : Youcef ADDOU, Kévin Scherrer, Alexandre Coulaud

##### Période : Décembre 2025 - Avril 2026



Objectif général : Concevoir, maquetter, documenter et déployer l’infrastructure IT complète, sécurisée et résiliente d’un siège social (4 étages) pour une startup en hyper‑croissance (50 → 200+ employés en 18 mois) avec politique de télétravail flexible.



1\. Périmètre fonctionnel et technique (Ce qui doit être livré)

Livrables obligatoires :

\- Dossier d’Architecture Technique (DAT) comprenant :

\- Schémas d’architecture physique et logique (LAN, WLAN, WAN, DMZ, flux applicatifs).

\- Plan d’adressage IP complet et politique VLAN.

\- Justification des choix matériels, logiciels et fournisseurs Cloud (comparatif et TCO).

\- Politiques de sécurité :

\- Règles de pare‑feu, ACLs, segmentation (VLANs, DMZ), micro‑segmentation.

\- Gestion des identités et des accès (IAM), MFA, NAC / principes Zero Trust.

\- Politique de sauvegarde et chiffrement des données.

\- PCA / PRA :

\- Analyse d’impact (BIA), identification des risques, RTO / RPO.

\- Procédures de reprise (scénarios : panne FAI, cyberattaque, panne serveur).

\- Processus de gestion des incidents (ITSM : ticketing, SLA, escalade).

\- Maquette fonctionnelle (POC) :

\- Environnement réseau virtualisé (EVE‑NG ou GNS3) démontrant segmentation et routage.

\- Déploiement d’un service containerisé (ex : outil de réservation de salles) sur un Cloud (IaaS/PaaS).

\- Tableau de bord de collecte de logs et démonstration de détection d’une anomalie simulée.

\- Dossier de gestion de projet :

\- Backlog priorisé, planification des sprints, board de suivi (Trello/Jira).

\- Preuves de versioning (Git/GitHub) : branches, commits, PRs.

\- Présentation orale :

\- Démo pour l’oral intermédiaire (10 min) axée sur compétences transverses.

\- Présentation finale technique et démonstration du POC.

Exclusions (hors périmètre) :

\- Achat réel de matériel en production (sauf maquette virtuelle et justification budgétaire).

\- Déploiement complet en production multi‑site hors siège.



2\. Exigences détaillées et critères techniques

Architecture réseau

\- LAN/WLAN : conception multi‑étages, segmentation par VLANs (administration, R\&D, production, invités, IoT), redondance des switches cœur et distribution.

\- WAN : lien principal + lien de secours (basculement), QoS pour voix/visioconférence.

\- Plan d’adressage : schéma IPv4 (et IPv6 si pertinent), sous‑réseaux par VLAN, réservation DHCP, documentation des plages.

\- Maquette : implémentation dans EVE‑NG/GNS3 avec routage inter‑VLAN et ACLs.

Sécurité

\- Segmentation : VLANs + DMZ pour services exposés (reverse proxy, VPN gateway).

\- Zero Trust / NAC : authentification des postes, contrôle d’accès basé sur identité et posture.

\- Accès distants : VPN sécurisé + MFA ; justification du choix (SSL VPN / SASE / ZTNA).

\- Pare‑feu \& IDS/IPS : règles documentées, journalisation centralisée.

\- Supervision \& SIEM : collecte de logs (ELK/Graylog), dashboard (Grafana), alerting et scénario de détection simulée.

Cloud \& DevOps

\- Architecture hybride : évaluer On‑Premise vs IaaS/PaaS/SaaS ; proposer solution hybride justifiée par TCO.

\- Fournisseur Cloud : comparaison AWS / Azure / GCP ; choix motivé (coûts, services, compatibilité).

\- Containerisation : Docker + orchestration (Kubernetes ou service managé) pour l’application de réservation.

\- CI/CD : pipelines basiques pour build et déploiement (GitHub Actions / GitLab CI).

\- Infrastructure as Code : templates Terraform/ARM/CloudFormation pour le POC.

Stockage et bases de données

\- Stratégie stockage : choix entre SAN/NAS/Objet selon besoins (fichiers partagés, sauvegardes, logs).

\- Bases de données : modèle relationnel pour données structurées (SQL) ; NoSQL si besoin pour logs/telemetry.

\- Sécurité DB : gestion des accès, chiffrement, protection contre injections, sauvegarde/restauration testée.

Continuité et reprise

\- BIA : identification des services critiques, impacts métiers, priorités de restauration.

\- PCA/PRA : procédures, rôles, checklists, tests de restauration (sauvegarde complète et incrémentale).

\- RTO/RPO : chiffrés pour chaque service critique.

Gestion de projet et compétences transverses

\- Méthodologie : Agile (Scrum/Kanban) — sprints 1–2 semaines, DoD, revues et rétrospectives.

\- Outils : Git/GitHub, Trello/Jira, Notion/Markdown pour documentation, Teams/Slack pour communication.

\- Documentation : DAT, procédures opérationnelles, guides d’exploitation et runbooks.



3\. Organisation de l’équipe et responsabilités

Rôles et responsabilités (assignés) :

\- Youcef ADDOU — Chef de projet / Scrum Master

\- Backlog, planning, relation encadrant, préparation oraux, gestion des livrables.

\- Kévin Scherrer — Ingénieur Réseau \& Sécurité

\- Conception LAN/WLAN/WAN, VLANs, pare‑feu, NAC, maquette EVE‑NG, tests de sécurité.

\- Alexandre Coulaud — Ingénieur Cloud \& DevOps

\- Étude Cloud/TCO, déploiement POC containerisé, CI/CD, IaC, monitoring.

Règles de collaboration :

\- Versioning : chaque livrable a une branche dédiée ; PR obligatoire pour fusion ; conventions de commit.

\- Réunions : daily stand‑up 15 min (ou 3x/semaine), revue de sprint, rétrospective.

\- Propriétaire de livrable : chaque livrable a un responsable principal et un second référent.



4\. Planning, jalons et sprints (exemple sur 10 semaines)

Sprint 0 (Semaine 0) — Préparation

\- Mise en place repo Git, board Trello/Jira, environnement EVE‑NG, charte projet.

Sprint 1 (S1) — Cadrage \& DAT initial

\- Schémas initiaux, plan d’adressage, backlog détaillé.

Sprint 2 (S2) — Maquette réseau

\- Implémentation EVE‑NG : VLANs, routage, ACLs.

Sprint 3 (S3) — Sécurité \& monitoring

\- Déploiement SIEM/ELK, règles pare‑feu, tests d’alerting.

Sprint 4 (S4) — Cloud POC

\- Containerisation de l’app, déploiement IaaS/PaaS, pipeline CI/CD.

Sprint 5 (S5) — Stockage \& DB

\- Choix stockage, déploiement DB, sauvegardes.

Sprint 6 (S6) — PCA/PRA \& tests

\- BIA, RTO/RPO, tests de restauration, simulations d’incidents.

Sprint 7 (S7) — Finalisation DAT \& documentation

\- Rédaction DAT final, politiques sécurité, runbooks.

Sprint 8 (S8) — Préparation oraux

\- Préparation démo 10 min (oral intermédiaire), slides, répétitions.

Jalons clés :

\- Oral intermédiaire (10 min) : démonstration compétences transverses (Git, gestion projet, présentation).

\- POC réseau fonctionnel : S2/S3.

\- POC service cloud : S4.

\- Livrables finaux remis : fin S8/S9.



5\. Critères d’acceptation et évaluation

Critères techniques (doivent être vérifiables) :

\- DAT complet et cohérent avec schémas et plan d’adressage.

\- Maquette EVE‑NG démontrant segmentation et routage inter‑VLAN.

\- Service containerisé déployé sur Cloud choisi et accessible selon règles de sécurité.

\- Tableau de bord montrant collecte de logs et détection d’une anomalie simulée.

\- PCA/PRA avec BIA, RTO/RPO et procédures testées.

\- Backlog, sprints et preuves de gestion Agile (tickets, revues).

\- Repositories Git avec historique, branches et PRs.

Alignement avec grille d’évaluation transverses :

\- Git \& GitHub (pondération 3) : preuves de versioning, PRs, README, workflows.

\- Gestion projet (pondération 4) : backlog, planning sprint, board actif.

\- Rédaction spécifications (pondération 5) : DAT et spécifications fonctionnelles/techniques.

\- Présentation orale (pondération 5) : clarté, structure, démonstration POC.

\- Posture professionnelle (pondération 3) : respect des délais, autonomie, qualité des livrables.



6\. Contraintes, risques et budget

Contraintes :

\- Temps limité (calendrier universitaire) ; effectif 3 personnes.

\- Budget simulé : toutes les dépenses Cloud et licences doivent être justifiées et optimisées.

\- Environnement de test uniquement (pas de production réelle).

Principaux risques \& mesures d’atténuation :

\- Retard sur POC Cloud → prioriser containerisation locale et IaC réutilisable.

\- Problème de sécurité non détecté → tests d’intrusion basiques et revue par pair.

\- Perte de données de maquette → sauvegardes régulières du repo et snapshots.

Budget \& TCO :

\- Fournir estimation coûts Cloud pour POC (mensuel) et comparaison On‑Premise vs Cloud (TCO sur 3 ans).

\- Justifier choix économique et technique dans DAT.



7\. Outils, standards et livrables formatés

Outils recommandés :

\- Versioning \& CI : Git, GitHub, GitHub Actions.

\- Maquette réseau : EVE‑NG ou GNS3.

\- Monitoring / SIEM : ELK stack, Grafana, Prometheus.

\- IaC : Terraform (ou équivalent).

\- Gestion projet : Trello/Jira, Notion pour documentation.

\- Communication : Teams / Slack.

Formats de livrables :

\- DAT en Markdown/Notion + PDF export.

\- Scripts et IaC dans repo Git.

\- Présentations en PDF/Slides (export), démo live pour oraux.

\- Runbooks et procédures en Markdown.



8\. Critères de réussite et remise

Critères de réussite :

\- Tous les livrables listés remis et validés.

\- POC réseau et service cloud fonctionnels et démontrés.

\- PCA/PRA documenté et tests de restauration réalisés.

\- Preuves de gestion Agile et versioning disponibles.

Remise finale :

\- Dépôt Git public/privé (avec accès jury), DAT final, PCA/PRA, maquette exportée, slides oraux.



Annexes (à produire)

\- Glossaire des acronymes.

\- Liste du matériel virtuel utilisé et versions.

\- Journal de bord des décisions (choix technologiques et justifications).

\- Tableaux comparatifs Cloud (coûts, services, avantages).





Youcef ADDOU — Chef de projet

Kévin Scherrer —  Cloud \& DevOps

Alexandre Coulaud — Réseau \& Sécurité

Date : 05/12/2025

