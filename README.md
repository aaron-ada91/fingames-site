# fingames-site

Le site public de **FinGames** — la page d'accueil, la politique de
confidentialité, les conditions d'utilisation, les mentions légales et le support.

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

Le site est servi par GitHub Pages sous le domaine **https://fingames.app**
(fichier `CNAME`, engendré lui aussi) ; l'ancienne adresse github.io y redirige.
Chaque page existe en anglais (l'URL donnée aux magasins) et en français.

| Page | Anglais | Français |
|---|---|---|
| Accueil | https://fingames.app/ | https://fingames.app/index.fr.html |
| Confidentialité | https://fingames.app/privacy.html | https://fingames.app/privacy.fr.html |
| Conditions | https://fingames.app/terms.html | https://fingames.app/terms.fr.html |
| Mentions légales | https://fingames.app/legal.html | https://fingames.app/legal.fr.html |
| Support | https://fingames.app/support.html | https://fingames.app/support.fr.html |

Aucune ressource tierce n'est chargée : polices et images sont servies par le
site lui-même, et le seul script, écrit dans la page, retient le thème choisi —
ni mesure d'audience, ni requête vers un tiers. Instagram et TikTok sont de
simples liens, suivis seulement si l'on clique. Le site d'une application qui
ne collecte rien ne peut pas transmettre l'adresse IP de ses visiteurs à un tiers.

Les images du site se préparent à part, quand les captures changent :
`python3 scripts/prepare-site-images.py` (captures détourées) et
`node scripts/prepare-og-image.mts` (aperçu partagé 1200 × 630), puis `npm run site`.
