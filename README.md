# Quiz en images — Formes en tête

Quiz responsive réalisé avec Vue 3 et la Composition API. Il propose cinq questions illustrées sur les formes géométriques, trois réponses par question, un score et une barre de progression.

## Installation et lancement

```sh
npm install
npm run dev
```

Pour vérifier les types et construire le projet :

```sh
npm run build
```

## Règles du quiz

- Une bonne réponse ajoute exactement un point ; une mauvaise réponse ne modifie pas le score.
- Chaque réponse fait avancer la progression, quelle que soit sa justesse.
- Les choix sont désactivés après une réponse ; il faut répondre avant de passer à la question suivante.
- Après la cinquième question, le résultat final s’affiche. « Rejouer le quiz » remet le score et la progression à zéro.

Le composant Vue est `App.vue`, son entrée est `main.ts` et les styles sont dans `quiz.css` et `base.css`. Les cinq illustrations SVG locales sont dans `public/images`. Les captures d’écran et le compte rendu sont aussi inclus dans le dépôt.
