# Bouquet sonore

Une page web qui génère un bouquet de fleurs 3D dans un vase et le fait vivre avec la musique : les fleurs poussent, s'ouvrent, pulsent, puis fanent selon le rythme et l'intensité du morceau.

## Utilisation

Ouvrir `index.html` dans un navigateur récent (Chrome, Safari, Firefox), sur ordinateur ou téléphone. Tout tient dans ce seul fichier, sans dépendance.

Sources sonores :

- **Démo** : un petit morceau généré qui monte puis retombe.
- **Fichier audio** : un morceau choisi sur l'appareil.
- **Micro** : le bouquet écoute le son ambiant. Rien n'est enregistré. Le micro demande une page servie en HTTPS (GitHub Pages convient).

## Comment le bouquet écoute

L'écoute se fait en trois temps, séparés dans le code :

1. **Mesure** : le son est découpé en 24 bandes réparties comme l'oreille, en décibels, à pas fixe (indépendant de la fluidité de l'affichage).
2. **Perception** : trois dimensions en sont tirées.
   - *Intensité* : le niveau comparé à sa moyenne récente (contraste) et à une échelle absolue (force).
   - *Activité* : la densité d'attaques, détectées par flux spectral avec un seuil qui suit la médiane récente, dans les graves, les médiums et les aigus.
   - *Pulsation* : régularité des attaques sur 8 secondes, avec un tempo estimé et une confiance.
3. **Comportement** : ces valeurs pilotent le bouquet.

| Ce qui pilote | Effet sur le bouquet |
| --- | --- |
| Intensité + activité | Taille de la composition (ce qui pousse ou fane) |
| Médiums et leurs attaques | Ouverture des fleurs principales |
| Hauts médiums | Fleurs de support |
| Aigus | Frémissement du feuillage de garniture |
| Basses et leurs attaques | Balancement du feuillage d'habillage, temps forts |

Le panneau « Ce que le bouquet entend » affiche ces mesures en direct, avec un historique de 20 secondes. Le moteur d'origine reste disponible (« Ancien ») pour comparer.

## Technique

WebGL 2 pour le rendu et Web Audio API pour l'analyse du son, sans bibliothèque externe.
