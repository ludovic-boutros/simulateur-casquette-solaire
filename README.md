# Simulateur de casquette solaire

Page web autonome (un seul fichier `index.html`, sans dépendance) qui simule l'ombre portée d'une casquette au-dessus d'un vitrage en retrait dans le mur, au fil de l'année. Elle aide à choisir la profondeur de casquette qui bloque le soleil d'été tout en laissant entrer celui d'hiver.

Par défaut : Rennes, façade plein sud.

## Utilisation

Ouvrir `index.html` dans un navigateur, ou le publier avec GitHub Pages : le workflow `.github/workflows/pages.yml` déploie `index.html` à chaque push sur `main`. Il faut activer une fois Settings > Pages > Source : « GitHub Actions ». Aucune étape de build.

La recherche de ville utilise l'API de géocodage Open-Meteo (accès réseau requis) ; une liste de villes courantes fonctionne hors ligne.

## Réglages

- **Vitrage** : hauteur, largeur, retrait dans le mur.
- **Casquette** : débord hors du mur, distance au-dessus du vitrage.
- **Date et heure solaire** : pilotent la vue en coupe et le graphe de la journée.
- **Lieu** : ville, latitude, longitude, orientation de la façade (180° = sud).
- **Joues latérales** : option pour compter l'ombre portée par les côtés du retrait.
- **Boutons** : préréglages « Fenêtre 1 m » et « Baie vitrée 2,15 m », et application du débord optimal.

## Résultats affichés

- **Vue en coupe** : rayon du soleil choisi, rayons de midi aux solstices, ombre sur la vitre.
- **Tableau** : part du soleil direct qui entre, été (1er juin - 31 août) et hiver (1er déc. - 28 fév.), avec et sans casquette.
- **Débord optimal** : celui qui maximise l'écart hiver moins été.
- **Graphes** : ensoleillement sur la journée choisie, vitrage au soleil à midi sur l'année, effet du débord été contre hiver.

Les graphes affichent un tooltip au survol (ou au toucher) avec la valeur de chaque courbe.

## Modèle et limites

- Position du soleil par formules astronomiques simplifiées (déclinaison, angle horaire, équation du temps) ; heures converties en heure légale selon le fuseau de la ville.
- Soleil direct uniquement, sur un mur vertical, ciel dégagé, pondéré par l'angle d'incidence.
- Casquette plate, plus large que le vitrage, posée au-dessus du linteau.
- Pas de masques lointains (arbres, bâtiments) ni de rayonnement diffus.

