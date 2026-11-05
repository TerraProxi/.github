# Contribuer à TerraProxi

Ces règles s'appliquent à tous les dépôts de l'organisation. Chaque dépôt peut les préciser dans
son propre `CONTRIBUTING.md` ou son `README.md`.

## Avant de commencer

1. Lire le `README.md` du dépôt et, pour le monorepo, `docs/setup.md` (installation) et
   `specs/README.md` (contrats).
2. Ouvrir ou reprendre une **issue** qui décrit le besoin : une issue, une branche, une pull request.
3. Pour une évolution de l'API : **la spec d'abord**. Modifier `specs/` (OpenAPI, JSON Schema,
   scénario Gherkin), puis le code et les tests dans la même pull request.

## Branches

`main` est toujours déployable. On travaille sur une branche dédiée :

| Préfixe | Usage | Exemple |
|---------|-------|---------|
| `feat/` | Nouvelle fonctionnalité | `feat/agenda-producteur` |
| `fix/` | Correction de bug | `fix/heure-messagerie` |
| `spec/` | Évolution des contrats | `spec/notifications` |
| `docs/` | Documentation | `docs/guide-producteur` |
| `chore/`, `ci/` | Outillage, CI, dépendances | `ci/tests-mobile` |

Une branche fusionnée est supprimée.

## Commits

Format [Conventional Commits](https://www.conventionalcommits.org/fr/) :
`<type>(<portée>): <description>` à l'impératif, en minuscules, sans point final, 72 caractères
au plus.

```
feat(api): add producer sales statistics
fix(mobile): read sent_at for message times
docs: describe the backup procedure
```

Types : `feat`, `fix`, `spec`, `docs`, `test`, `refactor`, `perf`, `ci`, `chore`.
Un commit = un changement logique. Jamais de secret, de `.env` ni de fichier généré.

## Pull requests

- Petites et ciblées (moins de 400 lignes de diff quand c'est possible).
- Le modèle de description est rempli : contexte, changements, vérifications, ce qui n'a pas pu être testé.
- La CI doit être verte : lint des specs, typage, tests API, web et mobile, build des images Docker.
- Relue de préférence par un autre membre de l'équipe avant la fusion.
- PR empilées : les fusionner dans l'ordre, chacune vers `main` une fois la précédente fusionnée
  (une PR fusionnée dans sa branche de base n'arrive pas sur `main`).

## Qualité attendue

- TypeScript strict, aucune variable non utilisée, aucun `TODO` ni `console.log` laissé.
- Toute nouvelle route a sa spec, son scénario et ses tests d'intégration.
- Les interfaces respectent la charte (Montserrat, Open Sans, couleurs TerraProxi) et l'accessibilité
  WCAG AA : contrastes, libellés, navigation au clavier.
- Les données personnelles suivent `docs/rgpd.md` : rien de sensible dans les journaux.
