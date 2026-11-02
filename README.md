# Mon bloc de force

Application web de suivi de powerlifting (force athlétique), pensée pour un usage sur téléphone. Elle permet de planifier des blocs d'entraînement de 4 semaines, de suivre ses records et de se situer par rapport aux niveaux de la Fédération Française de Force (FFForce).

Projet personnel, non affilié à la FFForce.

## Fonctionnalités

**Accueil**
- Niveau FFForce du total (départemental, R3, R2, R1, N2, N1, Europe, Monde), avec la progression vers le niveau suivant et les kilos manquants.
- Réglages : poids de corps (la catégorie de poids se déduit toute seule), sexe, Training Max.
- Courbe de progression du total.

**Bloc force**
- Tes 1RM de squat, bench et deadlift, avec un niveau indicatif de E à SSS par mouvement.
- Un bloc de 4 semaines (3 semaines de montée, 1 semaine de décharge), du lundi au vendredi.
- Charges calculées à partir du Training Max, arrondies à 2,5 kg, avec échauffement proposé.
- Séries à cocher, et chrono de repos en plein écran qui démarre à chaque série cochée.
- Notation de chaque séance lourde (Facile, Bien, Dur, Limite), utilisée pour calculer le bloc suivant.
- Accessoires entièrement modifiables (nom, séries, reps, muscle travaillé).
- Préparation du bloc suivant : nouveau 1RM estimé, ajustement du nombre de séries, et choix du type de bloc (Volume, Force, Force lourde, Pic de forme) avec une recommandation selon le bloc précédent.

**Calculatrice**
- Calculateur de disques : quels disques mettre de chaque côté de la barre, avec option colliers de compétition.
- Calculateur de PR : estimation du 1RM (formule d'Epley) à partir d'une série, tableau des pourcentages, historique des PR.

**Stats**
- Séances terminées, séries, répétitions, volume soulevé.
- Ressenti des séances et séries par groupe musculaire.

**Records**
- Historique par mouvement : 1RM estimé ou charge la plus lourde, sur 1, 3, 6 mois ou tout l'historique.

## Installer l'application sur iPhone

1. Ouvre l'adresse du site dans **Safari**.
2. Appuie sur le bouton Partager, puis sur « Sur l'écran d'accueil ».
3. Appuie sur « Ajouter ».

L'application s'ouvre ensuite comme une app, sans barre d'adresse, et fonctionne hors ligne une fois chargée une première fois.

## Données et confidentialité

- Toutes tes données (1RM, séances, records, réglages) sont enregistrées **uniquement dans le navigateur de ton appareil** (stockage local). Rien n'est envoyé à un serveur.
- Les données ne sont donc pas synchronisées entre appareils.
- Vider les données de Safari ou supprimer l'app de l'écran d'accueil peut effacer tes données. Pense à noter tes records ailleurs.
- Le code ne contient que des valeurs de départ neutres. Les valeurs à saisir au premier lancement sont tes propres 1RM et ton poids de corps.

## Les niveaux FFForce

Les seuils proviennent du tableau officiel « Niveaux Force Athlétique » de la FFForce, mis à jour le 13 novembre 2025, pour les hommes (catégories Junior, Senior/Open et Masters 1 à 4).

- La FFForce annonce que les niveaux N1 et N2 Senior/Open seront ajustés après les qualifications 2026, et que les niveaux sont revus régulièrement. Les valeurs de l'application peuvent donc devenir obsolètes : vérifie toujours sur le site officiel de la FFForce.
- Les niveaux concernent le total en force athlétique (sans équipement). Les niveaux E à SSS affichés par mouvement sont un barème indicatif créé pour cette application, et non un classement officiel.
- Le niveau de l'application se base sur la somme de tes 1RM saisis. Un total validé en compétition, sous arbitrage, peut être plus bas que celui réalisé à l'entraînement.

## Structure du projet

| Fichier | Rôle |
| --- | --- |
| `index.html` | Toute l'application (page, styles et code), sans dépendance externe hormis les polices Google Fonts |
| `manifest.webmanifest` | Informations d'installation (nom, icônes, mode plein écran) |
| `sw.js` | Service worker : fonctionnement hors ligne et mises en cache |
| `apple-touch-icon.png` | Icône de l'écran d'accueil iPhone |
| `icon-192.png`, `icon-512.png` | Icônes de l'application |

## Publication avec GitHub Pages

1. Place tous les fichiers à la racine du dépôt.
2. Dans Settings, puis Pages, choisis « Deploy from a branch », la branche `main` et le dossier `/ (root)`.
3. Le site est disponible à l'adresse `https://<pseudo>.github.io/<nom-du-depot>/`.

Avec un compte GitHub gratuit, le dépôt et le site sont publics.

## Mettre à jour l'application

- Remplace `index.html` dans le dépôt : l'application se met à jour à la connexion suivante.
- Si tu modifies les icônes ou le manifeste, change aussi le numéro de version `V` au début de `sw.js` (par exemple `bloc-force-v2`) pour forcer le rafraîchissement du cache.

## Limites connues

- Le bip du chrono peut ne pas se déclencher si l'écran est verrouillé ou si l'application passe en arrière-plan. La vibration n'est pas disponible sur iPhone dans un navigateur.
- Pas de sauvegarde ni d'export des données pour le moment.
- Seuls les tableaux de niveaux hommes sont intégrés.
