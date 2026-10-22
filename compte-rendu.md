# Compte rendu — Quiz en images

**Étudiant ou binôme :** à compléter  
**Thème :** les formes géométriques

## Présentation

L’application « Formes en tête » est un quiz responsive en une seule page, réalisé avec Vue 3 et la Composition API. Elle présente cinq questions illustrées, trois choix de réponse par question, le score courant et une barre de progression.

L’interface utilise les éléments HTML `header`, `main`, `section`, `img`, `button` et `progress`. Les images ont un texte alternatif. Les styles distinguent visuellement une bonne réponse d’une mauvaise, tandis qu’un message explicite donne également le résultat.

## Questions et images

Les cinq questions sont déclarées dans le tableau statique `questions` de `src/quiz/App.vue`. Chaque objet contient le texte, le chemin local de l’illustration, trois choix, l’indice de la bonne réponse et le texte alternatif. Les images SVG sont placées dans `public/images` et référencées par des chemins `/images/...`.

## Réactivité et déroulement

Les états `indexQuestion`, `score`, `reponseChoisie` et `termine` sont réactifs grâce à `ref`. Les valeurs dérivées — question courante, nombre de réponses, dernière question et exactitude de la réponse — utilisent `computed`.

La liste des choix est générée avec `v-for` et une clé stable. `:src` et `:alt` associent l’illustration à la question courante. `@click` valide un choix ; une garde dans `repondre` empêche de compter deux fois une question et les trois boutons sont désactivés après le choix. Une bonne réponse ajoute un point, une mauvaise réponse n’en ajoute pas, mais chacune fait avancer la progression.

La balise `progress` reçoit le nombre de réponses données et le nombre total de questions. Après chaque réponse, le bouton de navigation permet d’avancer. Après la cinquième réponse, « Voir le résultat » affiche le score final dans le même composant. « Rejouer le quiz » réinitialise le score, la progression et la question courante.

## Vérifications réalisées

- `npm run build` : vérification des types et compilation de production réussies.
- Réponse correcte à la première question : score à 1/5 et progression à 1/5 ; les trois choix sont désactivés.
- Réponse incorrecte à la deuxième question : score inchangé à 1/5, progression avancée à 2/5 et correction affichée.
- Réponses aux questions restantes : le score final affiché est de 4/5.
- Redémarrage : retour à la première question, score à 0/5 et progression à 0/5.
- Vérification à une largeur mobile de 390 px : les trois choix restent visibles et accessibles.
