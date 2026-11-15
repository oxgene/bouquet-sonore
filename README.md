# Bouquet sonore

Une page web qui génère un bouquet de fleurs 3D dans un vase et le fait vivre avec la musique : les fleurs poussent, s'ouvrent, pulsent, puis fanent selon le rythme et l'intensité du morceau.

## Utilisation

Ouvrir `index.html` dans un navigateur récent (Chrome, Safari, Firefox), sur ordinateur ou téléphone. Tout tient dans ce seul fichier, sans dépendance.

Sources sonores :

- **Démo** : un petit morceau généré qui monte puis retombe.
- **Fichier audio** : un morceau choisi sur l'appareil.
- **Micro** : le bouquet écoute le son ambiant. Rien n'est enregistré. Le micro demande une page servie en HTTPS (GitHub Pages convient).

## Correspondance musique ↔ bouquet

| Couche du bouquet | Ce qu'elle écoute |
| --- | --- |
| Fleurs principales | Médiums (mélodie, voix) |
| Fleurs de support | Hauts médiums |
| Feuillage de garniture | Aigus |
| Feuillage d'habillage | Basses, pulsation |
| Taille de la composition | Intensité globale du morceau |

## Technique

WebGL 2 pour le rendu et Web Audio API pour l'analyse du son, sans bibliothèque externe.
