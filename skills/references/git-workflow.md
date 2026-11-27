# Référence du workflow Git AIDE

Cette documentation rassemble les informations de `docs/git-workflow/` du projet AI Development Engineering. Les conventions et autorisations du projet concerné et les instructions explicites de l’utilisateur restent déterminantes ; vérifier les contrôles réellement disponibles avant de les annoncer.

## Branches et contributions

- `develop` rassemble les contributions intégrées ; `master` représente la production ; `main` est historique.
- Chaque demande utilise dès l’analyse un worktree dédié et une branche `demands/<identifiant>-<sujet>` issue de `develop` local vérifié. Les tâches restent typées par couche technique, sans worktree de couche associé.
- Les tâches sont réalisées et commitées sur cette branche selon leurs dépendances ; en consolidation, chaque changement est soumis au verdict humain avant son commit ; en développement, la vérification humaine intervient après les commits de tâches. Le worktree et sa branche sont réutilisés pour une reprise de la même demande ; un arbre propre ne prouve pas sa disponibilité.
- Les guides du projet source peuvent encore décrire l’ancien modèle : vérifier leur état et signaler les divergences jusqu’à leur alignement.

## Messages de commit

Un commit de tâche utilise `type(CARTE): changement`. Le titre est en français, avec un verbe à l’infinitif, une description précise et aucun point final. Les titres provisoires `wip`, `fixup`, `squash` et « corrections diverses » sont refusés.

Les types sont `feat` (fonctionnalité), `fix` (correction), `docs` (documentation), `refactor` (réorganisation), `test`, `perf`, `build`, `ci`, `style` et `chore`. Le type reflète le changement principal ; le scope identifie la carte. La documentation source utilise les préfixes `API`, `WEB`, `BO`, `UX` et `OPS` suivis d’au moins trois chiffres : d’autres projets peuvent avoir d’autres préfixes.

Une ligne unique `Demande : DEM-NNN` rattache un commit de carte à sa demande. Une ligne vide sépare le titre du corps ; le corps peut expliquer une motivation ou une contrainte sans recopier les preuves ou les fichiers du diff. Le scope `docs(DEM-NNN)` est réservé aux traces Markdown dans `dev-book/demand/` et `dev-book/tasks/` ; toute ligne de demande présente doit correspondre au scope. Les documents référencés et le rattachement de la carte doivent être uniques et cohérents. Les traces de cherry-pick sont conservées ; aucun `!` ni attribution supplémentaire n’est imposé.

```text
ci(OPS-075): vérifier les messages de chaque commit de la PR

Détecter aussi les titres invalides au milieu d'une série.

Demande : DEM-024
```

## Pull requests et contrôles

Une PR présente la demande validée vers `develop`. Son titre suit `type(DEM-NNN): description`, avec le type correspondant au résultat principal et une description respectant les règles de titre ci-dessus. Son corps expose le problème, le résultat, les vérifications et leurs limites.

Avant ouverture, vérifier les verdicts, les commits et les contrôles de toute la contribution par rapport à la base d’intégration vérifiée. Les messages et références sont examinés sur toute la plage, sans contrôle rétroactif hors plage ; les commits de fusion sont refusés. Une erreur obligatoire bloque la contribution. Une réussite technique ne remplace pas la revue humaine ; un contrôle inconnu ne vaut pas réussite.

Contrôler distinctement les commits de contribution et le titre de PR ou le message de squash préparé. Pour les contributions, un scope `DEM-NNN` n’est admis que pour l’exception documentaire décrite ci-dessus, avec vérification des fichiers et références. Un vérificateur disponible pour le titre ou le message préparé est bloquant en cas d’échec ; à défaut, l’humain vérifie leur conformité avant fusion. Le titre de PR ne garantit pas le message effectivement saisi lors du squash.

Pour `DEM-028`, `feat(OPS-075): vérifier les messages` est un titre de tâche acceptable ; `feat(DEM-028): vérifier les messages` est refusé en contribution, mais peut convenir à la PR ou au squash. `docs(DEM-028): documenter la demande` est acceptable en contribution uniquement pour les traces autorisées, et peut aussi convenir à la PR ou au squash si la documentation est le résultat principal. Un type inconnu, une description absente ou un identifiant de demande incohérent sont refusés.

Avant d’imposer une protection de métadonnées, vérifier son application aux commits de contribution et au squash : une règle qui n’accepte que le scope de demande peut bloquer les commits de carte. Les protections et contrôles effectifs dépendent du dépôt.

La contribution de développement ne modifie pas Codebase Integrity. Une consolidation relie ses corrections aux conventions et aux contrôles ajoutés ou renforcés ; une consolidation sans correction de code est justifiée sans imposer un nouveau contrôle. Les suppressions et déplacements sont également examinés. Les demandes de types contradictoires ou mélangés et les références ambiguës sont refusées.

La documentation source décrit des commandes de contrôle propres à son projet et un amorçage exceptionnel avec SHA approuvé. Leur chemin et leur disponibilité dépendent de la version du projet : consulter sa documentation et ses scripts plutôt que les supposer transposables. Les contrôles lourds relèvent des règles communes de lancement manuel.

## Intégration et suivi

Chaque demande de développement ou de consolidation ajoute un seul commit à `develop`. Préparer le message de squash avec le même format de titre que la PR, par exemple `feat(DEM-028): isoler les worktrees et environnements par demande`. Son corps précise le besoin et le résultat apporté, avec une référence à la demande qui conserve la provenance des commits de cartes.

À la livraison, l’humain exécute les tests CI/CD préalables puis effectue le **Squash and merge** de la PR vers `develop`, avec le message préparé, après réussite des contrôles et satisfaction des protections. Si le squash est indisponible, signaler le blocage. Une demande limitée à la PR s’arrête à son ouverture. Une correction fonctionnelle nécessite une nouvelle validation.

Après fusion, vérifier le message et le SHA intégrés distants et rapprocher le HEAD contrôlé de la PR et son diff cumulé du commit intégré ; tracer ce lien avec les SHA des cartes. Signaler toute divergence du message : ce contrôle intervient après la fusion. Une équivalence de patch seule ne prouve pas l’intégration. Actualiser `develop` uniquement si son checkout est libre, propre et si l’opération est autorisée. Préserver les autres worktrees, les données et les `.env`.

Ne pas supprimer automatiquement le worktree ou la branche de demande. La promotion vers `master` exige une demande distincte ; une PR intégrée ne prouve pas un déploiement.

## Versions et releases

La documentation source ne fixe pas de politique de versionnement sémantique, de tags ou de changelog automatique. Le type du commit ne détermine donc pas à lui seul une version. Le périmètre et la numérotation d’une release, ainsi que le circuit de correctif urgent, restent à définir dans le projet concerné.
