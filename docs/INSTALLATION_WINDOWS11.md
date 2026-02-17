# Mode opératoire — Installation d'un SMQ ISO 9001 (Odoo + module QMS) sous Windows 11

Ce guide permet de déployer une application web complète pour piloter votre Système de Management de la Qualité (SMQ) ISO 9001 avec Odoo 14 et le module `qms` de ce dépôt.

## 1) Prérequis

- **Windows 11** à jour
- **Docker Desktop** (avec Docker Compose V2)
- **Git for Windows**

### Vérifications rapides

Dans PowerShell :

```powershell
docker --version
docker compose version
git --version
```

## 2) Récupérer le projet

```powershell
cd C:\
git clone <URL_DU_DEPOT> odoo-qms-iso9001
cd .\odoo-qms-iso9001
```

## 3) Préparer la configuration

```powershell
Copy-Item .env.example .env
```

Vous pouvez modifier `.env` si vous souhaitez changer le port ou les identifiants PostgreSQL.

## 4) Démarrer l'application web

```powershell
docker compose up -d
```

Vérifier l'état :

```powershell
docker compose ps
```

Ouvrez ensuite :

- **http://localhost:8069** (ou votre port personnalisé)

## 5) Initialiser la base et installer le module QMS

1. À la première ouverture, créez votre base de données Odoo.
2. Activez le **mode développeur** dans Odoo.
3. Allez dans **Apps**.
4. Mettez à jour la liste des applications.
5. Recherchez **Quality Management System**.
6. Installez le module.

## 6) Structurer votre SMQ ISO 9001 (mode opératoire métier)

Après installation, implémentez votre SMQ selon l'ordre recommandé :

1. **Contexte & stratégie qualité**
   - Politique qualité
   - Parties intéressées
   - Processus
2. **Planification**
   - Objectifs qualité
   - Indicateurs et mesures
   - Ressources
3. **Maîtrise documentaire**
   - Procédures
   - Instructions
   - Enregistrements
   - Versions des documents
4. **Maîtrise opérationnelle & amélioration**
   - Non-conformités
   - Actions correctives / préventives
   - Opportunités
   - Réclamations
   - Observations
5. **Évaluation des performances**
   - Audits
   - Revues de direction
   - Évaluations d'audits

## 7) Exploitation quotidienne (routine recommandée)

- **Chaque semaine** : suivi des non-conformités, actions et indicateurs.
- **Chaque mois** : revue des objectifs, efficacité des actions, statut documentaire.
- **Chaque trimestre** : audit interne et plan d'amélioration.
- **Chaque année** : revue de direction complète et mise à jour de la politique qualité.

## 8) Sauvegarde et restauration

### Sauvegarder la base PostgreSQL

```powershell
docker exec -t odoo_qms_db pg_dump -U odoo postgres > .\backup_qms.sql
```

### Restaurer la base PostgreSQL

```powershell
Get-Content .\backup_qms.sql | docker exec -i odoo_qms_db psql -U odoo -d postgres
```

## 9) Maintenance

### Mettre à jour l'application

```powershell
git pull
docker compose pull
docker compose up -d
```

### Voir les logs

```powershell
docker compose logs -f web
docker compose logs -f db
```

## 10) Arrêt / redémarrage

```powershell
docker compose stop
docker compose start
```

Pour supprimer les conteneurs (sans supprimer les volumes) :

```powershell
docker compose down
```

## 11) Dépannage rapide

- Si le port 8069 est occupé, modifiez `ODOO_PORT` dans `.env`.
- Si le module n'apparaît pas, mettez à jour la liste des applications et vérifiez les logs `web`.
- Si Odoo ne démarre pas, vérifiez que le service `db` est healthy.

---

Ce mode opératoire couvre le déploiement technique et la trame de pilotage ISO 9001. Vous pouvez ensuite adapter les formulaires, workflows et droits d'accès à votre organisation.
