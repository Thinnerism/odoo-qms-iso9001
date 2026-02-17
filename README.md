# Odoo Quality Management System (ISO 9001)

Application web basée sur Odoo pour gérer et piloter un Système de Management de la Qualité (SMQ) ISO 9001.

## Contenu

- Addon Odoo `qms` (modèles, vues, données de base)
- Stack Docker Compose (Odoo 14 + PostgreSQL)
- Guide d'installation et d'exploitation sous Windows 11

## Démarrage rapide

```bash
cp .env.example .env
docker compose up -d
```

Puis ouvrez `http://localhost:8069`, créez votre base et installez l'application **Quality Management System**.

## Documentation

- Mode opératoire complet Windows 11 : [`docs/INSTALLATION_WINDOWS11.md`](docs/INSTALLATION_WINDOWS11.md)

## License

This program is free software: you can redistribute it and/or modify it under the terms of the GNU Affero General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License along with this program. If not, see http://www.gnu.org/licenses/.
