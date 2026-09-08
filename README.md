# fingames-site

Les pages légales publiques de **FinGames** — politique de confidentialité,
conditions d'utilisation et support.

## Ce dépôt est ENGENDRÉ, jamais édité à la main

Le contenu vient de `src/legal/` dans le dépôt de l'application. Pour le mettre
à jour :

```bash
cd ~/Developer/FINMATH/FinMath
npm run site                      # régénère site/
cp -R site/. ~/Developer/FINMATH/fingames-site/
cd ~/Developer/FINMATH/fingames-site
git add -A && git commit -m "Mise à jour des documents légaux" && git push
```

Un test (`src/legal/site.test.ts`) refuse que le site publié diverge de
l'application. Corriger un texte ici sans le corriger là-bas serait invisible —
et c'est la version que personne n'a relue qui finirait publiée.

## URL servies

| Page | URL |
|---|---|
| Accueil | https://aaron-ada91.github.io/fingames-site/ |
| Confidentialité | https://aaron-ada91.github.io/fingames-site/privacy.html |
| Conditions | https://aaron-ada91.github.io/fingames-site/terms.html |
| Support | https://aaron-ada91.github.io/fingames-site/support.html |

Aucune ressource tierce n'est chargée : ni police distante, ni script, ni
mesure d'audience. Le site d'une application qui ne collecte rien ne peut pas
transmettre l'adresse IP de ses visiteurs à un tiers.
