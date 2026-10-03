# fingames-site

Le site public de **FinGames** — la page d'accueil, la politique de
confidentialité, les conditions d'utilisation, les mentions légales et le support.

## Ce dépôt est ENGENDRÉ, jamais édité à la main

Le contenu vient de `src/legal/` dans le dépôt de l'application. Pour le mettre
à jour :

```bash
cd ~/Developer/FINGAMES/FinGames
npm run site                      # régénère site/
cp -R site/. ~/Developer/FINGAMES/fingames-site/
cd ~/Developer/FINGAMES/fingames-site
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
site lui-même, et le script local gère le thème et le menu —
ni mesure d'audience, ni requête vers un tiers. Instagram et TikTok sont de
simples liens, suivis seulement si l'on clique. Le site d'une application qui
ne collecte rien ne peut pas transmettre l'adresse IP de ses visiteurs à un tiers.

Les sources de présentation sont dans `site-src/home.mts` et
`site-src/product.css` du dépôt applicatif. Le générateur conserve les textes
légaux communs à l’application. Les routes FR/EN historiques sont conservées.

Les captures du 3 octobre 2026 proviennent de l’application actuelle exécutée
localement en React Native Web. Leur provenance et la reproduction sont décrites
dans `site-src/current/README.md` du dépôt applicatif. Le site les sert en WebP
400/800 px et précise que le rendu iOS peut différer.

```bash
node scripts/capture-site-app.mts          # app locale requise
node scripts/prepare-current-site-images.mts
node scripts/prepare-og-image.mts
npm run site
node scripts/check-site.mts               # Chrome requis
npx vitest run src/legal/site.test.ts
```

Le site ne charge aucune ressource tierce. Son JavaScript gère le thème et le
menu mobile ; le contenu reste accessible sans JavaScript. Les abonnements sont
présentés sans prix ni lien App Store non confirmé.
