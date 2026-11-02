# Beauté intérieure — prototype

Prototype web de réalité augmentée : la caméra du téléphone filme une personne, le navigateur détecte sa posture et dessine par-dessus les os et les muscles principaux.

But : tester le calage de l'anatomie sur le corps (go/no-go du projet), pas l'application finale.

## Utilisation

Ouvrir la page publiée par GitHub Pages dans Chrome sur Android, puis toucher « Caméra en direct ».

- Os / Muscles / Les deux : calques affichés.
- Toucher une zone : nom et explication.
- Bouton en haut à droite : mesures du calage.

## Composants

- Détection de posture : [MediaPipe Pose Landmarker](https://ai.google.dev/edge/mediapipe/solutions/vision/pose_landmarker) (`@mediapipe/tasks-vision` 0.10.35, modèle `pose_landmarker_lite`), licence Apache 2.0.
- Détection de la main : [MediaPipe Hand Landmarker](https://ai.google.dev/edge/mediapipe/solutions/vision/hand_landmarker), modèle `hand_landmarker`, licence Apache 2.0. Sert à écarter une main prise pour un corps.
- Anatomie : formes 2D simplifiées calculées à partir des 33 points du corps.
- Photo d'exemple : jeu de test de MediaPipe.
