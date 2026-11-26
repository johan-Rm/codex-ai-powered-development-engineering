# Référence du workflow Git AIDE

Cette documentation rassemble les informations de `docs/git-workflow/` du projet AI Development Engineering. Les conventions et autorisations du projet concerné et les instructions explicites de l’utilisateur restent déterminantes ; vérifier les contrôles réellement disponibles avant de les annoncer.

## Branches et contributions

- `develop` rassemble les contributions intégrées ; `master` représente la production ; `main` est historique.
- Les branches durables `layers/<couche>` correspondent aux worktrees `worktree/<couche>`. Une seule mission écrit dans une couche ; un arbre propre ne suffit pas à prouver sa disponibilité.
- Une demande est reconstituée dans le dossier principal sur `demands/<identifiant>`, depuis `develop` vérifié. Les commits validés sont repris par cherry-pick avec leur provenance, dans l’ordre des dépendances, sans copier du travail non commité ni fusionner les branches de couche. Un conflit qui modifie le résultat validé nécessite une décision humaine.
- La documentation source indique encore que les commits sont créés après validation humaine. Les consignes AIDE actuelles prévoient un commit local par tâche à l’implémentation, puis une vérification humaine : cette divergence reste à corriger dans la source.

## Messages de commit

La convention AIDE documentée utilise `type(CARTE): changement`. Le titre est en français, avec un verbe à l’infinitif, une description précise et aucun point final. Les titres provisoires `wip`, `fixup`, `squash` et « corrections diverses » sont refusés.

Les types sont `feat` (fonctionnalité), `fix` (correction), `docs` (documentation), `refactor` (réorganisation), `test`, `perf`, `build`, `ci`, `style` et `chore`. Le type reflète le changement principal ; le scope identifie la carte. La documentation source utilise les préfixes `API`, `WEB`, `BO`, `UX` et `OPS` suivis d’au moins trois chiffres : d’autres projets peuvent avoir d’autres préfixes.

Une ligne unique `Demande : DEM-NNN` rattache un commit de carte à sa demande. Une ligne vide sépare le titre du corps ; le corps peut expliquer une motivation ou une contrainte sans recopier les preuves ou les fichiers du diff. Le scope `docs(DEM-NNN)` est réservé aux traces Markdown dans `dev-book/demand/` et `dev-book/tasks/` ; toute ligne de demande présente doit correspondre au scope. Les documents référencés et le rattachement de la carte doivent être uniques et cohérents. Les traces de cherry-pick sont conservées ; aucun `!` ni attribution supplémentaire n’est imposé.

```text
ci(OPS-075): vérifier les messages de chaque commit de la PR

Détecter aussi les titres invalides au milieu d'une série.

Demande : DEM-024
```

## Pull requests et contrôles

Une PR présente la demande reconstituée vers `develop`. Son titre exprime en français le résultat global et se termine par `(DEM-NNN)` ; aucun préfixe Conventional Commit n’est imposé. Son corps expose le problème, le résultat, les vérifications et leurs limites.

Avant ouverture, vérifier les verdicts, les commits et les contrôles de toute la contribution par rapport à la base d’intégration vérifiée. Les messages et références sont examinés sur toute la plage, sans contrôle rétroactif hors plage ; les commits de fusion sont refusés. Une erreur obligatoire bloque la contribution. Une réussite technique ne remplace pas la revue humaine ; un contrôle inconnu ne vaut pas réussite.

La contribution de développement ne modifie pas Codebase Integrity. Une consolidation relie ses corrections aux conventions et aux contrôles ajoutés ou renforcés ; une consolidation sans correction de code est justifiée sans imposer un nouveau contrôle. Les suppressions et déplacements sont également examinés. Les demandes de types contradictoires ou mélangés et les références ambiguës sont refusées.

La documentation source décrit des commandes de contrôle propres à son projet et un amorçage exceptionnel avec SHA approuvé. Leur chemin et leur disponibilité dépendent de la version du projet : consulter sa documentation et ses scripts plutôt que les supposer transposables. Les contrôles lourds relèvent des règles communes de lancement manuel.

## Intégration et suivi

Pour l’étape 06 de livraison de développement ou de consolidation, les autorisations du `AGENTS.md` réservent les tests CI/CD préalables et la fusion à l’humain. L’intégration AIDE utilise **Rebase and merge** vers `develop`, sans squash ni commit de fusion. Vérifier la méthode, les protections, les contrôles, le HEAD et la cible ; si la méthode est indisponible, signaler le blocage. Une demande limitée à la PR n’autorise pas sa fusion. Une correction fonctionnelle nécessite une nouvelle validation.

Après fusion, vérifier l’état intégré, le SHA résultant et sa présence dans `develop` distant ; tracer la correspondance des commits réécrits. Une équivalence de patch seule ne prouve pas l’intégration. Actualiser ensuite `develop` et les seules couches libres, propres et sans travail inédit, selon les autorisations du projet. Un rebase local sans commit à rejouer est limité aux cas explicitement autorisés après preuve d’intégration et de provenance. Préserver les branches occupées, les worktrees, les données et les `.env` ; ne pas utiliser stash, reset destructif ou force-push pour obtenir l’alignement.

Vérifier l’égalité des SHA avant clôture et ne supprimer que les branches temporaires livrées dont l’intégration et l’absence d’autre travail sont établies. Une couche sale ou occupée bloque la clôture. La promotion vers `master` exige une demande distincte ; une PR intégrée ne prouve pas un déploiement.

## Versions et releases

La documentation source ne fixe pas de politique de versionnement sémantique, de tags ou de changelog automatique. Le type du commit ne détermine donc pas à lui seul une version. Le périmètre et la numérotation d’une release, ainsi que le circuit de correctif urgent, restent à définir dans le projet concerné.
