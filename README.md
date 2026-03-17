# Odoo Quality Management System
Odoo addon for ISO 9001 Quality Management System. This is a simplified and customized version based on some models used in the management system modules by Odoo Community Association available at https://github.com/OCA/management-system/.

## Outils de pilotage pour un SaaS comme Dailybiz

Si vous avez besoin d'outils de pilotage dans Dailybiz, ce module couvre déjà les briques clés d'un pilotage QMS:

- **Objectifs qualité (`qms.goal`)** pour fixer des cibles par processus et suivre l'avancement.
- **Indicateurs (`qms.indicator`)** et **mesures d'indicateurs (`qms.indicator.measurement`)** pour monitorer la performance dans le temps.
- **Mesures d'objectifs (`qms.goal.measurement`)** pour comparer le réel vs la cible.
- **Audits (`qms.audit`)**, **constats (`qms.finding`)** et **non-conformités (`qms.non.conformity`)** pour le pilotage de la conformité.
- **Actions (`qms.action`)** avec des étapes de traitement pour suivre les plans d'actions correctifs/préventifs.
- **Revues de direction (`qms.review`)** pour centraliser les décisions de pilotage.

### Mise en place recommandée (rapide)

1. Définir les processus (`qms.process`) et les responsables.
2. Créer 5 à 10 KPI prioritaires dans `qms.indicator` (qualité, délais, satisfaction, incidents).
3. Associer des objectifs mesurables dans `qms.goal` avec une fréquence de mesure.
4. Mettre en place une revue mensuelle avec suivi des actions ouvertes.
5. Utiliser les audits et non-conformités pour alimenter l'amélioration continue.

## License

This program is free software: you can redistribute it and/or modify it under the terms of the GNU Affero General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License along with this program. If not, see http://www.gnu.org/licenses/.
