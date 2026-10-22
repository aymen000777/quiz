# Compte rendu — Quiz en images

**Étudiant ou binôme :** à compléter  
**Thème :** les formes géométriques

## Présentation

« Formes en tête » est un quiz Vue 3 en une page qui présente cinq questions illustrées, trois choix par question, un score et une barre de progression. L’interface utilise notamment `header`, `main`, `section`, `img`, `button` et `progress`. Chaque image a un texte alternatif ; la correction est affichée avec un message, et pas seulement par sa couleur.

## Questions et images

Le tableau statique `questions` de `App.vue` contient cinq objets. Chaque objet définit le texte de la question, le chemin de l’image locale, les trois choix, l’indice de la bonne réponse et le texte alternatif. Les cinq images SVG se trouvent dans `public/images`.

## Réactivité et déroulement

`ref` gère `indexQuestion`, `score`, `reponseChoisie` et `termine` ; `computed` fournit la question courante, la progression et l’état de la réponse. `v-for` avec `:key` affiche les choix ; `:src` et `:alt` affichent l’image. Le clic appelle `repondre`. Une garde évite le double comptage et les choix sont désactivés après la validation. Une bonne réponse ajoute un point ; toute réponse avance la progression. Il faut répondre avant de poursuivre. Après cinq réponses, « Voir le résultat » affiche le score final ; « Rejouer » remet la partie à zéro.

## Vérifications

- `npm run build` : vérification des types et compilation réussies.
- Bonne réponse : score +1, progression +1 et trois boutons désactivés.
- Mauvaise réponse : score inchangé, progression +1 et bonne réponse indiquée.
- Partie terminée : résultat 4/5 ; redémarrage : score et progression reviennent à zéro.
- À 390 px de largeur, les trois choix restent accessibles.
