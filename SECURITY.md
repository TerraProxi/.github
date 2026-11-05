# Politique de sécurité

## Signaler une vulnérabilité

**Ne publiez pas de faille dans une issue publique.**

Utilisez le signalement privé de GitHub : onglet **Security** du dépôt concerné, puis
**Report a vulnerability**. Indiquez :

- le dépôt et la version (commit) concernés ;
- la description de la faille et son impact (données exposées, action possible) ;
- les étapes pour la reproduire.

L'équipe accuse réception sous 5 jours ouvrés, puis vous tient informé de la correction.
Merci de nous laisser le temps de corriger avant toute divulgation.

## Périmètre

| Dépôt | Suivi |
|-------|-------|
| [TerraProxi](https://github.com/TerraProxi/TerraProxi) (API, site web, application mobile) | ✅ branche `main` |
| [Prototype-Front](https://github.com/TerraProxi/Prototype-Front) | ❌ archivé, non maintenu |

## Ce que nous protégeons

- Les comptes (mots de passe hachés avec bcrypt, sessions révocables, protection contre la force brute).
- Les paiements : traités uniquement par Stripe, aucune donnée de carte ne transite par nos serveurs.
- Les données personnelles (RGPD) : hébergement en France, export et suppression à la demande.

Les mesures techniques sont détaillées dans `docs/rgpd.md` et `specs/decisions/` du monorepo.
