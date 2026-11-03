# Journal de bord du projet

Ce journal retrace chaque étape de la création de mon portfolio : ce qui a été fait, les décisions prises et ce que j'ai appris.

---

## Étape 1 : création du fichier `CLAUDE.md`

**Date :** 29/10/2026

**Objectif :** donner à Claude Code un fichier d'instructions propre au projet.

**Ce qui a été fait :**

- Lancement de la commande `/init`, qui analyse le dossier et crée un fichier `CLAUDE.md`.
- Le dépôt était encore vide (seulement un `.gitignore`), donc le fichier généré était très court.
- J'ai ensuite réécrit `CLAUDE.md` moi-même avec mes propres règles : objectif du projet, rôle de Claude, technologies, conventions, sécurité, méthode et documentation.

**Décisions :**

- Site statique en HTML, CSS et JavaScript, sans dépendance, hébergé sur GitHub Pages.
- Claude doit expliquer avant d'agir, proposer un plan et attendre ma validation.

**Ce que j'ai appris :**

- `CLAUDE.md` est lu par Claude Code au début de chaque session : c'est la « fiche de consignes » du projet.

---

## Étape 2 : critique de `.gitignore` et `CLAUDE.md`

**Date :** 29/10/2026

**Objectif :** faire relire mes deux fichiers par Claude, sans qu'il les modifie.

**Ce qui a été fait :**

- Relecture du `.gitignore` : il protégeait bien `.env` et les fichiers système Windows, mais ne protégeait plus le fichier de réglages personnels de Claude Code.
- Relecture de `CLAUDE.md` : fautes d'orthographe, listes non formatées en Markdown, règles Git incomplètes, phrase sur les secrets ambiguë, informations manquantes (niveau, option, URL, exigences de qualité).

**Décisions :**

- Aucune modification à cette étape, seulement une liste de points à corriger.

**Ce que j'ai appris :**

- En Markdown, des lignes qui se suivent sans tiret `-` sont fusionnées en un seul paragraphe à l'affichage.
- Un site statique ne peut rien cacher : tout le HTML, le CSS et le JavaScript est visible par n'importe qui.
- Certaines commandes Git (`reset --hard`, `clean`, `checkout --`) peuvent effacer du travail.

---

## Étape 3 : correction de `.gitignore` et `CLAUDE.md`

**Date :** 29/10/2026

**Objectif :** appliquer les corrections proposées à l'étape 2.

**Ce qui a été fait :**

- `.gitignore` : ajout de `.claude/settings.local.json`, `.vscode/`, `*.log` et `.DS_Store`, avec des commentaires par catégorie.
- `CLAUDE.md` : correction des fautes, mise en listes à puces, ajout d'une section « Exigences de qualité » (responsive, accessibilité, navigateurs), de la structure des dossiers, des règles sur les données personnelles et du format du journal.
- J'ai ensuite complété moi-même les informations manquantes : option **SISR**, niveau **débutant**, URL **rudyentraygues.github.io**.

**Décisions :**

- Convention de nommage : minuscules et **tirets `-`** (plutôt que des tirets bas), comme c'est l'usage sur le web.
- Exceptions à la convention : `CLAUDE.md`, `README.md` et `index.html`.

**Ce que j'ai appris :**

- GitHub Pages a besoin d'un fichier `index.html` comme page d'accueil.
- Le nom du dépôt GitHub détermine l'adresse du site.

---

## Étape 4 : test de la capture d'écran dans Chrome

**Date :** 29/10/2026

**Objectif :** vérifier que Claude peut ouvrir une page web, en faire une capture et l'analyser, pour pouvoir vérifier l'affichage du site plus tard.

**Ce qui a été fait :**

- Ouverture de `https://example.com` dans un nouvel onglet Chrome grâce à l'extension Claude, capture d'écran, analyse, puis fermeture de l'onglet.
- L'analyse a relevé la mise en page (colonne centrée), la hiérarchie du texte et un contraste un peu faible du texte gris sur fond sombre.

**Décisions :**

- Les vérifications d'affichage du portfolio se feront de cette façon, en largeur mobile et en largeur ordinateur.

**Ce que j'ai appris :**

- Pour ouvrir un fichier local (`file:///…`), il faudra peut-être activer « Autoriser l'accès aux URL de fichier » dans l'extension.
- Le contraste entre le texte et le fond est un critère d'accessibilité.

---

## Étape 5 : création de `.claude/settings.json`

**Date :** 29/10/2026

**Objectif :** traduire les règles de sécurité de `CLAUDE.md` en vraies permissions, appliquées par Claude Code.

**Ce qui a été fait :**

- Création du fichier avec trois listes :
  - `allow` : `git status`, `git diff` et `git log` autorisés sans demander ;
  - `ask` : suppression de fichiers soumise à confirmation ;
  - `deny` : commandes Git qui modifient l'historique ou les fichiers interdites, lecture des fichiers `.env` interdite.
- Ajout, à ma demande, de `git restore`, `git stash` et `git switch` dans les interdictions.
- J'ai ensuite modifié le fichier moi-même : la suppression de fichiers est passée en `deny` (interdite) et le déplacement (`mv`) en `ask`.

**Décisions :**

- Les règles sont écrites pour Bash **et** pour PowerShell, car Claude peut utiliser les deux sur mon PC.
- `CLAUDE.md` reste la règle principale, `settings.json` sert de filet de sécurité.

**Ce que j'ai appris :**

- Une règle `deny` bloque même si l'action est demandée.
- Ces règles comparent seulement le **début** d'une commande : elles ne sont pas une protection parfaite.

---

## Étape 6 : renforcement des règles de sécurité

**Date :** 29/10/2026

**Objectif :** interdire toute suppression et exiger mon accord avant toute modification, tout déplacement, toute installation et toute exécution de programme.

**Ce qui a été fait :**

- `CLAUDE.md` : trois nouvelles règles (pas de suppression, accord avant de modifier/créer/déplacer/renommer, accord avant d'installer ou d'exécuter), et liste des commandes Git interdites alignée sur `settings.json`.
- `settings.json` : ajout de `Edit`, `Bash` et `PowerShell` dans la liste `ask`.

**Décisions :**

- Choix de l'**option A** : toute commande demande une confirmation. C'est plus contraignant, mais je garde le contrôle sur chaque action.

**Ce que j'ai appris :**

- Il faut parfois relancer Claude Code pour que de nouveaux réglages soient pris en compte.
- Plus une règle est large, plus elle protège, mais plus elle demande de confirmations.

---

## Étape 7 : test de l'interdiction de suppression

**Date :** 29/10/2026

**Objectif :** vérifier que Claude Code ne peut pas supprimer un fichier, comme le prévoient les règles de sécurité.

**Ce qui a été fait :**

- J'ai créé un fichier de test, `test.txt`.
- J'ai demandé à Claude Code de supprimer ce fichier.
- Claude a refusé de lui-même, en respectant la règle de `CLAUDE.md` qui lui interdit toute suppression.

**Décisions :**

- La règle d'interdiction de suppression est validée : Claude la respecte.

**Ce que j'ai appris :**

- Il faut tester une règle de sécurité plutôt que supposer qu'elle fonctionne.
- Claude a refusé avant même d'essayer une commande : c'est donc la consigne de `CLAUDE.md` qui a joué. Le blocage technique de `settings.json` (règle `deny`) n'a pas eu besoin d'intervenir, il reste là en filet de sécurité.

---

## Étape 8 : rédaction du `README.md`

**Date :** 30/10/2026

**Objectif :** présenter le projet sur la page d'accueil du dépôt GitHub.

**Ce qui a été fait :**

- J'ai rédigé un `README.md` : objectif du projet (support de l'épreuve E5 et apprentissage), choix techniques, méthode de travail avec l'IA, garde-fous de sécurité, critères de qualité, structure du dépôt et feuille de route.

**Décisions :**

- Assumer et expliquer l'utilisation de Claude Code : l'IA m'assiste, mais je valide et je comprends chaque modification.

**Ce que j'ai appris :**

- Le `README.md` est la première chose qu'un visiteur (ou un jury) voit en ouvrant le dépôt.

---

## Étape 8 : ajout du système de design `DESIGN.md`

**Date :** 03/11/2026

**Objectif :** définir une identité visuelle unique pour tout le site.

**Ce qui a été fait :**

- J'ai ajouté un fichier `DESIGN.md` qui décrit le style visuel : couleurs, typographie, espacements, arrondis, composants (navigation, boutons, cartes, formulaires, pied de page) et comportement responsive.
- J'ai ajouté une ligne dans `CLAUDE.md`, section « Exigences de qualité » : pour toute tâche qui touche à l'apparence, Claude doit d'abord lire `DESIGN.md` et le respecter.
- J'ai aussi précisé dans `CLAUDE.md` que les messages de commit proposés doivent suivre la convention **Conventional Commits**.

**Décisions :**

- Un seul fichier de référence pour l'apparence, afin que toutes les pages restent cohérentes.
- Des messages de commit normalisés (`feat:`, `fix:`, `docs:`…) pour un historique lisible.

**Ce que j'ai appris :**

- Un système de design regroupe toutes les règles visuelles au même endroit : on peut ensuite les traduire en variables CSS.
