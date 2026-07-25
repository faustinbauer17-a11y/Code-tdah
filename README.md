# CODE // TDAH

Appli web (un seul fichier `index.html`, aucune dépendance externe) pour réviser
le code de la route avant le 5 août, pensée pour un cerveau TDAH.

## Ouvrir l'appli
Aucune installation : double-clique sur `index.html`, ça s'ouvre dans le
navigateur et fonctionne **hors-ligne** (rien n'est chargé depuis internet).
Pour la mettre en ligne, dépose simplement `index.html` sur n'importe quel
hébergement statique (Netlify, GitHub Pages, ton propre site...).

## Ce qui a été pensé pour le TDAH
- **Sessions courtes et chronométrées** (5 / 10 / 15 questions, ~4 à 12 min) :
  un objectif clair et atteignable plutôt qu'un quiz sans fin.
- **Une seule question à l'écran** : zéro liste, zéro scroll, zéro distraction visuelle.
- **Jauge circulaire type compteur de vitesse** : rend le temps restant visible
  d'un coup d'œil, sans avoir à lire un chiffre.
- **Pause imposable** : bouton pause avec minuteur de retour, pour éviter le
  décrochage sans jamais culpabiliser d'arrêter.
- **Gamification légère** : points, série de jours (streak), bonus "sans faute",
  visibles en permanence en haut de l'écran — la boucle de récompense reste courte.
- **Répétition espacée simplifiée** : les questions ratées reviennent plus
  souvent dans les sessions suivantes (poids proportionnel au nombre d'erreurs).
- **Rappels** : bouton 🔔 pour activer les notifications navigateur en fin de
  pause/session (fonctionne tant que l'onglet est ouvert — un vrai rappel
  quotidien nécessiterait une notification push serveur, hors scope ici).

## Contenu
`index.html` contient une banque de 51 questions originales réparties en 9
thèmes (panneaux danger, panneaux obligation/interdiction, priorités,
vitesses & distances, alcool/fatigue, sécurité & équipements, premiers
secours, éco-conduite, autoroute). Le tableau `QUESTIONS` en haut du `<script>`
est fait pour être complété facilement : chaque entrée suit le format

```js
{cat:"Nom du thème", q:"Question ?", choices:["A","B","C","D"], correct:1, exp:"Explication courte."}
```

Pour viser large avant l'examen, ajoute d'autres questions dans ce même
tableau — aucune autre partie du code n'a besoin d'être touchée.

## Données
Tout est stocké en local dans le navigateur (`localStorage`), rien n'est
envoyé nulle part. Vider le cache du navigateur réinitialise la progression.

## Prochaines étapes possibles
- Ajouter davantage de questions (viser 200+ pour bien couvrir l'examen réel).
- Ajouter un mode "erreurs uniquement".
- Déployer sur Netlify pour y accéder depuis le téléphone aussi.
