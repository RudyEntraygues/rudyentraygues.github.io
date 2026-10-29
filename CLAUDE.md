# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Présentation

L'objectif est de créer un site internet de type portfolio, accessible sur internet.

C'est le mien : je m'appelle Rudy, je suis en BTS SIO et je prépare mon épreuve de fin de BTS. Je veux aussi apprendre comment fonctionne un site internet.

- Option du BTS : SISR
- Mon niveau actuel en HTML / CSS / JavaScript : débutant — adapte tes explications à ce niveau.

## Rôle de Claude

- Tu dois toujours expliquer avant d'agir, me proposer un plan et attendre que je le valide.
- Tu travailles par petites étapes (une étape = un fichier ou une fonctionnalité), sauf quand je te demande explicitement de faire plusieurs choses.
- Si tu as un doute, pose-moi des questions.
- Si tu ne sais pas, dis « je ne sais pas » et n'essaie pas de deviner.

## Technologies

- HTML
- CSS
- JavaScript
- Le site sera statique et sans dépendance (pas de npm, pas de framework, pas de bibliothèque externe).
- Il sera hébergé sur **GitHub Pages**. URL visée : rudyentraygues.github.io

## Exigences de qualité

- Le site doit être responsive (mobile et ordinateur).
- Le site doit être accessible (textes alternatifs sur les images, contrastes suffisants, titres hiérarchisés).
- Le site doit fonctionner sur les navigateurs récents (Chrome, Firefox, Edge).

## Conventions

- Le contenu et les commentaires doivent être en français.
- Les noms de fichiers et de dossiers sont toujours en minuscules, avec des tirets '-' et jamais d'espace.
  - Exceptions : `CLAUDE.md`, `README.md`, et `index.html` (obligatoire pour la page d'accueil sur GitHub Pages).
- Structure des dossiers :
  - `css/` pour les feuilles de style
  - `js/` pour les scripts
  - `images/` pour les images
  - `docs/` pour la documentation

## Règles de sécurité

- Tu n'as jamais le droit de supprimer un fichier ou un dossier. Si une suppression est nécessaire, tu me l'indiques et c'est moi qui la fais.
- Tu dois me demander avant de modifier, créer, déplacer ou renommer un fichier ou un dossier.
- Tu dois me demander avant d'installer quoi que ce soit (logiciel, extension, paquet) et avant d'exécuter un programme ou un script.
- Tu ne dois jamais utiliser `git commit`, `git push`, `git add`, `git reset --hard`, `git checkout -- …`, `git clean`, `git rebase`, `git restore`, `git stash` ou `git switch`.
- Seules les commandes Git en lecture sont autorisées (`git status`, `git diff`, `git log`).
- Ne lis, n'écris et n'envoie jamais de secret (mot de passe, clé, token). Si une tâche en nécessite un, arrête-toi et propose-moi une solution.
- Un site statique ne peut rien cacher : aucun secret ne doit se trouver dans le HTML, le CSS ou le JavaScript.
- Aucune donnée personnelle sensible sur le site (adresse, numéro de téléphone…). Un formulaire de contact ne peut pas fonctionner seul sur un site statique : il faudrait un service externe, à me proposer avant de l'utiliser.

## Méthode

- Quand tu effectues un travail, fais-moi un résumé de ce que tu as fait en m'expliquant point par point.
- Vérifie toujours ton travail avant de me le rendre : erreurs, bugs, incohérences, bugs graphiques.
- Pour vérifier l'affichage, ouvre le site dans Chrome et fais des captures d'écran en largeur mobile et en largeur ordinateur.
- Tu peux me proposer un message de commit en adoptant la convention « Conventional Commits »

## Documentation

Tu tiens une documentation de chaque étape dans `docs/journal.md`, rédigée sous forme de résumés pour qu'elle soit lisible par un humain. Chaque entrée contient :

- la date ;
- l'objectif de l'étape ;
- ce qui a été fait ;
- les décisions prises et pourquoi ;
- ce que j'ai appris.
