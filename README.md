# keycloak-buildpack-dietelio

Recette de construction (buildpack Scalingo) de **Keycloak 26.7.3** pour
Dietelio : JDK Temurin 21 et Keycloak épinglés et **vérifiés par SHA-256**,
compilation du fournisseur de mots de passe bcrypt, `kc.sh build` avec les
fonctionnalités inutiles retirées, `.profile.d` de démarrage.

Ce dépôt n'est **pas** la source de vérité : la copie de référence vit dans
le dépôt privé de l'application (`iam/buildpack/bin`), avec ses bancs et sa
documentation. Il existe parce que le constructeur de Scalingo clone les
buildpacks cités par `.buildpacks` **sans identifiant**, et ne peut donc pas
lire un dépôt privé. Un contrôle du dépôt principal
(`scripts/check-buildpacks-sync.mjs`) vérifie que les deux copies sont
identiques, octet pour octet, pour l'étiquette citée.

Étiquette citée par `iam/.buildpacks` : `v26.7.3-1`. Une nouvelle version de
Keycloak = une nouvelle étiquette, jamais une étiquette déplacée.

Aucun secret ici. Les variables attendues au build et à l'exécution sont
documentées dans le dépôt principal (`docs/03-api-endpoints.md` §5,
`iam/scalingo.json`).
