# Documentation AIDE

> Règles de rédaction, d’organisation et de vérification de la documentation des projets.

## Rôle et responsabilités

- Préparer les évolutions documentaires au fil du développement ; intégrer la documentation dans `docs/` à la reconstitution depuis un brouillon préparé pendant l’implémentation.
- Organiser les thématiques principales dans les sous-dossiers directement sous `docs/` et créer les niveaux nécessaires à chaque thématique.
- Expliquer chaque sujet dans un document de référence unique et y renvoyer depuis les autres pages.
- Détailler les points qui nécessitent des explications complémentaires.

## Conventions techniques

### Noms et navigation

- À la racine de `docs/`, réserver les fichiers à `README.md` et `index.md` ; aucun document de sujet ne doit s’y trouver.
- Ranger chaque document de sujet dans un sous-dossier thématique pertinent, existant ou créé si nécessaire. Vérifier les sujets et références existants avant d’ajouter un document ; ne pas créer de catégorie fourre-tout.
- Relier chaque thématique depuis le sommaire principal et chaque document depuis le sommaire de sa thématique. Lors d’une réorganisation, identifier les fichiers et liens concernés, puis préserver les preuves historiques selon les règles ci-dessous.
- Nommer sans numéro les dossiers de thématiques directement sous `docs/`, comme `architecture/`. Les numéros restent permis dans les sous-dossiers et fichiers, notamment pour les piliers et étapes des boucles.
- Réserver `index.md` aux sommaires : titres, listes de liens et tableaux de navigation. Chaque entrée contient un lien et, si utile, un libellé bref.
- Placer les explications et commandes dans un document nommé par sujet, accessible depuis le sommaire.

### Rédaction et source de référence

- Commencer chaque document explicatif par une courte citation Markdown (`>`) après son titre principal. Les README et sommaires sont exemptés ; aucune citation supplémentaire n’est exigée dans les sous-sections.
- Utiliser des titres précis et des paragraphes courts. Supprimer répétitions, détails inutiles et formulations superflues.
- Employer « convention technique » pour désigner une règle technique du projet.
- Présenter « Rôle et responsabilités » des README comme une liste de responsabilités, sans renvoi documentaire ni inventaire de scripts ou de fichiers de tests.
- Définir les conventions techniques dans le README concerné. Les guides les expliquent et y renvoient sans les recopier.

### Références et vérifications

- Lors d’un déplacement, actualiser les liens et les renvois aux sections, y compris dans les demandes et cartes. Conserver les chemins écrits comme preuves historiques, les identifiants de commits, les résultats et les verdicts.
- Vérifier les liens du dev-book. Toute exception doit préciser son fichier source, sa cible et son motif avant adoption ; ne pas supposer qu’une exception est configurée.
- Examiner les fichiers suivis ou non ignorés, sans parcourir les copies de worktrees, les dépendances ignorées ou les `.env`.
- Inclure les liens HTML présents dans le Markdown. Signaler les références dynamiques pour examen humain ; ne pas présenter les liens externes ou les liens sortants des fichiers HTML comme vérifiés sans contrôle adapté.
- Relire humainement les titres, citations et paragraphes pour vérifier leur précision, leur concision et l’absence de répétitions.

## Contrôle du projet source

Lorsque le projet fournit `codebase-integrity/scripts/check_docs.py`, exécuter `python3 codebase-integrity/scripts/check_docs.py` selon ses conventions et les règles applicables aux tests lourds. Le contrôle décrit dans la documentation source vérifie les noms, sommaires et citations de `docs/`, ainsi que les liens locaux du Markdown et leurs renvois aux sections Markdown ou HTML. Il ne vérifie ni les destinations externes ni les liens sortants des fichiers HTML et signale les références dynamiques. Vérifier la commande et ses capacités dans le projet concerné ; ne pas supposer qu’elles sont identiques ailleurs.
