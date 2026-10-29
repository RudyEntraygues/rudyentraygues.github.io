# Portfolio BTS SIO SISR

Portfolio professionnel réalisé dans le cadre de mon BTS Services Informatiques aux Organisations, option SISR (Solutions d'Infrastructure, Systèmes et Réseaux).

**Site en ligne :** https://rudyentraygues.github.io _(en construction)_

> **Statut :** phase 1, mise en place du projet. Le site n'est pas encore publié.

---

## Sommaire

- [Objectif du projet](#objectif-du-projet)
- [Choix techniques](#choix-techniques)
- [Méthodologie : travailler avec une IA sans lui déléguer la compréhension](#méthodologie--travailler-avec-une-ia-sans-lui-déléguer-la-compréhension)
- [Garde-fous de sécurité](#garde-fous-de-sécurité)
- [Critères de qualité](#critères-de-qualité)
- [Structure du dépôt](#structure-du-dépôt)
- [Feuille de route](#feuille-de-route)
- [Documentation](#documentation)

---

## Objectif du projet

Ce site a deux objectifs :

1. **Servir de support à l'épreuve E5** du BTS SIO : présenter mon parcours, mes réalisations professionnelles, les compétences mobilisées, mon tableau de synthèse et ma veille technologique.
2. **Apprendre comment fonctionne un site web de bout en bout** : structure, mise en forme, interactions, versionnement, hébergement et, plus tard, base de données et supervision.

Le projet est lui-même une réalisation professionnelle : il mobilise le travail en mode projet, la mise à disposition d'un service et le développement de la présence en ligne.

---

## Choix techniques

| Technologie      | Rôle                                   | Pourquoi ce choix                                                             |
| ---------------- | -------------------------------------- | ----------------------------------------------------------------------------- |
| **HTML**         | Structure et contenu des pages         | Écrit en HTML sémantique pour l'accessibilité et le référencement             |
| **CSS**          | Mise en forme et adaptation aux écrans | Variables CSS issues d'un système de design unique, pour un rendu cohérent    |
| **JavaScript**   | Interactions                           | Utilisé avec parcimonie : le site reste lisible si le script ne se charge pas |
| **Git / GitHub** | Versionnement et sauvegarde            | Historique complet et traçable de chaque modification                         |
| **GitHub Pages** | Hébergement                            | Gratuit, en HTTPS, adapté à un site statique                                  |

**Site statique, sans framework ni bibliothèque.** Un portfolio change peu : il n'a pas besoin d'une base de données ni de code côté serveur. Ce choix rend le site plus rapide, plus sûr (aucun code serveur exposé) et surtout **entièrement compréhensible** : chaque ligne a été écrite ou relue en sachant ce qu'elle fait. Une partie dynamique (PHP, base de données) est prévue dans une phase ultérieure, quand un vrai besoin l'exigera.

---

## Méthodologie : travailler avec une IA sans lui déléguer la compréhension

Ce projet est développé avec **Claude Code**, un assistant de programmation basé sur l'IA. Son utilisation est un choix assumé : ces outils font désormais partie du métier. Mais l'objectif est d'apprendre à **les piloter**, pas de leur confier le projet.

### Le cycle de travail appliqué à chaque étape

```
 1. Concevoir      →  je définis l'objectif et le résultat attendu
 2. Planifier      →  Claude Code propose un plan, sans rien modifier
 3. Valider        →  je relis le plan, je pose mes questions, je l'ajuste
 4. Réaliser       →  par petites étapes : un fichier ou une fonctionnalité à la fois
 5. Relire         →  je lis chaque modification ligne par ligne avant de l'accepter
 6. Tester         →  validateurs W3C, affichage mobile et ordinateur, accessibilité
 7. Documenter     →  journal de bord : ce qui a été fait, décidé et compris
 8. Enregistrer    →  je réalise moi-même le commit Git
```

### Ce que je fais volontairement sans l'IA

- **Concevoir** : l'arborescence, les maquettes et le contenu sont décidés avant toute ligne de code.
- **Écrire une première version à la main** : la page d'accueil est écrite manuellement, puis seulement relue par l'IA. Elle sert ensuite de modèle aux autres pages.
- **Réécrire pour comprendre** : après chaque fonctionnalité JavaScript générée, je me fais expliquer le code puis je réécris moi-même au moins une fonction.
- **Rédiger mes réalisations professionnelles** : le contenu du portfolio est écrit par moi. L'IA peut corriger ou poser des questions, pas rédiger à ma place.
- **Gérer les versions** : tous les commits et envois vers GitHub sont faits manuellement.

---

## Garde-fous de sécurité

Travailler avec un agent capable de modifier des fichiers et d'exécuter des commandes impose des règles. Elles sont appliquées sur deux niveaux :

| Niveau                     | Fichier                                          | Fonctionnement                                                                                                              |
| -------------------------- | ------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------- |
| **Consignes**              | [`CLAUDE.md`](CLAUDE.md)                         | Règlement du projet lu par l'IA à chaque session : rôle, conventions, méthode, interdits.                                   |
| **Permissions techniques** | [`.claude/settings.json`](.claude/settings.json) | Règles appliquées par l'outil lui-même : certaines actions sont bloquées ou soumises à ma validation, quoi que l'IA décide. |

Principes retenus :

- **Les actions irréversibles restent humaines** : suppression de fichiers, commits et envois vers GitHub.
- **Aucun secret** (mot de passe, clé, jeton) dans le dépôt ni dans les échanges avec l'IA.
- **Aucune donnée interne** de l'entreprise où j'effectue mon alternance n'est publiée ni transmise à l'IA.
- **Git comme filet de sécurité** : un commit avant chaque étape importante, pour pouvoir revenir en arrière.

---

## Critères de qualité

Chaque étape n'est considérée comme terminée que si ces critères sont vérifiés :

- [ ] Aucune erreur au validateur HTML du W3C
- [ ] Aucune erreur au validateur CSS du W3C
- [ ] Affichage correct sur mobile (375 px), tablette (768 px) et ordinateur (1440 px)
- [ ] Score d'accessibilité Lighthouse supérieur ou égal à 90
- [ ] Aucune erreur dans la console du navigateur
- [ ] Site consultable sur Chrome, Firefox et Edge

---

## Structure du dépôt

```
.
├── index.html          # Page d'accueil
├── css/                # Feuilles de style
├── js/                 # Scripts
├── images/             # Images
├── docs/               # Documentation du projet
│   └── journal.md      # Journal de bord
├── .claude/
│   └── settings.json   # Permissions de l'assistant IA
├── CLAUDE.md           # Consignes de l'assistant IA
├── .gitignore          # Fichiers exclus du versionnement
└── README.md           # Ce fichier
```

---

## Feuille de route

- **Phase 1** : mise en place du projet (Git, consignes, permissions, documentation)
- **Phase 2** : conception (contenu, arborescence, maquettes, système de design)
- **Phase 3** : structure des pages en HTML
- **Phase 4** : mise en forme en CSS
- **Phase 5** : interactions en JavaScript
- **Phase 6** : mise en ligne sur GitHub Pages
- **Phase 7** : contenu, mentions légales, préparation de l'épreuve
- **Phase 8** : partie dynamique (PHP, base de données) et nom de domaine personnel
- **Phase 9** : tableau de bord de supervision du site

---

## Documentation

- [`docs/journal.md`](docs/journal.md) : journal de bord, avec ce qui a été réalisé, les décisions prises et ce que j'ai appris à chaque étape.
- [`CLAUDE.md`](CLAUDE.md) : règles de collaboration avec l'assistant IA.
- Historique des commits : chaque modification est décrite selon la convention [Conventional Commits](https://www.conventionalcommits.org/fr/).

---

## Auteur

**Rudy Entraygues**, étudiant en BTS SIO option SISR, en alternance.
