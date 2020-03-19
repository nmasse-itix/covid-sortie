# Attestation de sortie pendant le confinement

Un formulaire en ligne pour simplifier l'attestation de sortie pendant le confinement.

J'ai fait ceci dans le but de m'aider moi meme et mes amis, mais vu que vous êtes tous chez vous aujourd'hui ça a forcément dégénéré et vous avez surchargé mon serveur :D

Si vous avez des doutes pour vos données; vous pouvez demander à un ami développeur son avis (pas de suspense, il vous dira que tout est ok).

La page n'envoie aucune info nulle part. Toutes les infos restent dans votre navigateur, l'attestation est générée directement dans celui ci et non sur un serveur distant. (0 cloud !)

## Soyez prudents

Restez au maximum chez vous, suivez les infos mises a jour sur [le site du gouvernement](https://www.gouvernement.fr/info-coronavirus).

## Déploiement sur OpenShift

```sh
oc new-project covid-sortie
oc new-app openshift/nginx~https://github.com/nmasse-itix/covid-sortie --name=covid-sortie
oc create route edge covid-sortie --service=covid-sortie --insecure-policy=Redirect --hostname=covid-sortie.apps-crc.testing
```
