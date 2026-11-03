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

**Problèmes et solutions :** Aucun.

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

**Problèmes et solutions :** Aucun.

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

**Problèmes et solutions :** Aucun.

**Décisions :**

- Convention de nommage : minuscules et **tirets `-`** (plutôt que des tirets bas), comme c'est l'usage sur le web.
- Exceptions à la convention : `CLAUDE.md` et `README.md`.

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

**Problèmes et solutions :** Aucun.

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

**Problèmes et solutions :** Aucun.

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

**Problèmes et solutions :** Aucun.

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

**Problèmes et solutions :** Aucun.

**Décisions :**

- La consigne de `CLAUDE.md` est respectée, mais la règle `deny` de `settings.json` n'a pas été testée en conditions réelles, puisque Claude a refusé avant d'essayer. Elle reste un filet de sécurité, dont le chargement se vérifie avec `/permissions`.

**Ce que j'ai appris :**

- Il faut tester une règle de sécurité plutôt que supposer qu'elle fonctionne.
- Claude a refusé avant même d'essayer une commande : c'est donc la consigne de `CLAUDE.md` qui a joué. Le blocage technique de `settings.json` (règle `deny`) n'a pas eu besoin d'intervenir, il reste là en filet de sécurité.

---

## Étape 8 : premier envoi sur GitHub, erreur GH007

**Date :** 29/10/2026

**Objectif :** envoyer le dépôt sur GitHub pour la première fois.

**Ce qui a été fait :**

- Premier `git push` du dépôt vers GitHub, refusé, puis corrigé et renvoyé avec succès.

**Problèmes et solutions :**

- **Problème :** au premier `git push`, GitHub a refusé l'envoi avec l'erreur `GH007`, car les commits contenaient mon adresse e-mail personnelle et l'option de confidentialité de l'e-mail est activée sur mon compte. Rien n'a été publié.
- **Solution :**
  1. récupération de l'adresse noreply dans les paramètres GitHub ;
  2. configuration de Git avec cette adresse (`git config --global user.email`) ;
  3. correction du commit existant avec `git commit --amend --reset-author --no-edit` ;
  4. nouvel envoi.

**Décisions :**

- Utiliser l'adresse noreply pour tous mes dépôts publics.
- Ne pas désactiver la protection de GitHub.

**Ce que j'ai appris :**

- Chaque commit contient l'adresse e-mail de son auteur : une fois le dépôt publié, elle devient visible.
- GitHub fournit une adresse noreply pour ne pas exposer son adresse personnelle.

---

## Étape 9 : rédaction du `README.md`

**Date :** 30/10/2026

**Objectif :** présenter le projet sur la page d'accueil du dépôt GitHub.

**Ce qui a été fait :**

- J'ai rédigé un `README.md` : objectif du projet (support de l'épreuve E5 et apprentissage), choix techniques, méthode de travail avec l'IA, garde-fous de sécurité, critères de qualité, structure du dépôt et feuille de route.

**Problèmes et solutions :** Aucun.

**Décisions :**

- Assumer et expliquer l'utilisation de Claude Code : l'IA m'assiste, mais je valide et je comprends chaque modification.

**Ce que j'ai appris :**

- Le `README.md` est la première chose qu'un visiteur (ou un jury) voit en ouvrant le dépôt.

---

## Étape 10 : conception du site avec Claude (chat)

**Date :** 30/10/2026

**Objectif :** réfléchir à la conception du site avec Claude (version chat) avant de commencer à coder.

**Ce qui a été fait :**

- Échange sur l'idée d'une animation de parcours au défilement, sur le contenu de la V1 et sur la couverture des compétences de l'épreuve E5.

**Problèmes et solutions :** Aucun.

**Décisions :**

- L'animation de parcours au défilement (un personnage illustré qui raconte mon parcours) est **reportée à l'an prochain**, pour trois raisons :
  - les animations CSS liées au défilement ne sont pas encore supportées par défaut sur Firefox ;
  - l'animation ne doit pas nuire à l'accessibilité ni à la lisibilité pour le jury ;
  - elle demande 10 à 15 h de travail supplémentaire, surtout pour les illustrations.
- **V1** : site statique avec des animations légères, qui respectent la préférence « réduire les animations ».
- **Couverture des compétences E5** : la compétence « Répondre aux incidents et aux demandes d'assistance » sera surtout couverte par mon alternance au support. À vérifier avec mes professeurs : un projet personnel comme mon homelab est-il accepté comme réalisation ?

**Ce que j'ai appris :**

- Une fonctionnalité CSS récente n'est pas forcément disponible sur tous les navigateurs : il faut vérifier sa compatibilité avant de l'utiliser.
- Les animations doivent respecter la préférence « réduire les animations » de l'utilisateur.

---

## Étape 11 : ajout du système de design `DESIGN.md`

**Date :** 03/11/2026

**Objectif :** définir une identité visuelle unique pour tout le site.

**Ce qui a été fait :**

- J'ai ajouté un fichier `DESIGN.md` qui décrit le style visuel : couleurs, typographie, espacements, arrondis, composants (navigation, boutons, cartes, formulaires, pied de page) et comportement responsive.
- J'ai ajouté une ligne dans `CLAUDE.md`, section « Exigences de qualité » : pour toute tâche qui touche à l'apparence, Claude doit d'abord lire `DESIGN.md` et le respecter.
- J'ai aussi précisé dans `CLAUDE.md` que les messages de commit proposés doivent suivre la convention **Conventional Commits**.

**Problèmes et solutions :** Aucun.

**Décisions :**

- Un seul fichier de référence pour l'apparence, afin que toutes les pages restent cohérentes.
- Des messages de commit normalisés (`feat:`, `fix:`, `docs:`…) pour un historique lisible.

**Ce que j'ai appris :**

- Un système de design regroupe toutes les règles visuelles au même endroit : on peut ensuite les traduire en variables CSS.

---

## Étape 12 : création de l'arborescence du site

**Date :** 03/11/2026

**Objectif :** mettre en place les dossiers et les fichiers du site, encore vides, avant d'écrire le contenu.

**Ce qui a été fait :**

- Création de six pages HTML vides à la racine : `index.html` (accueil), `mon-parcours.html`, `competences.html`, `projets.html`, `veille.html` et `contact.html`.
- Création des dossiers `css/`, `js/` et `images/`.
- Création d'une feuille de style unique `css/style.css` et d'un script unique `js/script.js`, vides.
- Ajout d'un fichier vide `images/.gitkeep`.

**Problèmes et solutions :** Aucun.

**Décisions :**

- Les pages sont à la racine, à côté de `index.html` : les liens entre pages restent simples (`href="projets.html"`).
- Une seule feuille de style et un seul script pour tout le site : plus facile à retrouver et à maintenir.
- La page « À propos » s'appelle finalement `mon-parcours.html`, nom plus parlant pour un portfolio de BTS.
- Une page de contact avec des liens seulement, sans formulaire, car un formulaire ne fonctionne pas seul sur un site statique.

**Ce que j'ai appris :**

- Git n'enregistre pas les dossiers vides : le fichier `.gitkeep` sert seulement à garder le dossier `images/` dans le dépôt. On pourra le supprimer quand il contiendra de vraies images.
- GitHub Pages affiche automatiquement `index.html` quand on visite l'adresse du site.

---

## Étape 13 : structure HTML de la page d'accueil

**Date :** 03/11/2026

**Objectif :** écrire tout le contenu HTML de `index.html`, sans le style, en avançant point par point.

**Ce qui a été fait :**

- **Squelette** : j'ai écrit moi-même le `<head>` ; j'ai corrigé les chemins vers `css/style.css` et `js/script.js` et ajouté une description. J'ai changé le titre de l'onglet en `Rudy Entraygues | Portfolio`.
- **En-tête** : mon nom en lien vers l'accueil et un menu `<nav>` de 6 liens, avec `aria-current="page"` sur « Accueil ».
- **Contenu principal** (`<main>`) : une section héros (titre `h1`, accroche, deux liens-boutons), une section « Ce que je fais » et une section de 4 cartes vers les autres pages.
- **Pied de page** : mention © 2026 et lien vers mon profil GitHub.
- **Vérification** : la page s'affiche dans Chrome via l'extension VS Code **Live Server** (`http://127.0.0.1:5500`).

**Problèmes et solutions :**

- **Problème :** l'extension Chrome de Claude refuse les fichiers ouverts en `file:///`, et Python (qui aurait permis de lancer un petit serveur local) n'est pas installé.
- **Solution :** utiliser l'extension VS Code **Live Server**, qui sert la page à l'adresse `http://127.0.0.1:5500`.

**Décisions :**

- Utiliser des balises sémantiques (`header`, `nav`, `main`, `section`, `article`, `footer`) pour l'accessibilité et le référencement.
- Respecter la hiérarchie des titres : un seul `h1`, puis `h2` pour les sections et `h3` pour les cartes.
- Des liens `<a>` (et non des `<button>`) pour les boutons du héros, car ils mènent vers une autre page.
- Des textes provisoires, que je réécrirai avec mes propres mots.
- Aucune donnée personnelle sensible dans le pied de page : seulement un lien GitHub, qui est public.

**Ce que j'ai appris :**

- Sans CSS, le navigateur applique un style par défaut : texte noir, liens bleus soulignés, listes à puces.
- Un chemin comme `href="style.css"` est relatif : il cherche le fichier dans le même dossier que la page. Il faut écrire `css/style.css` si le fichier est dans un sous-dossier.
- `aria-label` et `aria-current` donnent des informations aux lecteurs d'écran sans rien changer à l'affichage.
- Un serveur web local (Live Server) envoie les fichiers au navigateur en HTTP, comme le fera GitHub Pages.

---

## Étape 14 : variables CSS

**Date :** 03/11/2026

**Objectif :** commencer le CSS en traduisant les valeurs de `DESIGN.md` en variables, avant de styler la page étape par étape.

**Ce qui a été fait :**

- Dans `css/style.css`, déclaration de variables dans `:root` : couleurs (un seul bleu pour les éléments cliquables, couleurs de texte et de fond), polices, espacements, arrondis et largeur maximale du contenu.
- Aucun changement visible à l'écran : les variables ne sont pas encore utilisées.

**Problèmes et solutions :** Aucun.

**Décisions :**

- Des noms de variables en français (`--couleur-principale`, `--fond-parchemin`…), pour respecter la convention du projet et rester lisibles.
- Seulement les valeurs utiles à mon site : les éléments que je n'ai pas (recherche, configurateur…) sont laissés de côté.
- La police du système (`system-ui`), sans police à télécharger, pour respecter la règle « aucune dépendance ».
- Une largeur maximale de 980px, prévue par `DESIGN.md` pour les pages riches en texte.
- Le gris `#7a7a7a` n'est pas repris : sur le fond `#f5f5f7`, son contraste (environ 4:1) est sous le minimum d'accessibilité de 4,5:1 pour du petit texte.

**Ce que j'ai appris :**

- Une variable CSS se déclare avec deux tirets (`--nom: valeur;`) et s'utilise avec `var(--nom)`.
- `:root` représente toute la page : une variable déclarée là est utilisable partout.
- Avec des variables, on change une couleur à un seul endroit au lieu de la chercher dans tout le fichier.

---

## Étape 15 : styles de base

**Date :** 03/11/2026

**Objectif :** régler ce qui s'applique à toute la page avant de styler chaque zone.

**Ce qui a été fait :**

- Dans `css/style.css`, ajout d'une section « Base » :
  - `box-sizing: border-box` sur tous les éléments ;
  - `body` : suppression de la marge par défaut, police du texte, taille 17px, interligne 1.47, couleur du texte et du fond ;
  - titres `h1`, `h2`, `h3` : police d'affichage, graisse 600, interligne serré ;
  - paragraphes : marge du bas uniforme ;
  - liens : bleu principal, et contour bleu visible en navigation au clavier (`:focus-visible`).

**Problèmes et solutions :**

- **Problème :** l'extension Claude pour Chrome n'était pas connectée, donc Claude ne pouvait pas faire les captures d'écran de vérification.
- **Solution :** reconnexion de l'extension et relance de Live Server, puis vérification de l'affichage, faite en même temps que l'étape 16.

**Décisions :**

- Les tailles des titres seront réglées zone par zone (héros, présentation, cartes) aux étapes suivantes.
- Les liens restent soulignés pour l'instant : un lien ne doit pas se reconnaître seulement à sa couleur (accessibilité).
- Le contour de focus n'apparaît qu'au clavier (`:focus-visible`), comme le prévoit `DESIGN.md`.

**Ce que j'ai appris :**

- Le navigateur ajoute une marge par défaut autour de la page : `margin: 0` sur `body` la supprime.
- Avec `box-sizing: border-box`, la largeur d'un élément inclut ses marges intérieures et sa bordure.
- `:focus-visible` cible un élément sélectionné au clavier, ce qui aide les personnes qui ne se servent pas d'une souris.

---

## Étape 16 : en-tête et menu de navigation

**Date :** 03/11/2026

**Objectif :** mettre en forme la barre du haut, présente sur toutes les pages.

**Ce qui a été fait :**

- Dans `css/style.css`, ajout d'une section « En-tête et menu » :
  - `.en-tete` : barre noire, avec mon nom à gauche et le menu à droite (`display: flex`) ;
  - `.logo` : mon nom en blanc, 14px, graisse 600, sans soulignement ;
  - `.menu` : liste sans puces, liens en ligne ;
  - `.menu a` : liens blancs en 14px, sans soulignement, avec une zone cliquable d'au moins 44px de haut ;
  - la page en cours (`aria-current="page"`) est soulignée.
- Vérification dans Chrome via Live Server, en largeur ordinateur et en vue téléphone (400px).

**Problèmes et solutions :**

- **Problème :** en vue téléphone, mon nom était collé tout en haut de la barre noire. Sur mobile, il se retrouve seul sur sa ligne, et contrairement aux liens du menu, il n'avait pas de marge intérieure.
- **Solution :** ajout de `display: inline-block` et `padding: var(--espace-sm) 0` sur `.logo`, comme pour les liens du menu. Mon nom a maintenant de l'air au-dessus, et sa zone cliquable fait 45px de haut.
- **Problème :** Claude n'arrivait pas à réduire la fenêtre de Chrome pour tester l'affichage mobile.
- **Solution :** j'ai activé la vue téléphone dans l'outil Inspecter de Chrome.

**Décisions :**

- Pas de menu « hamburger » dans la V1 : sur mobile, les liens passent à la ligne grâce à `flex-wrap: wrap`. Cela fonctionne sans JavaScript et reste accessible. Un hamburger pourra être ajouté plus tard.
- Liens du menu en 14px au lieu des 12px prévus par `DESIGN.md`, pour qu'ils restent lisibles, surtout sur mobile.
- La page en cours est signalée par un soulignement, et pas seulement par une couleur.

**Ce que j'ai appris :**

- `display: flex` place les éléments enfants en ligne ; `justify-content: space-between` les écarte aux deux bouts.
- `flex-wrap: wrap` permet aux éléments de passer à la ligne quand la place manque : c'est une façon simple d'adapter un menu au mobile.
- Un sélecteur d'attribut comme `a[aria-current="page"]` cible les éléments qui ont cet attribut.
- Une zone cliquable doit mesurer au moins 44px de haut pour être facile à toucher au doigt.
- Un défaut peut être invisible sur ordinateur et n'apparaître que sur mobile : il faut toujours vérifier les deux largeurs.
- Dans Chrome, l'outil Inspecter (F12) a un mode téléphone (Ctrl+Maj+M) qui sert à tester l'affichage mobile.
