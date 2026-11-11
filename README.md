# Bird stickers for the world's living bird species

<img src="previews/header.webp" alt="huashu-bird-sticker: specimen drawer, body-size lineup and family plates" width="100%">

**花叔开源的全球鸟类贴纸库：按全球统一鸟类名录AviList整理的1.1万多种鸟，每种一张白边贴纸，附多语种鸟名和分布、形态、保护等级数据。贴纸出自花叔做的观鸟App「鸣迹」。[中文说明 →](README.zh-Hans.md)**

**English** · [简体中文](README.zh-Hans.md) · [繁體中文](README.zh-Hant.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Español](README.es.md) · [Français](README.fr.md) · [Deutsch](README.de.md) · [Português](README.pt.md) · [Русский](README.ru.md) · [العربية](README.ar.md)

<a href="https://birdalbum.com/?utm_source=github&utm_medium=readme&utm_campaign=bird-sticker"><img src="previews/birdalbum.webp" alt="Bird Album: every bird in the world, one sticker each. birdalbum.com" width="100%"></a>

**See the whole library in use at [birdalbum.com](https://birdalbum.com/?utm_source=github&utm_medium=readme&utm_campaign=bird-sticker).** Bird Album is a free bird guide built on these stickers: look up any species by name in 15 languages, see where it lives and which months it is around, and open a map of 8,171 birding hotspots that shows what people are seeing at each one this month.

By [Huashu (花叔)](https://github.com/alchaincyf), from the bird-watching app Mingji (鸣迹). More than 11,000 bird species across 45 orders and 249 families, following [AviList v2026](https://www.avilist.org/), the unified global checklist first published in 2025 (the IOC list has ended in its favour). Every species that AviList does not flag as extinct or possibly extinct is included, plus 43 flagged species that already had a sticker: extinct, extinct in the wild, possibly extinct, or, for two, once extinct in the wild and since reintroduced (see `extinctionStatus`). Every species has a sticker. Each species comes with structured data: taxonomy, names in up to 43 languages, cross-database IDs, and what each sticker was made from.

> **Version 2.0 moved the taxonomy from IOC 15.2 to AviList v2026.** 82 species changed their scientific name (and so their `id` and sticker path), 91 former species are now subspecies of another species, and 30 new species were split off. Every change is listed in [`data/crosswalk-ioc15.2-avilist2026.csv`](data/crosswalk-ioc15.2-avilist2026.csv), and each record keeps its old IOC ID under `previous`. See [CHANGELOG](CHANGELOG.md).

![40 stickers from 15 bird orders](previews/hero.webp)

**AI-generated, and every file says so.** Each sticker file carries XMP/IPTC metadata stating that it is an AI-generated illustration, not a photograph (IPTC Digital Source Type `trainedAlgorithmicMedia`), which AI system was used, that it was not verified by experts and may contain errors, the license, and a link back to this repository.

**License in short:** the stickers are licensed under [CC BY 4.0](LICENSE.md): use them for anything, including commercial work, editing and redistribution, as long as you credit huashu-bird-sticker with a link to this repository. The data is MIT, and third-party parts are listed in [NOTICE](NOTICE.md).

## Use a sticker in one line

Every sticker is served by the jsDelivr CDN (CORS enabled), so you can put it straight into a page:

```html
<img src="https://cdn.jsdelivr.net/gh/alchaincyf/huashu-bird-sticker@main/stickers/Coraciiformes/Alcedinidae/Alcedo_atthis.webp" alt="Common Kingfisher" width="240">
```

To look a bird up by name, load [`data/stickers.json`](data/stickers.json) (2.7 MB: scientific, English and Chinese name, file path and the species page on birdalbum.com for each species; the 91 subspecies stickers are listed under `forms` in `data/species.json`). Names in 43 languages are in [`data/names.csv`](data/names.csv).

```js
const idx = await (await fetch("https://cdn.jsdelivr.net/gh/alchaincyf/huashu-bird-sticker@main/data/stickers.json")).json();
const s = idx.stickers.find(x => x.en === "Eurasian Magpie");
const url = idx.cdn + s.file;  // the sticker URL
```

Credit it next to the image like this, with the link to the species page:

`Illustration: [Bird Album](https://birdalbum.com/birds/common-kingfisher/) / [huashu-bird-sticker](https://github.com/alchaincyf/huashu-bird-sticker), CC BY 4.0`

## Bird of the day

A new bird on your GitHub profile, blog or Notion page every day. Paste this line into any Markdown file (`?lang=` for 15 languages, `?theme=dark` or `auto`):

```markdown
[![Bird of the day](https://birdalbum.com/today.svg)](https://birdalbum.com/today/)
```

[![Bird of the day](https://birdalbum.com/today.svg)](https://birdalbum.com/today/)

## Gallery

Eighteen of the most colourful and distinctive groups, 24 stickers each, picked so that no two look alike. Every sticker shown here meets the quality bar.

### Hummingbirds · *Trochilidae* — 361 species

![Hummingbirds](previews/families/trochilidae.webp)

### Parrots & cockatoos · *Psittaciformes* — 391 species

![Parrots & cockatoos](previews/families/parrots.webp)

### Kingfishers · *Alcedinidae* — 123 species

![Kingfishers](previews/families/alcedinidae.webp)

### Bee-eaters, rollers & motmots · *Meropidae* · *Coraciidae* · *Brachypteraciidae* · *Momotidae* · *Todidae* — 69 species

![Bee-eaters, rollers & motmots](previews/families/coraciiformes.webp)

### Toucans & barbets · *Ramphastidae* · *Capitonidae* · *Semnornithidae* · *Megalaimidae* · *Lybiidae* — 132 species

![Toucans & barbets](previews/families/toucans.webp)

### Birds-of-paradise & bowerbirds · *Paradisaeidae* · *Ptilonorhynchidae* — 67 species

![Birds-of-paradise & bowerbirds](previews/families/paradisaeidae.webp)

### Pittas · *Pittidae* — 46 species

![Pittas](previews/families/pittidae.webp)

### Tanagers · *Thraupidae* — 392 species

![Tanagers](previews/families/thraupidae.webp)

### Sunbirds & flowerpeckers · *Nectariniidae* · *Dicaeidae* — 207 species

![Sunbirds & flowerpeckers](previews/families/nectariniidae.webp)

### Cotingas & manakins · *Cotingidae* · *Pipridae* — 120 species

![Cotingas & manakins](previews/families/cotingas.webp)

### Pheasants & partridges · *Phasianidae* — 185 species

![Pheasants & partridges](previews/families/phasianidae.webp)

### Ducks, geese & swans · *Anatidae* — 164 species

![Ducks, geese & swans](previews/families/anatidae.webp)

### Pigeons & doves · *Columbidae* — 338 species

![Pigeons & doves](previews/families/columbidae.webp)

### Waxbills & munias · *Estrildidae* — 138 species

![Waxbills & munias](previews/families/estrildidae.webp)

### Jays & magpies · *Corvidae* — 135 species

![Jays & magpies](previews/families/corvidae.webp)

### New World orioles & oropendolas · *Icteridae* — 107 species

![New World orioles & oropendolas](previews/families/icteridae.webp)

### Hornbills · *Bucerotidae* — 64 species

![Hornbills](previews/families/bucerotidae.webp)

### Starlings & mynas · *Sturnidae* — 118 species

![Starlings & mynas](previews/families/sturnidae.webp)

### One from each order

![One from each order](previews/orders.webp)

## What's inside

| | |
|---|---|
| `stickers/<Order>/<Family>/<Genus_species>.webp` | One transparent sticker per species with a white outline, about 1,000 px on the long side. `<Genus_species>.<subspecies>.webp` are 91 extra stickers of subspecies that used to be separate species |
| `data/species.json` | One record per species, the complete dataset: taxonomy, names, IDs, range and subspecies, body measurements and ecology, conservation status, sticker and its source. Field reference: [data/README.md](data/README.md) |
| `data/crosswalk-ioc15.2-avilist2026.csv` | How every IOC 15.2 species maps to AviList v2026: same, renamed, lumped, split |
| `data/species.csv` | The same, flattened for spreadsheets |
| `data/names.csv` | Names in 43 languages (46 columns: Chinese, French and Portuguese each have two variants) |
| `data/languages.json` | Language codes and the IOC multilingual column each one comes from |
| `data/field-guide.zh-Hans.json` | Chinese field-guide notes (look, field marks, sexes and ages, similar species) for 1,596 species, CC BY-SA 4.0 |

A record looks like this (names shortened):

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

## Coverage

- Names: English (AviList) covers every species. Other languages come from the IOC multilingual list and are kept only where the species concept did not change; for the 129 species whose boundaries changed (lumps and splits) or that are new, an old name may refer to a different set of birds, so we left it out rather than guess. Simplified Chinese covers 10,947 species (each changed species was checked by hand); French, Spanish, German, Russian, Japanese and Traditional Chinese cover over 94%. Korean, Arabic, Thai, Persian and some others cover only a few hundred to about a thousand species, because that is what the IOC list has. See `data/names.csv`.
- IDs: eBird 10,983 and Avibase 11,011, both taken from AviList; Wikidata 10,757, GBIF 10,477.
- Stickers: all 11,011 species, plus 91 subspecies stickers, 11,102 files in all.

## How the stickers were made, and how good they are

All 11,102 sticker files are AI-generated illustrations, and every file says so in its metadata (IPTC Digital Source Type `trainedAlgorithmicMedia`). For each species we wrote down its field marks and found reference photos (since November 2026, where we could find them, a board of photos by several photographers), generated the sticker with GPT-image, upscaled it, and cut it out. A step-by-step explanation with a flowchart and FAQ, in 15 languages: [How the stickers are made](https://birdalbum.com/how-stickers-are-made/). If you want to make something similar, see the prompts, pose rules and review rubric in [docs/how-the-stickers-are-made.md](docs/how-the-stickers-are-made.md).

Every sticker was then scored by a separate AI reviewer. In November 2026 we re-checked all of them to a stricter standard, as plates for a field guide: a sticker passes only if identification, plumage, bill and eye, legs and feet, and proportions each score at least 3 out of 4, identification scores 4, and the reviewer would accept it as a field-guide plate. 77 stickers passed as they were; the other 11,025 were generated again until a new version passed.

- **All 11,102 meet our quality bar** (`"meetsQualityBar": true`): every one passed the stricter review above. The reviewer is an AI, not a bird expert, so passing does not mean a sticker has no mistakes; [issue #1](../../issues/1) and [issue #3](../../issues/3) show the kinds of error birders have found.
- **Some were drawn from a written description alone**, without any reference photo (`"reference": null` in `data/species.json`; the count is in [data/README.md](data/README.md#reference-photos)). They are more likely to contain mistakes than stickers checked against a photo. On [birdalbum.com](https://birdalbum.com/), the species page of each of these stickers carries an extra notice.

These are illustrations, not field-guide plates. Treat them as a friendly picture of the bird, and check a field guide before relying on a fine detail. If you spot a mistake, please [open an issue](../../issues/new/choose) — corrections from birders are the most valuable contribution this project can get.

**Know a group of birds well?** [Review one family](../../issues/new?template=family-review.yml): tell us which of its stickers are wrong. Each one you flag is regenerated and reviewed again, and you are credited in [CONTRIBUTORS.md](CONTRIBUTORS.md).

## About the reference photos

**What a reference is for.** A sticker shows what a species looks like: its plumage colours and markings, bill, eye, legs and feet, and proportions. These are facts about the bird, the same things a field guide describes in words. A written description alone is often not enough for the image model to get them right, so we use reference photos.

**How we use it.** The image model is given a written description of the species' field marks together with reference photos, and generates a new illustration. How the photos were used depends on when a sticker was made. Early stickers, generated before November 2026, used one photo per species, and both the bird's appearance and its pose in that photo served as reference. Since November 2026, the photos are used only to check what the bird looks like, and every bird is drawn in a standard pose that we set, on a plain background (standing side-on for most groups; swimming, flying and a few other groups have poses of their own); where we could find them, the photos come from several photographers (6,369 stickers were made with a board of several images). All but 77 of the early stickers have since been generated again this way; those 77 passed the stricter review as they were. A separate reviewer then checks the result against the field marks. No reference photo is included in this repository.

**Credit and removal.** The reference photos we recorded for each sticker (page, and the author and license where known) are listed in `sticker.reference` in `data/species.json`; stickers generated from a written description alone have `"reference": null`. A breakdown by reference license is in [data/README.md](data/README.md#reference-photos). If one of your photos was used as a reference and you would rather it weren't, [open a takedown request](../../issues/new?template=takedown.yml) and we will replace the sticker within 7 days.

## Use it

Raw files can be loaded directly:

```
https://raw.githubusercontent.com/alchaincyf/huashu-bird-sticker/main/stickers/Accipitriformes/Accipitridae/Accipiter_nisus.webp
```

```python
import json
species = json.load(open("data/species.json"))["species"]
by_name = {s["scientificName"]: s for s in species}
print(by_name["Pica pica"]["names"]["ja"], by_name["Pica pica"]["sticker"]["file"])
```

The repository is about 700 MB. To fetch only the data and a few stickers:

```bash
git clone --filter=blob:none --sparse https://github.com/alchaincyf/huashu-bird-sticker
cd huashu-bird-sticker && git sparse-checkout set data stickers/Strigiformes
```

## Used by

- [水杉输入法 MSIME](https://github.com/metasequoiaime/msime) — a cross-platform Chinese input method; its bird-name dictionary pack is built from `data/species.json`.
- [Everybird](https://github.com/yusuftaleb/everybird-stickers) by Yusuf Taleb — the stickers, resized and keyed by eBird code.
- Listed in [Awesome Public Datasets](https://github.com/awesomedata/apd-core) under Biology.

Using it somewhere? Open an issue and we will add you here.

## Credits

- Taxonomy, English names, ranges, eBird and Avibase IDs: AviList Core Team. 2026. AviList: The Global Avian Checklist, v2026. https://doi.org/10.2173/avilist.v2026, CC BY 4.0.
- Names in other languages: IOC World Bird List v15.2, Gill, Donsker & Rasmussen (Eds), CC BY 3.0.
- Other cross-database IDs: Wikidata (CC0).
- Body measurements and ecology: AVONET, Tobias et al. 2022, *Ecology Letters*, CC BY 4.0.
- Reference photographers: credited per species in `data/species.json`. Reference photos are not included in this repository.
- Stickers drawn for 鸣迹 (Mingji), a bird-watching notebook app for iOS.

If one of your photos was used as a reference for a sticker and you would rather it weren't, [open a takedown request](../../issues/new?template=takedown.yml) and we will replace the sticker within 7 days.
