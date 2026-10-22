# Apex Sprint, moteur d'analyse vidéo (prototype)

Page web unique (`index.html`). Aucun serveur, aucune base de données : la vidéo est analysée dans le navigateur de l'utilisateur et n'est envoyée nulle part.

## Mettre en ligne avec GitHub et Render

1. Sur github.com : **New repository**, nom `apex-sprint-video`. Puis **Add file > Upload files**, dépose `index.html`, `render.yaml` et `README.md`, puis **Commit changes**.
2. Sur render.com : **New > Static Site**, connecte ton compte GitHub et choisis le dépôt `apex-sprint-video`.
3. Réglages : *Build Command* vide (ou `echo ok`), *Publish Directory* `.` (si Render refuse le point, mets `./`). Clique sur **Create Static Site**.
4. Render te donne un lien du type `https://apex-sprint-video.onrender.com`. Ouvre-le dans Chrome, sur téléphone ou ordinateur.

## Utilisation

1. Attends « Modèle prêt » (le modèle précis fait environ 30 Mo : prévoir quelques secondes, internet obligatoire).
2. Choisis une vidéo de sprint filmée de profil, caméra fixe, athlète entier visible sur au moins 5 à 6 pas.
3. Renseigne la taille de l'athlète et la phase de la course (accélération, vitesse maximale, fin de course).
4. Laisse « Ralenti » sur détection automatique. Clique sur **Analyser**.
5. Utilise le curseur et la lecture au ralenti pour vérifier que le squelette suit bien le corps.
6. Exporte les mesures (JSON) pour les comparer à l'avis d'un entraîneur.

## Nouveautés de la version 2

- Stabilisation d'un léger mouvement de caméra (activée par défaut).
- Corrections écrites directement sur la vidéo : segments verts ou rouges, angles, messages (« Pied loin du bassin : 31 cm »), bouton « Prochain défaut », enregistrement d'une image annotée.
- Si la caméra est trop instable pour repérer les appuis au sol, l'outil les repère avec la position du pied par rapport au bassin. Dans ce cas, contact, vol, longueur de pas et vitesse ne sont pas mesurés.

## Conseils de tournage

- Trépied à hauteur de hanche, 10 à 15 m de la piste, caméra perpendiculaire à la course, sans la bouger.
- 120 images par seconde ou plus pour des temps de contact fiables.
- Vêtements ajustés, fond simple, bonne lumière.

## Limites connues

- Analyse en 2D : les mesures supposent une caméra de profil et fixe.
- Les seuils (cibles) sont des valeurs de départ à faire valider par un entraîneur.
- Outil d'aide à l'entraînement, pas un diagnostic médical.
