# Des autocollants pour les espèces d'oiseaux actuelles du monde

<img src="previews/header.webp" alt="huashu-bird-sticker: specimen drawer, body-size lineup and family plates" width="100%">

[English](README.md) · [简体中文](README.zh-Hans.md) · [繁體中文](README.zh-Hant.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Español](README.es.md) · **Français** · [Deutsch](README.de.md) · [Português](README.pt.md) · [Русский](README.ru.md) · [العربية](README.ar.md)

<a href="https://birdalbum.com/fr/?utm_source=github&utm_medium=readme&utm_campaign=bird-sticker"><img src="previews/birdalbum.webp" alt="Bird Album : tous les oiseaux du monde, un autocollant pour chacun. birdalbum.com" width="100%"></a>

**Découvrez toute la bibliothèque en situation sur [birdalbum.com](https://birdalbum.com/fr/?utm_source=github&utm_medium=readme&utm_campaign=bird-sticker).** Bird Album est un guide des oiseaux gratuit construit sur ces autocollants : cherchez n'importe quelle espèce par son nom dans 15 langues, voyez où elle vit et à quels mois on peut la croiser, et ouvrez une carte de 8 171 sites d'observation qui montre ce que les gens observent ce mois-ci à chacun.

Plus de 11 000 espèces d'oiseaux réparties en 45 ordres et 249 familles, d'après [AviList v2026](https://www.avilist.org/), la liste mondiale unifiée publiée pour la première fois en 2025 (la liste de l'IOC a pris fin à son profit). Toutes les espèces qu'AviList ne signale pas comme éteintes ou possiblement éteintes sont incluses, plus 43 espèces signalées qui avaient déjà un autocollant : éteintes, éteintes à l'état sauvage, possiblement éteintes ou, pour deux d'entre elles, autrefois éteintes à l'état sauvage puis réintroduites (voir `extinctionStatus`). Chaque espèce a un autocollant. Chaque espèce est accompagnée de données structurées : taxonomie, noms dans jusqu'à 43 langues, identifiants dans d'autres bases de données et ce à partir de quoi chaque autocollant a été généré.

> **La version 2.0 a fait passer la taxonomie de l'IOC 15.2 à AviList v2026.** 82 espèces ont changé de nom scientifique (donc d'`id` et de chemin d'autocollant), 91 anciennes espèces sont désormais des sous-espèces d'une autre espèce et 30 nouvelles espèces ont été scindées. Tous les changements sont listés dans [`data/crosswalk-ioc15.2-avilist2026.csv`](data/crosswalk-ioc15.2-avilist2026.csv), et chaque fiche conserve son ancien identifiant IOC dans `previous`. Voir le [CHANGELOG](CHANGELOG.md).

![40 autocollants de 15 ordres d’oiseaux](previews/hero.webp)

**Générés par IA, et chaque fichier l'indique.** Les métadonnées XMP/IPTC de chaque autocollant précisent qu'il s'agit d'une illustration générée par IA et non d'une photographie (type de source numérique IPTC `trainedAlgorithmicMedia`), le système d'IA utilisé, qu'elle n'a pas été vérifiée par des experts et peut contenir des erreurs, la licence et un lien vers ce dépôt.

**Licence en bref :** les autocollants sont sous licence [CC BY 4.0](LICENSE.md) : vous pouvez les utiliser pour tout, y compris en usage commercial, les modifier et les redistribuer, à condition de citer huashu-bird-sticker avec un lien vers ce dépôt. Les données sont sous licence MIT, et les éléments provenant de tiers sont listés dans [NOTICE](NOTICE.md).

## Utiliser un autocollant en une ligne

Chaque autocollant est servi par le CDN jsDelivr (CORS activé) : vous pouvez l’insérer directement dans une page :

```html
<img src="https://cdn.jsdelivr.net/gh/alchaincyf/huashu-bird-sticker@main/stickers/Coraciiformes/Alcedinidae/Alcedo_atthis.webp" alt="Martin-pêcheur d’Europe" width="240">
```

Pour chercher un oiseau par son nom, chargez [`data/stickers.json`](data/stickers.json) (2,7 Mo : nom scientifique, anglais et chinois, chemin du fichier et page de l’espèce sur birdalbum.com pour chaque espèce ; les 91 autocollants de sous-espèces sont listés sous `forms` dans `data/species.json`). Les noms en 43 langues sont dans [`data/names.csv`](data/names.csv).

```js
const idx = await (await fetch("https://cdn.jsdelivr.net/gh/alchaincyf/huashu-bird-sticker@main/data/stickers.json")).json();
const s = idx.stickers.find(x => x.en === "Eurasian Magpie");
const url = idx.cdn + s.file;  // URL de l’autocollant
```

Créditez-le à côté de l’image ainsi, avec le lien vers la page de l’espèce :

`Illustration: [Bird Album](https://birdalbum.com/birds/common-kingfisher/) / [huashu-bird-sticker](https://github.com/alchaincyf/huashu-bird-sticker), CC BY 4.0`

## L’oiseau du jour

Un oiseau différent chaque jour sur votre profil GitHub, blog ou page Notion. Collez cette ligne dans n’importe quel Markdown (`?lang=` pour 15 langues, `?theme=dark` ou `auto`) :

```markdown
[![L’oiseau du jour](https://birdalbum.com/today.svg?lang=fr)](https://birdalbum.com/today/?lang=fr)
```

[![L’oiseau du jour](https://birdalbum.com/today.svg?lang=fr)](https://birdalbum.com/today/?lang=fr)

## Galerie

Dix-huit des groupes les plus colorés et les plus caractéristiques, 24 autocollants pour chacun, choisis pour que deux d'entre eux ne se ressemblent jamais. Tous les autocollants montrés ici atteignent le seuil de qualité.

### Colibris · *Trochilidae* — 361 espèces

![Colibris](previews/families/trochilidae.webp)

### Perroquets et cacatoès · *Psittaciformes* — 391 espèces

![Perroquets et cacatoès](previews/families/parrots.webp)

### Martins-pêcheurs · *Alcedinidae* — 123 espèces

![Martins-pêcheurs](previews/families/alcedinidae.webp)

### Guêpiers, rolliers et motmots · *Meropidae* · *Coraciidae* · *Brachypteraciidae* · *Momotidae* · *Todidae* — 69 espèces

![Guêpiers, rolliers et motmots](previews/families/coraciiformes.webp)

### Toucans et barbus · *Ramphastidae* · *Capitonidae* · *Semnornithidae* · *Megalaimidae* · *Lybiidae* — 132 espèces

![Toucans et barbus](previews/families/toucans.webp)

### Paradisiers et jardiniers · *Paradisaeidae* · *Ptilonorhynchidae* — 67 espèces

![Paradisiers et jardiniers](previews/families/paradisaeidae.webp)

### Brèves · *Pittidae* — 46 espèces

![Brèves](previews/families/pittidae.webp)

### Tangaras · *Thraupidae* — 392 espèces

![Tangaras](previews/families/thraupidae.webp)

### Soui-mangas et dicées · *Nectariniidae* · *Dicaeidae* — 207 espèces

![Soui-mangas et dicées](previews/families/nectariniidae.webp)

### Cotingas et manakins · *Cotingidae* · *Pipridae* — 120 espèces

![Cotingas et manakins](previews/families/cotingas.webp)

### Faisans et perdrix · *Phasianidae* — 185 espèces

![Faisans et perdrix](previews/families/phasianidae.webp)

### Canards, oies et cygnes · *Anatidae* — 164 espèces

![Canards, oies et cygnes](previews/families/anatidae.webp)

### Pigeons et tourterelles · *Columbidae* — 338 espèces

![Pigeons et tourterelles](previews/families/columbidae.webp)

### Astrilds et capucins · *Estrildidae* — 138 espèces

![Astrilds et capucins](previews/families/estrildidae.webp)

### Geais et pies · *Corvidae* — 135 espèces

![Geais et pies](previews/families/corvidae.webp)

### Ictéridés du Nouveau Monde (carouges, orioles, caciques) · *Icteridae* — 107 espèces

![Ictéridés du Nouveau Monde (carouges, orioles, caciques)](previews/families/icteridae.webp)

### Calaos · *Bucerotidae* — 64 espèces

![Calaos](previews/families/bucerotidae.webp)

### Étourneaux et mainates · *Sturnidae* — 118 espèces

![Étourneaux et mainates](previews/families/sturnidae.webp)

### Un de chaque ordre

![Un de chaque ordre](previews/orders.webp)

## Contenu

| | |
|---|---|
| `stickers/<Order>/<Family>/<Genus_species>.webp` | Un autocollant transparent avec contour blanc par espèce, d'environ 1 000 px sur le grand côté. Les `<Genus_species>.<subspecies>.webp` sont 91 autocollants supplémentaires de sous-espèces qui étaient auparavant des espèces distinctes |
| `data/species.json` | Une fiche par espèce, le jeu de données complet : taxonomie, noms, identifiants, aire de répartition et sous-espèces, mesures corporelles et écologie, statut de conservation, autocollant et sa provenance. Description des champs : [data/README.md](data/README.md) |
| `data/crosswalk-ioc15.2-avilist2026.csv` | Comment chaque espèce de l'IOC 15.2 correspond à AviList v2026 : identique, renommée, regroupée, scindée |
| `data/species.csv` | La même chose, mise à plat pour les tableurs |
| `data/names.csv` | Les noms dans 43 langues (46 colonnes : le chinois, le français et le portugais ont chacun deux variantes) |
| `data/languages.json` | Les codes de langue et la colonne multilingue de l'IOC dont chacun provient |
| `data/field-guide.zh-Hans.json` | Notes de guide de terrain en chinois simplifié (aspect, critères de terrain, sexes et âges, espèces proches) pour 1 596 espèces, CC BY-SA 4.0 |

Voici à quoi ressemble une fiche (noms abrégés) :

```json
{
  "id": "Accipiter_nisus",
  "scientificName": "Accipiter nisus",
  "authority": "(Linnaeus, 1758)",
  "taxonomy": {"system": "AviList v2026", "seq": 3097, "order": "Accipitriformes", "family": "Accipitridae", "genus": "Accipiter"},
  "names": {"en": "Eurasian Sparrowhawk", "zh-Hans": "雀鹰", "ja": "ハイタカ", "es": "Gavilán común", "fr": "Épervier d'Europe", "…": "…"},
  "ids": {"ebird": "eurspa1", "avibase": "avibase-DB376A66", "wikidata": "Q25380", "gbif": "2480637", "inaturalist": 5106},
  "range": {"text": "lowland to treeline montane forest, open woodland, and urban and suburban parks, from Europe eastward to …", "…": "…"},
  "subspecies": [{"name": "nisus", "authority": "(Linnaeus, 1758)", "range": "breeds Europe to Türkiye and Siberia; winters to Africa"}, "…"],
  "traits": {"massG": 220.8, "wingMm": 207.4, "tailMm": 155.5, "habitat": "Forest", "migration": "partially migratory", "trophicNiche": "Vertivore", "…": "…"},
  "conservation": {"iucn": "LC", "cites": "II", "chinaProtection": "Class II"},
  "taxonConcept": "same",
  "sticker": {
    "file": "stickers/Accipitriformes/Accipitridae/Accipiter_nisus.webp",
    "kind": "ai-illustration",
    "reviewScore": 91,
    "meetsQualityBar": true,
    "license": "CC-BY-4.0",
    "reference": {"type": "photo", "page": "https://commons.wikimedia.org/wiki/File:…", "author": "Dion Art", "license": "CC BY-SA 4.0"}
  }
}
```

## Couverture

- Noms : l'anglais (AviList) couvre toutes les espèces. Les autres langues viennent de la liste multilingue de l'IOC et ne sont conservées que là où le concept d'espèce n'a pas changé ; pour les 129 espèces dont les limites ont changé (regroupements et scissions) ou qui sont nouvelles, un ancien nom peut désigner un autre ensemble d'oiseaux, nous l'avons donc omis plutôt que de deviner. Le chinois simplifié couvre 10 947 espèces (chaque espèce modifiée a été vérifiée à la main) ; le français, l'espagnol, l'allemand, le russe, le japonais et le chinois traditionnel dépassent 94 %. Le coréen, l'arabe, le thaï, le persan et quelques autres ne couvrent que de quelques centaines à environ mille espèces, car c'est ce que contient la liste de l'IOC. Voir `data/names.csv`.
- Identifiants : eBird 10 983 et Avibase 11 011, tous deux repris d'AviList ; Wikidata 10 757, GBIF 10 477.
- Autocollants : les 11 011 espèces, plus 91 autocollants de sous-espèces, soit 11 102 fichiers au total.

## Comment les autocollants ont été faits, et leur qualité

Les 11 102 fichiers d'autocollants sont des illustrations générées par IA. Pour chaque espèce, nous avons trouvé des photos de référence (depuis novembre 2026, quand nous avons pu en trouver, une planche de photos de plusieurs photographes), dessiné l'autocollant avec GPT-image, l'avons agrandi puis détouré. Pour qui veut faire quelque chose de semblable, les prompts, les règles de pose et les critères d’évaluation sont dans [docs/how-the-stickers-are-made.md](docs/how-the-stickers-are-made.md) (en anglais).

Chaque autocollant a ensuite été noté par un relecteur IA distinct. En novembre 2026, nous avons réexaminé tous les autocollants selon un critère plus strict, comme des planches de guide de terrain : un autocollant ne réussit la relecture que si chacun des cinq critères — identification, plumage, bec et œil, pattes et pieds, proportions — obtient au moins 3 sur 4, si l'identification obtient 4 et si le relecteur l'accepterait comme planche de guide de terrain. 77 autocollants l'ont réussie tels quels ; les 11 025 autres ont été générés à nouveau jusqu'à ce qu'une nouvelle version la réussisse.

- **Les 11 102 atteignent notre seuil de qualité** (`"meetsQualityBar": true`) : tous ont réussi la relecture plus stricte décrite ci-dessus. Le relecteur est une IA, pas un spécialiste des oiseaux : réussir ne veut donc pas dire qu'un autocollant est sans erreur ; voir le [ticket n° 1](../../issues/1) et le [ticket n° 3](../../issues/3) pour les types d'erreurs relevées par des ornithologues amateurs.
- **Certains ont été générés à partir d’une description écrite seulement**, sans photo de référence (`"reference": null` dans `data/species.json` ; le nombre figure dans [data/README.md](data/README.md#reference-photos)). Ils risquent davantage de contenir des erreurs que les stickers comparés à une photo. Sur [birdalbum.com](https://birdalbum.com/), la page de l’espèce porte un avertissement supplémentaire pour ces stickers.

Ce sont des illustrations, pas des planches de guide de terrain. Voyez-les comme une image sympathique de l'oiseau, et consultez un guide de terrain avant de vous fier à un détail fin. Si vous repérez une erreur, [ouvrez un ticket](../../issues/new/choose) : les corrections des ornithologues amateurs sont la contribution la plus précieuse que ce projet puisse recevoir.

**Vous connaissez bien un groupe d’oiseaux ?** [Relisez une famille](../../issues/new?template=family-review.yml) et dites-nous quels stickers sont faux. Chaque sticker signalé est régénéré et revu, et votre nom figure dans [CONTRIBUTORS.md](CONTRIBUTORS.md).

## À propos des photos de référence

**À quoi sert une référence.** Un autocollant montre à quoi ressemble une espèce : les couleurs et les motifs du plumage, le bec, l'œil, les pattes et les proportions. Ce sont des faits sur l'oiseau, les mêmes qu'un guide de terrain décrit avec des mots. Une description écrite ne suffit souvent pas au modèle d'image pour les rendre correctement ; nous utilisons donc des photos de référence.

**Comment nous l'utilisons.** Pour chaque espèce, on montre au modèle d'image une ou plusieurs photos de référence avec une description écrite des critères d'identification, et il dessine une nouvelle illustration. La façon dont les photos ont servi dépend de la date de l'autocollant. Les premiers autocollants, générés avant novembre 2026, s'appuyaient sur une photo par espèce, et l'apparence de l'oiseau comme sa posture sur cette photo servaient de référence. Depuis novembre 2026, les photos servent uniquement à vérifier l'apparence de l'oiseau ; nous ne reprenons ni la posture, ni la composition, ni l'arrière-plan, ni la lumière de la photo. Chaque oiseau est dessiné dans une posture standard fixée par nous, sur un fond uni (debout et de profil pour la plupart des groupes ; les oiseaux qui nagent, ceux qui volent et quelques autres groupes ont leurs propres postures). Quand nous avons pu en trouver, les photos proviennent de plusieurs photographes, afin qu'un autocollant reflète l'espèce plutôt qu'une image en particulier (6 369 autocollants ont été faits avec une planche de plusieurs images). Depuis, tous les premiers autocollants sauf 77 ont été générés à nouveau de cette façon ; ces 77 ont réussi tels quels la relecture plus stricte. Un relecteur distinct vérifie ensuite le dessin au regard des critères d'identification. Ce dépôt ne contient aucune photo de référence.

**Crédits et retrait.** Les photos de référence que nous avons notées pour chaque autocollant (page et, quand ils sont connus, auteur et licence) sont listées dans `sticker.reference`, dans `data/species.json` ; les autocollants générés à partir d'une description écrite seulement ont `"reference": null`. Une répartition selon la licence des photos de référence se trouve dans [data/README.md](data/README.md#reference-photos). Si l'une de vos photos a servi de référence et que vous préférez qu'elle ne le soit pas, [faites une demande de retrait](../../issues/new?template=takedown.yml) : nous remplacerons l'autocollant sous 7 jours.

## Utilisation

Les fichiers bruts peuvent être chargés directement :

```
https://raw.githubusercontent.com/alchaincyf/huashu-bird-sticker/main/stickers/Accipitriformes/Accipitridae/Accipiter_nisus.webp
```

```python
import json
species = json.load(open("data/species.json"))["species"]
by_name = {s["scientificName"]: s for s in species}
print(by_name["Pica pica"]["names"]["ja"], by_name["Pica pica"]["sticker"]["file"])
```

Le dépôt pèse environ 700 Mo. Pour ne récupérer que les données et quelques autocollants :

```bash
git clone --filter=blob:none --sparse https://github.com/alchaincyf/huashu-bird-sticker
cd huashu-bird-sticker && git sparse-checkout set data stickers/Strigiformes
```

## Ils l’utilisent

- [水杉输入法 MSIME](https://github.com/metasequoiaime/msime) : une méthode de saisie du chinois multiplateforme ; son dictionnaire de noms d’oiseaux est généré à partir de `data/species.json`.
- [Everybird](https://github.com/yusuftaleb/everybird-stickers), de Yusuf Taleb : les stickers, réduits et nommés par code eBird.
- Référencé dans [Awesome Public Datasets](https://github.com/awesomedata/apd-core), catégorie Biology.

Vous l’utilisez quelque part ? Ouvrez une issue et nous vous ajouterons ici.

## Crédits

- Taxonomie, noms anglais, aires de répartition et identifiants eBird et Avibase : AviList Core Team. 2026. AviList: The Global Avian Checklist, v2026. https://doi.org/10.2173/avilist.v2026, CC BY 4.0.
- Noms dans les autres langues : IOC World Bird List v15.2, Gill, Donsker et Rasmussen (dir.), CC BY 3.0.
- Autres identifiants entre bases de données : Wikidata (CC0).
- Mesures corporelles et écologie : AVONET, Tobias et al., 2022, *Ecology Letters*, CC BY 4.0.
- Photographes des images de référence : mentionnés espèce par espèce dans `data/species.json`. Les photos de référence ne sont pas incluses dans ce dépôt.
- Autocollants dessinés pour 鸣迹 (Mingji), un carnet d'observation des oiseaux pour iOS.

Si l'une de vos photos a servi de référence pour un autocollant et que vous préférez qu'elle ne le soit pas, [faites une demande de retrait](../../issues/new?template=takedown.yml) : nous remplacerons l'autocollant sous 7 jours.
