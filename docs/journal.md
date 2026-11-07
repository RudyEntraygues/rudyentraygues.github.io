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

---

## Étape 17 : section héros et boutons

**Date :** 03/11/2026

**Objectif :** mettre en forme la première section de l'accueil : grand titre, accroche et deux boutons.

**Ce qui a été fait :**

- Dans `css/style.css`, ajout d'une section « Héros » :
  - `.heros` : fond blanc, contenu centré, 80px d'espace en haut et en bas ;
  - titre `h1` en 56px avec des lettres légèrement resserrées ;
  - `.accroche` en 28px, avec une largeur limitée et centrée ;
  - `.boutons` : les deux boutons côte à côte, centrés, qui passent l'un sous l'autre si la place manque ;
  - `.bouton` : forme de pilule commune, avec `.bouton-principal` (bleu plein, texte blanc) et `.bouton-secondaire` (contour bleu, fond transparent).
- Deux media queries pour le responsive :
  - jusqu'à 1068px : titre en 40px ;
  - jusqu'à 640px : titre en 34px, accroche en 21px, espace réduit à 48px.
- Vérification dans Chrome via Live Server à trois largeurs :
  - téléphone (400px) : titre sur 2 lignes, boutons côte à côte de 49px de haut ;
  - ordinateur (982px) : titre en 40px ;
  - grand écran (1280px) : titre en 56px.
  - Dans les trois cas, il n'y a pas de défilement horizontal, et le contour bleu apparaît au clavier sur les boutons.

**Problèmes et solutions :** Aucun.

**Décisions :**

- Une classe `.bouton` pour la forme commune, et une classe par variante pour les couleurs : la pilule n'est écrite qu'une fois.
- Le bouton principal a aussi une bordure de 1px, de la même couleur que son fond, pour que les deux boutons aient exactement la même taille.
- Deux paliers de taille de titre au lieu des trois de `DESIGN.md` : en 34px, le titre tient déjà sur 2 lignes sur un téléphone.
- L'effet au clic sur les boutons est reporté à l'étape des animations.

**Ce que j'ai appris :**

- Une media query (`@media (max-width: 640px) { … }`) applique des règles seulement sur les écrans assez étroits : c'est la base du responsive.
- `margin: 0 auto` centre horizontalement un bloc qui a une largeur maximale.
- On peut combiner plusieurs classes sur un même élément (`class="bouton bouton-principal"`) pour partager une base commune et ajouter des variantes.
- `border-radius` avec une très grande valeur donne une forme de pilule.

---

## Étape 18 : passage du bleu au vert

**Date :** 03/11/2026

**Objectif :** remplacer le bleu repris de `DESIGN.md` par du vert, pour donner au site une couleur qui me soit propre.

**Ce qui a été fait :**

- Choix des trois verts avec Claude (chat), puis vérification des contrastes par Claude Code :

  | Rôle                            | Avant     | Après     | Contraste                                    |
  | ------------------------------- | --------- | --------- | -------------------------------------------- |
  | Liens et boutons sur fond clair | `#0066cc` | `#00783c` | 5,6:1 sur blanc (et texte blanc sur ce vert) |
  | Contour au clavier              | `#0071e3` | `#008643` | 5,1:1 sur blanc, 4,1:1 sur la barre noire    |
  | Liens sur fond sombre           | `#2997ff` | `#00ab56` | 4,9:1 sur `#272729`                          |

- `DESIGN.md` : remplacement des trois codes couleur, des noms de couleurs (« Action Blue » devient « Action Green »…) et du mot « blue » dans les phrases. Le reste du fichier n'a pas changé.
- `css/style.css` : changement des trois valeurs dans `:root`, et du mot « bleu » dans les commentaires.
- Vérification dans Chrome via Live Server, en largeur ordinateur (982px) et téléphone (390px) : boutons, liens et contour au clavier sont verts, sans défilement horizontal.

**Problèmes et solutions :** Aucun.

**Décisions :**

- Garder `DESIGN.md` tel quel en dehors des couleurs : il reste la référence pour la suite du design.
- Ne pas renommer les variables CSS : leurs noms (`--couleur-principale`…) décrivent un rôle, pas une couleur, donc ils restent justes avec le vert.
- Faire deux commits séparés : un pour `DESIGN.md` (documentation), un pour le CSS (changement visible).

**Ce que j'ai appris :**

- Grâce aux variables CSS, changer la couleur de tout le site n'a demandé que trois lignes.
- Il vaut mieux nommer une variable selon son rôle (`--couleur-principale`) plutôt que selon sa couleur (`--bleu`) : le nom reste valable si la couleur change.
- Il faut vérifier le contraste d'une nouvelle couleur avant de l'adopter : le texte doit atteindre au moins 4,5:1, et un contour au moins 3:1.

---

## Étape 19 : section de présentation (tuile sombre)

**Date :** 03/11/2026

**Objectif :** mettre en forme la section « Ce que je fais » en tuile sombre, pour créer une alternance avec le héros clair.

**Ce qui a été fait :**

- Dans `css/style.css`, ajout d'une section « Présentation » :
  - `.presentation` : fond `#272729`, texte blanc, contenu centré, 80px d'espace en haut et en bas ;
  - titre `h2` en 40px ;
  - paragraphe en 21px avec un interligne de 1.5, et une largeur limitée à 760px ;
  - règle pour les futurs liens de cette section, en vert clair (`--couleur-principale-sombre`).
- Media query jusqu'à 640px : espace réduit à 48px, titre en 28px, texte en 17px.
- Vérification dans Chrome via Live Server :
  - ordinateur (1536px) : titre en 40px, texte en 21px sur 3 lignes de 760px maximum ;
  - téléphone (390px) : titre en 28px, texte en 17px ;
  - il n'y a pas de défilement horizontal, et aucun espace blanc entre le héros et la section sombre.

**Problèmes et solutions :** Aucun.

**Décisions :**

- Paragraphe en 21px plutôt que les 28px prévus par `DESIGN.md` sous les titres des tuiles : ce paragraphe fait plusieurs lignes, et une taille plus petite se lit mieux.
- Largeur du paragraphe limitée à 760px : un texte centré devient difficile à lire si les lignes sont trop longues.
- Pas de bordure entre les sections : le passage du fond blanc au fond sombre suffit à les séparer.

**Ce que j'ai appris :**

- Sur un fond sombre, il faut changer la couleur du texte (blanc) et celle des liens (un vert plus clair), sinon ils deviennent illisibles.
- Une règle CSS peut cibler un élément à l'intérieur d'un autre, par exemple `.presentation h2` pour le titre de cette section seulement.
- Le blanc sur `#272729` a un contraste d'environ 14:1, très au-dessus du minimum de 4,5:1.

---

## Étape 20 : cartes de raccourcis

**Date :** 03/11/2026

**Objectif :** mettre en forme la section « Découvrir mon portfolio » et ses 4 cartes vers les autres pages.

**Ce qui a été fait :**

- Dans `css/style.css`, ajout d'une section « Raccourcis » :
  - `.raccourcis` : fond parchemin (gris très clair), 80px d'espace en haut et en bas ;
  - titre `h2` en 40px, centré ;
  - `.cartes` : grille de 4 colonnes de même largeur, avec 24px entre les cartes et une largeur maximale de 980px ;
  - `.carte` : fond blanc, bordure fine, arrondi de 18px, 24px de marge intérieure, pas d'ombre ;
  - titres des cartes en 21px ;
  - `flex-grow: 1` sur le texte, pour aligner les liens en bas des cartes.
- Media queries :
  - jusqu'à 1068px : 2 colonnes ;
  - jusqu'à 640px : 1 colonne, titre en 28px, espace réduit à 48px.
- Vérification dans Chrome via Live Server :
  - ordinateur (1536px) : 4 cartes de 227px, liens alignés à la même hauteur ;
  - tablette (900px) : 2 lignes de 2 cartes, liens alignés sur chaque ligne ;
  - téléphone (390px) : cartes empilées ;
  - il n'y a jamais de défilement horizontal.

**Problèmes et solutions :** Aucun.

**Décisions :**

- 4, puis 2, puis 1 colonne : le nombre de colonnes suit le nombre de cartes et la largeur de l'écran.
- Les liens des cartes restent soulignés, comme les autres liens dans du texte.
- Même taille de titre `h2` que la section sombre (40px, puis 28px sur téléphone), pour que les sections restent cohérentes.

**Ce que j'ai appris :**

- `display: grid` avec `grid-template-columns: repeat(4, 1fr)` crée 4 colonnes de même largeur ; `1fr` signifie « une part de l'espace disponible ».
- `gap` règle l'espace entre les éléments d'une grille (ou d'un flex), sans ajouter de marge sur les bords.
- Dans une carte en `flex-direction: column`, `flex-grow: 1` sur le texte le fait grandir pour remplir la place libre, ce qui pousse le lien tout en bas.

---

## Étape 21 : pied de page

**Date :** 03/11/2026

**Objectif :** mettre en forme le pied de page, présent sur toutes les pages.

**Ce qui a été fait :**

- Dans `css/style.css`, ajout d'une section « Pied de page » :
  - `.pied-de-page` : fond parchemin, ligne fine en haut, texte `#333333` en 14px, centré, 32px d'espace en haut et en bas ;
  - disposition en `flex` avec `flex-wrap` : le copyright est seul sur sa ligne (`flex-basis: 100%`) et les 3 liens (GitHub, LinkedIn, Mentions légales) sont côte à côte en dessous ;
  - marge intérieure verticale sur les liens pour agrandir la zone cliquable.
- Vérification dans Chrome via Live Server, sur l'accueil et sur `mentions-legales.html` :
  - ordinateur (1536px) : pied de page de 130px de haut, les 3 liens sur une ligne, chacun de 37px de haut ;
  - téléphone (390px) : le copyright passe sur 2 lignes bien serrées, les liens se placent sur 2 lignes (2 + 1), centrés ;
  - il n'y a pas de défilement horizontal.

**Problèmes et solutions :**

- **Problème :** l'ajout du CSS a d'abord échoué, car `css/style.css` avait été reformaté avec une indentation de 2 espaces au lieu de 4 (sans doute par un formateur automatique de VS Code à l'enregistrement).
- **Solution :** relecture du fichier, puis écriture de la nouvelle section avec 2 espaces, pour rester cohérent.
- **Problème :** dans la première version (liens l'un sous l'autre, avec l'interligne de 2.41 prévu par `DESIGN.md`), le copyright passait sur 2 lignes sur téléphone avec un grand trou entre elles.
- **Solution :** j'ai choisi de placer les liens côte à côte avec un interligne normal : le pied de page est plus discret, et le défaut disparaît.

**Décisions :**

- Une ligne fine en haut du pied de page, car les cartes juste au-dessus ont le même fond parchemin.
- Les liens côte à côte plutôt que l'un sous l'autre, pour un pied de page moins épais et plus discret.
- Je m'écarte de `DESIGN.md` : texte en 14px au lieu de 12px, interligne normal au lieu de 2.41, 32px d'espace au lieu de 64px.
- Tout en CSS, sans modifier le HTML des deux pages.

**Ce que j'ai appris :**

- `flex-basis: 100%` force un élément d'un flex à occuper toute une ligne : les éléments suivants passent dessous.
- Un grand interligne convient à une liste de liens, mais pas à une phrase qui passe sur plusieurs lignes.
- Un formateur automatique peut modifier un fichier à l'enregistrement : il faut le relire avant de le modifier à nouveau.

---

## Étape 22 : retirer les références à Apple de DESIGN.md

**Date :** 04/11/2026

**Objectif :** faire de `DESIGN.md` le système de design de mon portfolio, et non plus une analyse du site d'Apple. Corriger aussi une erreur de casse dans `CLAUDE.md`.

**Ce qui a été fait :**

- Dans `CLAUDE.md`, la ligne des exceptions de nommage écrit maintenant `DESIGN.md` au lieu de `DESIGN.MD`. Rien d'autre n'a changé dans ce fichier.
- Dans `DESIGN.md` :
  - le nom passe de `Apple-design-analysis` à `portfolio-rudy`, et la description décrit un portfolio sobre et aéré avec un seul accent vert ;
  - toutes les mentions d'Apple et de ses produits (iPhone 17 Pro, Apple Watch, AirPods, « Apple tight », « signature Apple », logo Apple, boutons « Buy » / « Bag ») ont été réécrites pour parler du portfolio (sections, cartes de projets, contenu) ;
  - les noms de couleur sont repassés en vert : « Action Green », « Focus Green », « Sky Link Green ».
- Vérification avec `git diff` et des comparaisons en lecture seule avec le dernier commit :
  - le bloc de valeurs (lignes 5 à 274 : couleurs, typographie, arrondis, espacements, composants) est identique ;
  - aucune valeur (hex, px, em, %, rgba, ratios, interlignes) n'a disparu ni n'a été ajoutée ;
  - les titres de sections sont les mêmes, et il y a toujours 8 règles « Do » et 8 règles « Don't » ;
  - il ne reste aucune mention d'Apple, sauf `-apple-system` dans les piles de polices (c'est une valeur technique).

**Problèmes et solutions :**

- **Problème :** avant de commencer, la version non enregistrée dans Git de `DESIGN.md` était revenue aux noms « Action Blue », « blue pill »…, alors que le dernier commit disait « Green » (les tableaux avaient aussi été réalignés, sans doute par un formateur automatique de VS Code). Les valeurs hex, elles, n'avaient pas changé.
- **Solution :** j'ai décidé de remettre les noms en « Green » pendant la réécriture, pour que les textes correspondent à ma couleur d'accent.

**Décisions :**

- Les noms des composants (`product-tile-light`, `store-utility-card`, `environment-quote-card`…) n'ont pas changé : ce sont des identifiants utilisés dans les références `{component.…}`, donc des valeurs.
- La section « Note on Font Substitutes » ne cite plus Apple ni macOS/iOS : elle dit seulement que SF Pro n'est pas disponible partout.
- Les polices `SF Pro Display` et `SF Pro Text` restent dans les valeurs. À décider plus tard : SF Pro n'existe que sur les appareils Apple, donc sur Windows et Android le site s'affiche avec la police du système (`system-ui`).
- Le texte reste en anglais, comme le fichier d'origine.

**Ce que j'ai appris :**

- On peut s'inspirer d'un design existant, mais il faut le rendre personnel : un système de design ne doit pas recopier les noms et les textes d'une autre marque.
- `-apple-system` n'est pas une mention d'Apple : c'est un mot-clé CSS qui demande au navigateur la police du système.
- Un formateur automatique peut modifier un fichier sans prévenir : `git diff` permet de voir exactement ce qui a changé depuis le dernier commit.

---

## Étape 23 : nettoyage des dernières traces d'Apple dans DESIGN.md

**Date :** 04/11/2026

**Objectif :** retirer de `DESIGN.md` les noms encore copiés du site d'Apple, pour que ce soit vraiment mon design : inspiré d'Apple, avec une touche de vert.

**Ce qui a été fait :**

- Renommage des composants qui venaient de la boutique Apple, partout dans le fichier (YAML et texte) :

  | Avant                                                         | Après                 |
  | ------------------------------------------------------------- | --------------------- |
  | `product-tile-light / -parchment / -dark / -dark-2 / -dark-3` | `section-tile-…`      |
  | `store-utility-card`                                          | `project-card`        |
  | `button-store-hero`                                           | `button-hero`         |
  | `configurator-option-chip(-selected)`                         | `tag-chip(-selected)` |
  | `environment-quote-card`                                      | `quote-card`          |

- Couleurs : « Sky Link Green » (copié du « Sky Link Blue » d'Apple) devient « Light Green ». « Paper White », une couleur qui n'existait pas dans mes couleurs, est remplacée par `{colors.on-primary}`.
- La description et l'introduction disent maintenant que c'est mon système de design, inspiré du style sobre d'Apple, avec un seul accent vert.
- Correction de deux incohérences :
  - le bouton secondaire avait un fond blanc dans le YAML mais un fond transparent dans le texte. Le YAML passe en `transparent`, comme dans `css/style.css` ;
  - le texte disait que le `tagline` était parfois en graisse 700, alors que le YAML le définit en 600. Le texte dit maintenant 600.
- Vérifications en lecture seule :
  - plus aucun ancien nom dans le fichier ;
  - chaque référence `{component.…}` et `{colors.…}` pointe vers un élément défini dans le YAML ;
  - les nouveaux noms ne sont pas utilisés dans le CSS, le HTML ou le JavaScript, donc le site ne change pas.

**Problèmes et solutions :** Aucun.

**Décisions :**

- À l'étape 22, les noms des composants avaient été gardés parce que ce sont des identifiants. Comme ils ne servent qu'à l'intérieur de `DESIGN.md`, on peut les renommer sans rien casser, à condition de les remplacer partout à la fois.
- La police SF Pro est conservée. `-apple-system` reste aussi, car c'est un mot-clé CSS.
- « Learn more » et les noms comme « Parchment » ou « Pearl » sont gardés : ce sont des mots courants, pas des noms de produits Apple.

**Ce que j'ai appris :**

- Pour renommer un identifiant, il faut le remplacer partout en même temps (définition et références), sinon des références pointent vers un élément qui n'existe plus.
- Avant de renommer, il faut vérifier où le nom est utilisé : ici, seulement dans `DESIGN.md`, donc le site n'est pas touché.
- Une documentation peut se contredire (YAML d'un côté, texte de l'autre) : c'est le code réel (`style.css`) qui permet de trancher.

---

## Étape 24 : tailles de texte en `rem`

**Date :** 04/11/2026

**Objectif :** faire grossir le texte du site quand un visiteur augmente la taille de police dans les réglages de son navigateur (accessibilité).

**Ce qui a été fait :**

- Dans `css/style.css`, les 16 valeurs de `font-size` passent de `px` en `rem`, avec une base de 16px = 1rem. La valeur d'origine est notée en commentaire (par exemple `1.0625rem; /* 17px */`) :

  | px   | rem       |
  | ---- | --------- |
  | 14px | 0.875rem  |
  | 17px | 1.0625rem |
  | 21px | 1.3125rem |
  | 28px | 1.75rem   |
  | 34px | 2.125rem  |
  | 40px | 2.5rem    |
  | 56px | 3.5rem    |

- Les espacements, arrondis, bordures, largeurs, `letter-spacing` et points de rupture des media queries restent en `px`.
- Vérification dans Chrome via Live Server, en mesurant les tailles calculées par le navigateur :
  - à taille de police par défaut, ordinateur (1536px) et téléphone (375px) : toutes les tailles sont identiques à avant, au pixel près ;
  - avec une taille de racine de 24px (l'équivalent du réglage « Très grande ») : le texte grossit de 50 % (17px devient 25,5px, le titre passe de 56px à 84px), sans défilement horizontal. Sur téléphone, le menu passe sur plus de lignes.

**Problèmes et solutions :**

- **Problème :** Claude n'arrivait pas à réduire la fenêtre de Chrome à 375px (elle restait à 1536px).
- **Solution :** affichage de la page dans un cadre (`iframe`) de 375px de large, qui se comporte comme un écran de téléphone.
- **Problème :** le réglage « Très grande » se trouve dans `chrome://settings/fonts`, une page de Chrome que Claude ne modifie pas.
- **Solution :** simulation en mettant temporairement `<html>` à 24px dans la page de test, sans modifier le fichier CSS. Il me reste à faire le test réel moi-même dans les réglages de Chrome.

**Décisions :**

- Base de 16px, car c'est la taille par défaut de tous les navigateurs : le rendu par défaut ne change pas.
- `rem` plutôt que `em`, pour éviter que les tailles se multiplient quand des éléments sont imbriqués.
- Pas de `font-size` sur `<html>` dans le CSS, sinon on écraserait le réglage du visiteur.
- Les autres unités restent en `px` pour l'instant : on change une seule chose à la fois.

**Ce que j'ai appris :**

- `px` est une taille fixe, qui ignore le réglage de taille de police du visiteur.
- `rem` est un multiple de la taille du texte de `<html>`, qui vient du réglage du navigateur : 1rem = 16px par défaut, 24px en « Très grande ».
- `em` dépend de la taille du parent, donc les valeurs se multiplient quand on imbrique des éléments.
- Pour convertir, on divise par 16 : 17px ÷ 16 = 1,0625rem.

---

## Étape 25 : structure HTML de la page « Mon parcours »

**Date :** 04/11/2026

**Objectif :** écrire le contenu HTML de `mon-parcours.html` à partir de mon CV, sans le style.

**Ce qui a été fait :**

- Claude a proposé une structure de page, que j'ai validée après avoir répondu à ses questions. Je ne fais plus de maquette à la main : Claude propose, je valide ou je demande des modifications.
- `mon-parcours.html` contient :
  - le même en-tête et le même pied de page que l'accueil, avec « Mon parcours » marqué comme page en cours ;
  - un titre `h1` et une introduction, inspirée de mon CV, qui met en avant ma curiosité et ma motivation ;
  - les sections Formation, Alternance (chargé de support IT chez Malakoff Humanis), Expériences professionnelles (6 postes, du plus récent au plus ancien), Certifications et Langues ;
  - des liens vers les pages Compétences et Projets.
- Vérification dans Chrome via Live Server :
  - un seul `h1`, puis des `h2` et des `h3`, sans saut de niveau ;
  - ordinateur (1536px) et téléphone (375px) : pas de défilement horizontal. Le contenu n'a pas encore de style : il sera mis en forme à la phase CSS.

**Problèmes et solutions :** Aucun.

**Décisions :**

- Pas de numéro de téléphone, d'adresse e-mail personnelle ni de photo : le site est public, ce sont des données personnelles.
- Ville affichée : Rennes. Les noms d'entreprises sont cités. Pas de centres d'intérêt pour l'instant.
- L'alternance est décrite de façon générale (poste et type de missions), sans aucune information interne.
- Les compétences techniques (Linux, Proxmox, Docker…) iront sur la page Compétences, et le homelab sur la page Projets, pour ne pas répéter la même chose sur deux pages.
- Les dates sont écrites dans des balises `<time datetime="…">`, qui donnent la date exacte aux navigateurs et aux lecteurs d'écran.

**Ce que j'ai appris :**

- La balise `<time>` affiche une date lisible pour l'humain, et son attribut `datetime` donne la même date dans un format compris par les machines (par exemple `2026-07`).
- Un `<article>` regroupe un bloc complet et autonome, comme une expérience professionnelle.
- Un site public est lu par tout le monde, y compris par les moteurs de recherche : on n'y met que les informations qu'on accepte de rendre publiques.

---

## Étape 26 : structure HTML de la page « Compétences »

**Date :** 05/11/2026

**Objectif :** écrire le contenu HTML de `competences.html`, sans le style, à partir de mon CV et du README de mon profil GitHub.

**Ce qui a été fait :**

- `competences.html` contient :
  - le même en-tête et le même pied de page que les autres pages, avec « Compétences » marqué comme page en cours ;
  - une introduction qui dit clairement que je présente ce que je pratique, et que je reste en apprentissage ;
  - les 6 compétences du BTS SIO, chacune avec l'endroit où je la travaille (homelab, alternance, portfolio, veille) ;
  - les technologies que je pratique, regroupées par domaine ;
  - ce que j'apprends en ce moment et mes prochaines étapes.
- Vérification dans Chrome via Live Server :
  - un seul `h1`, puis des `h2` et des `h3`, sans saut de niveau ;
  - ordinateur (1536px) et téléphone (375px) : pas de défilement horizontal. Le contenu n'a pas encore de style : il sera mis en forme à la phase CSS.

**Problèmes et solutions :**

- **Problème :** la première version de la page, proposée par Claude, ne reprenait que mon CV et n'utilisait pas le README de mon profil GitHub. Je l'ai refusée.
- **Solution :** Claude a lu mon README, puis a réécrit la page en ajoutant TCP/IP, VLAN, Kali Linux, VirtualBox, PowerShell, Python, Home Assistant et mes apprentissages en cours.
- **Problème :** sur GitHub, une partie des compétences du README est affichée sous forme de badges, donc d'images, absents du texte de la page.
- **Solution :** lecture du texte alternatif (`alt`) de chaque badge.

**Décisions :**

- Aucun niveau de maîtrise, ni barre ni pourcentage : je suis et je resterai en apprentissage, et un chiffre ne prouve rien.
- La mention « en cours d'acquisition » n'est pas utilisée : elle laisserait croire que les autres compétences sont entièrement acquises. L'introduction et la section « Ce que j'apprends » le disent pour toute la page.
- Les outils no-code restent dans un groupe à part, en fin de liste, pour ne pas brouiller mon profil systèmes et réseaux.
- La liste des 6 compétences du BTS est à comparer avec la grille officielle de ma session.

**Ce que j'ai appris :**

- Une compétence seule ne prouve rien : il faut montrer où elle a été mise en œuvre.
- La balise `<cite>` indique le titre d'une œuvre, comme un livre.
- Une image doit avoir un texte alternatif : c'est grâce à lui qu'un lecteur d'écran, ou un outil, peut comprendre ce qu'elle montre.

---

## Étape 27 : structure HTML de la page « Projets »

**Date :** 05/11/2026

**Objectif :** écrire le contenu HTML de `projets.html`, la liste de mes réalisations, sans le style.

**Ce qui a été fait :**

- `projets.html` contient :
  - le même en-tête et le même pied de page que les autres pages, avec « Projets » marqué comme page en cours ;
  - 4 réalisations : le support IT chez Malakoff Humanis (en cours), le Wi-Fi invité pour restaurants (en cours), le HomeLab et ce portfolio ;
  - pour chacune : une description, les technologies (sauf pour l'alternance) et les compétences du BTS SIO mobilisées ;
  - un lien vers le dépôt GitHub, ou vers Mon parcours pour l'alternance.
- Vérification dans Chrome via Live Server :
  - un seul `h1`, puis `h2`, `h3` et `h4`, sans saut de niveau ;
  - ordinateur (1536px) et téléphone (375px) : pas de défilement horizontal. Le contenu n'a pas encore de style : il sera mis en forme à la phase CSS.

**Problèmes et solutions :**

- **Problème :** Claude ne trouvait pas le projet Wi-Fi invité sur mon profil GitHub, car il se trouve dans une organisation à part.
- **Solution :** je lui ai donné le lien de l'organisation, où il a trouvé le dépôt `wifi-resto`.

**Décisions :**

- L'alternance figure parmi les réalisations avec la mention « en cours », et reste décrite de façon générale, sans aucun outil ni information interne.
- Aucune adresse IP, aucun port ni aucun détail de configuration du homelab sur le site.
- Le restaurant partenaire et les membres de l'équipe du projet Wi-Fi ne sont pas nommés.
- Pas de lien vers les fiches détaillées pour l'instant : elles n'existent pas encore.

**Ce que j'ai appris :**

- Une organisation GitHub permet à une équipe de partager des dépôts en dehors de son profil personnel.
- Pour chaque réalisation, le jury attend les compétences mobilisées et ma contribution personnelle.
- Il vaut mieux donner à un lien un texte qui dit où il mène (« Voir le dépôt HomeLab sur GitHub ») : un lecteur d'écran peut lire les liens hors de leur contexte.

---

## Étape 28 : fiche de réalisation du HomeLab

**Date :** 07/11/2026

**Objectif :** créer la première fiche de réalisation détaillée, celle du HomeLab, qui servira de modèle pour les autres fiches.

**Ce qui a été fait :**

- `projet-homelab.html` contient, dans l'ordre :
  - un résumé (début en août 2026, projet en cours) ;
  - le contexte et les objectifs : pourquoi j'ai monté ce homelab au moment de mon admission en BTS ;
  - l'environnement technique : matériel, virtualisation, applications hébergées, réseau et sécurité, supervision ;
  - ce que j'ai réalisé : installation de Proxmox, services, sécurisation, accès à distance par WireGuard, supervision ;
  - 4 problèmes rencontrés, chacun présenté en symptôme, cause et solution ;
  - le résultat, les compétences du BTS mobilisées, ce que j'ai appris, et les liens vers le dépôt et vers Projets.
- `projets.html` : ajout d'un lien « Voir la fiche détaillée du HomeLab » dans l'article HomeLab.
- Vérification dans Chrome via Live Server :
  - un seul `h1`, 23 titres sans saut de niveau, « Projets » marqué comme page en cours ;
  - ordinateur (1536px) et téléphone (375px) : pas de défilement horizontal ;
  - le lien depuis la page Projets mène bien à la fiche.

**Problèmes et solutions :**

- **Problème :** le dépôt ne cite pas toutes les applications que j'utilise.
- **Solution :** je me suis connecté via WireGuard pour retrouver mes apps : Homarr, Pi-hole, Nginx Proxy Manager, Netdata, n8n, Filebrowser et WireGuard.

**Décisions :**

- La fiche est à la racine du site, et non dans un dossier `projets/`, pour garder des liens simples, sans `../`.
- Dans le menu, « Projets » est marqué comme page en cours, car la fiche fait partie de cette rubrique.
- Sur les 8 problèmes documentés dans le dépôt, j'en garde 4 : le mode VMD, le VLAN oublié, les permissions du conteneur non privilégié et le blocage SSH. Ce sont les plus utiles pour montrer une démarche de diagnostic.
- Aucune adresse IP, aucun port ni aucun nom de machine sur le site.
- Pas de captures d'écran pour l'instant : elles viendront plus tard, une fois les informations sensibles masquées.

**Ce que j'ai appris :**

- Une fiche de réalisation sert à prouver au jury que j'ai fait le travail moi-même et que je sais l'expliquer.
- Présenter une panne en « symptôme, cause, solution » montre une méthode de diagnostic.
- Mon dépôt GitHub doit rester à jour avec ce que j'utilise réellement, sinon le site et le dépôt ne disent pas la même chose.
