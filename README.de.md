# Sticker für die lebenden Vogelarten der Welt

<img src="previews/header.webp" alt="huashu-bird-sticker: specimen drawer, body-size lineup and family plates" width="100%">

[English](README.md) · [简体中文](README.zh-Hans.md) · [繁體中文](README.zh-Hant.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Español](README.es.md) · [Français](README.fr.md) · **Deutsch** · [Português](README.pt.md) · [Русский](README.ru.md) · [العربية](README.ar.md)

<a href="https://birdalbum.com/de/?utm_source=github&utm_medium=readme&utm_campaign=bird-sticker"><img src="previews/birdalbum.webp" alt="Bird Album: alle Vögel der Welt, ein Sticker pro Art. birdalbum.com" width="100%"></a>

**Die ganze Bibliothek im Einsatz sehen Sie auf [birdalbum.com](https://birdalbum.com/de/?utm_source=github&utm_medium=readme&utm_campaign=bird-sticker).** Bird Album ist ein kostenloser Vogelführer auf Basis dieser Sticker: Jede Art lässt sich in 15 Sprachen nach ihrem Namen nachschlagen, dazu sieht man, wo sie lebt und in welchen Monaten sie anzutreffen ist, und eine Karte mit 8.171 Beobachtungs-Hotspots zeigt, was dort in diesem Monat gerade gesehen wird.

Über 11.000 Vogelarten in 45 Ordnungen und 249 Familien, nach [AviList v2026](https://www.avilist.org/), der einheitlichen globalen Checkliste, die 2025 erstmals erschienen ist (die IOC-Liste wurde zu ihren Gunsten eingestellt). Enthalten ist jede Art, die AviList nicht als ausgestorben oder möglicherweise ausgestorben kennzeichnet, dazu 43 gekennzeichnete Arten, für die es schon einen Sticker gab: ausgestorben, in der Wildnis ausgestorben, möglicherweise ausgestorben oder, bei zweien, einst in der Wildnis ausgestorben und inzwischen wieder angesiedelt (siehe `extinctionStatus`). Jede Art hat einen Sticker. Zu jeder Art gibt es strukturierte Daten: Taxonomie, Namen in bis zu 43 Sprachen, IDs aus anderen Datenbanken und wonach jeder Sticker erzeugt wurde.

> **Version 2.0 hat die Taxonomie von IOC 15.2 auf AviList v2026 umgestellt.** 82 Arten haben ihren wissenschaftlichen Namen geändert (und damit ihre `id` und den Pfad ihres Stickers), 91 frühere Arten sind jetzt Unterarten einer anderen Art, und 30 neue Arten wurden abgespalten. Alle Änderungen stehen in [`data/crosswalk-ioc15.2-avilist2026.csv`](data/crosswalk-ioc15.2-avilist2026.csv), und jeder Eintrag behält seine alte IOC-ID unter `previous`. Siehe [CHANGELOG](CHANGELOG.md).

![40 Sticker aus 15 Vogelordnungen](previews/hero.webp)

**KI-generiert, und jede Datei sagt es.** In den XMP/IPTC-Metadaten jedes Stickers steht, dass es sich um eine KI-generierte Illustration und kein Foto handelt (IPTC Digital Source Type `trainedAlgorithmicMedia`), welches KI-System verwendet wurde, dass sie nicht von Fachleuten geprüft wurde und Fehler enthalten kann, dazu die Lizenz und ein Link zu diesem Repository.

**Lizenz in Kürze:** Die Sticker stehen unter [CC BY 4.0](LICENSE.md): Sie dürfen für alles genutzt werden, auch kommerziell, ebenso bearbeitet und weitergegeben, sofern Sie huashu-bird-sticker mit einem Link auf dieses Repository nennen. Die Daten stehen unter MIT, Teile von Dritten sind in [NOTICE](NOTICE.md) aufgeführt.

## Einen Sticker mit einer Zeile einbinden

Jeder Sticker wird über das jsDelivr-CDN ausgeliefert (mit CORS), Sie können ihn also direkt in eine Seite setzen:

```html
<img src="https://cdn.jsdelivr.net/gh/alchaincyf/huashu-bird-sticker@main/stickers/Coraciiformes/Alcedinidae/Alcedo_atthis.webp" alt="Eisvogel" width="240">
```

Um einen Vogel nach Namen zu finden, laden Sie [`data/stickers.json`](data/stickers.json) (2,7 MB: wissenschaftlicher, englischer und chinesischer Name, Dateipfad und die Artseite auf birdalbum.com für jede Art; die 91 Unterarten-Sticker stehen unter `forms` in `data/species.json`). Namen in 43 Sprachen stehen in [`data/names.csv`](data/names.csv).

```js
const idx = await (await fetch("https://cdn.jsdelivr.net/gh/alchaincyf/huashu-bird-sticker@main/data/stickers.json")).json();
const s = idx.stickers.find(x => x.en === "Eurasian Magpie");
const url = idx.cdn + s.file;  // Sticker-URL
```

Nennen Sie die Quelle neben dem Bild so, mit Link zur Artseite:

`Illustration: [Bird Album](https://birdalbum.com/birds/common-kingfisher/) / [huashu-bird-sticker](https://github.com/alchaincyf/huashu-bird-sticker), CC BY 4.0`

## Vogel des Tages

Jeden Tag ein anderer Vogel auf Ihrem GitHub-Profil, Blog oder in Notion. Diese Zeile in eine beliebige Markdown-Datei einfügen (`?lang=` für 15 Sprachen, `?theme=dark` oder `auto`):

```markdown
[![Vogel des Tages](https://birdalbum.com/today.svg?lang=de)](https://birdalbum.com/today/?lang=de)
```

[![Vogel des Tages](https://birdalbum.com/today.svg?lang=de)](https://birdalbum.com/today/?lang=de)

## Galerie

Achtzehn der farbenprächtigsten und markantesten Gruppen, je 24 Sticker, so ausgewählt, dass keine zwei gleich aussehen. Alle hier gezeigten Sticker erfüllen den Qualitätsanspruch.

### Kolibris · *Trochilidae* — 361 Arten

![Kolibris](previews/families/trochilidae.webp)

### Papageien und Kakadus · *Psittaciformes* — 391 Arten

![Papageien und Kakadus](previews/families/parrots.webp)

### Eisvögel · *Alcedinidae* — 123 Arten

![Eisvögel](previews/families/alcedinidae.webp)

### Bienenfresser, Racken und Sägeracken · *Meropidae* · *Coraciidae* · *Brachypteraciidae* · *Momotidae* · *Todidae* — 69 Arten

![Bienenfresser, Racken und Sägeracken](previews/families/coraciiformes.webp)

### Tukane und Bartvögel · *Ramphastidae* · *Capitonidae* · *Semnornithidae* · *Megalaimidae* · *Lybiidae* — 132 Arten

![Tukane und Bartvögel](previews/families/toucans.webp)

### Paradiesvögel und Laubenvögel · *Paradisaeidae* · *Ptilonorhynchidae* — 67 Arten

![Paradiesvögel und Laubenvögel](previews/families/paradisaeidae.webp)

### Pittas · *Pittidae* — 46 Arten

![Pittas](previews/families/pittidae.webp)

### Tangaren · *Thraupidae* — 392 Arten

![Tangaren](previews/families/thraupidae.webp)

### Nektarvögel und Blütenpicker · *Nectariniidae* · *Dicaeidae* — 207 Arten

![Nektarvögel und Blütenpicker](previews/families/nectariniidae.webp)

### Schmuckvögel und Manakins · *Cotingidae* · *Pipridae* — 120 Arten

![Schmuckvögel und Manakins](previews/families/cotingas.webp)

### Fasane und Rebhühner · *Phasianidae* — 185 Arten

![Fasane und Rebhühner](previews/families/phasianidae.webp)

### Enten, Gänse und Schwäne · *Anatidae* — 164 Arten

![Enten, Gänse und Schwäne](previews/families/anatidae.webp)

### Tauben · *Columbidae* — 338 Arten

![Tauben](previews/families/columbidae.webp)

### Prachtfinken · *Estrildidae* — 138 Arten

![Prachtfinken](previews/families/estrildidae.webp)

### Häher und Elstern · *Corvidae* — 135 Arten

![Häher und Elstern](previews/families/corvidae.webp)

### Stärlinge und Trupiale der Neuen Welt · *Icteridae* — 107 Arten

![Stärlinge und Trupiale der Neuen Welt](previews/families/icteridae.webp)

### Nashornvögel · *Bucerotidae* — 64 Arten

![Nashornvögel](previews/families/bucerotidae.webp)

### Stare und Beos · *Sturnidae* — 118 Arten

![Stare und Beos](previews/families/sturnidae.webp)

### Je eine aus jeder Ordnung

![Je eine aus jeder Ordnung](previews/orders.webp)

## Inhalt

| | |
|---|---|
| `stickers/<Order>/<Family>/<Genus_species>.webp` | Ein transparenter Sticker mit weißem Rand pro Art, etwa 1.000 px an der langen Seite. Die Dateien `<Genus_species>.<subspecies>.webp` sind 91 zusätzliche Sticker für Unterarten, die früher eigene Arten waren |
| `data/species.json` | Ein Eintrag pro Art, der vollständige Datensatz: Taxonomie, Namen, IDs, Verbreitung und Unterarten, Körpermaße und Ökologie, Gefährdungsstatus, Sticker und dessen Herkunft. Feldbeschreibung: [data/README.md](data/README.md) |
| `data/crosswalk-ioc15.2-avilist2026.csv` | Wie jede Art der IOC 15.2 auf AviList v2026 abgebildet wird: gleich, umbenannt, zusammengelegt, aufgespalten |
| `data/species.csv` | Dasselbe, für Tabellenkalkulationen abgeflacht |
| `data/names.csv` | Namen in 43 Sprachen (46 Spalten: Chinesisch, Französisch und Portugiesisch haben jeweils zwei Varianten) |
| `data/languages.json` | Sprachcodes und die mehrsprachige IOC-Spalte, aus der jede Sprache stammt |
| `data/field-guide.zh-Hans.json` | Bestimmungsführer-Notizen auf vereinfachtem Chinesisch (Aussehen, Bestimmungsmerkmale, Geschlechter und Alter, ähnliche Arten) für 1.596 Arten, CC BY-SA 4.0 |

So sieht ein Eintrag aus (Namen gekürzt):

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

## Abdeckung

- Namen: Englisch (AviList) deckt alle Arten ab. Die anderen Sprachen stammen aus der mehrsprachigen IOC-Liste und werden nur dort übernommen, wo sich das Artkonzept nicht geändert hat; bei den 129 Arten, deren Grenzen sich geändert haben (Zusammenlegungen und Abspaltungen) oder die neu sind, kann ein alter Name eine andere Gruppe von Vögeln meinen, deshalb haben wir ihn weggelassen, statt zu raten. Vereinfachtes Chinesisch deckt 10.947 Arten ab (jede geänderte Art wurde von Hand geprüft); Französisch, Spanisch, Deutsch, Russisch, Japanisch und traditionelles Chinesisch liegen über 94 %. Koreanisch, Arabisch, Thailändisch, Persisch und einige weitere decken nur einige hundert bis rund tausend Arten ab, weil die IOC-Liste nicht mehr hergibt. Siehe `data/names.csv`.
- IDs: eBird 10.983 und Avibase 11.011, beide aus AviList übernommen; Wikidata 10.757, GBIF 10.477.
- Sticker: alle 11.011 Arten, dazu 91 Unterarten-Sticker, insgesamt 11.102 Dateien.

## Wie die Sticker entstanden sind und wie gut sie sind

Alle 11.102 Sticker-Dateien sind KI-Illustrationen. Für jede Art haben wir Referenzfotos gesucht (seit November 2026, wo wir welche finden konnten, eine Tafel mit Fotos mehrerer Fotografen), den Sticker mit GPT-image gezeichnet, hochskaliert und freigestellt. Wer etwas Ähnliches bauen möchte: Prompts, Haltungsregeln und Bewertungskriterien stehen in [docs/how-the-stickers-are-made.md](docs/how-the-stickers-are-made.md) (auf Englisch).

Jeder Sticker wurde danach von einem eigenen KI-Prüfer bewertet. Im November 2026 haben wir alle Sticker nach einem strengeren Maßstab erneut geprüft, als Tafeln für ein Bestimmungsbuch: Ein Sticker besteht nur, wenn Bestimmbarkeit, Gefieder, Schnabel und Auge, Beine und Füße sowie Proportionen jeweils mindestens 3 von 4 Punkten erreichen, die Bestimmbarkeit 4 Punkte erreicht und der Prüfer ihn als Bestimmungsbuch-Tafel akzeptieren würde. 77 Sticker bestanden unverändert; die übrigen 11.025 wurden so lange neu erzeugt, bis eine neue Fassung bestand.

- **Alle 11.102 erfüllen unseren Qualitätsanspruch** (`"meetsQualityBar": true`): Jeder hat die oben beschriebene strengere Prüfung bestanden. Der Prüfer ist eine KI, kein Vogelexperte; bestanden heißt also nicht, dass ein Sticker fehlerfrei ist. Welche Arten von Fehlern Vogelbeobachter gefunden haben, zeigen [Issue #1](../../issues/1) und [Issue #3](../../issues/3).
- **Einige wurden nur nach einer schriftlichen Beschreibung erzeugt**, ohne Referenzfoto (`"reference": null` in `data/species.json`; die Anzahl steht in [data/README.md](data/README.md#reference-photos)). Sie enthalten eher Fehler als Sticker, die mit einem Foto abgeglichen wurden. Auf [birdalbum.com](https://birdalbum.com/) trägt die Artseite jedes dieser Sticker einen zusätzlichen Hinweis.

Das sind Illustrationen, keine Bestimmungsbuch-Tafeln. Sie sind als freundliches Bild des Vogels gedacht; bei feinen Details sollte man ein Bestimmungsbuch zurate ziehen. Wenn Sie einen Fehler entdecken, [eröffnen Sie bitte ein Issue](../../issues/new/choose): Korrekturen von Vogelbeobachtern sind der wertvollste Beitrag, den dieses Projekt bekommen kann.

**Sie kennen eine Vogelgruppe gut?** [Prüfen Sie eine Familie](../../issues/new?template=family-review.yml) und sagen Sie uns, welche Sticker falsch sind. Jeder gemeldete Sticker wird neu erzeugt und erneut geprüft, und Ihr Name kommt in [CONTRIBUTORS.md](CONTRIBUTORS.md).

## Zu den Referenzfotos

**Wozu eine Referenz dient.** Ein Sticker zeigt, wie eine Art aussieht: Gefiederfarben und -zeichnung, Schnabel, Auge, Beine und Füße sowie Proportionen. Das sind Tatsachen über den Vogel, dieselben Dinge, die ein Feldführer in Worten beschreibt. Eine schriftliche Beschreibung allein reicht dem Bildmodell oft nicht, um sie richtig wiederzugeben, deshalb verwenden wir Referenzfotos.

**Wie wir sie verwenden.** Für jede Art bekommt das Bildmodell ein oder mehrere Referenzfotos zusammen mit einer schriftlichen Beschreibung der Bestimmungsmerkmale gezeigt und zeichnet eine neue Illustration. Wie die Fotos verwendet wurden, hängt davon ab, wann ein Sticker entstanden ist. Frühe Sticker, die vor November 2026 erzeugt wurden, beruhten auf einem Foto pro Art, und sowohl das Aussehen des Vogels als auch seine Haltung auf diesem Foto dienten als Vorlage. Seit November 2026 dienen die Fotos nur noch dazu, das Aussehen des Vogels zu prüfen; Haltung, Bildaufbau, Hintergrund und Licht eines Fotos übernehmen wir nicht. Jeder Vogel wird in einer von uns festgelegten Standardhaltung auf schlichtem Hintergrund gezeichnet (bei den meisten Gruppen stehend im Profil; schwimmende, fliegende und einige andere Gruppen haben eigene Haltungen). Wo wir welche finden konnten, stammen die Fotos von mehreren Fotografen, damit ein Sticker die Art wiedergibt und nicht ein einzelnes Bild (6.369 Sticker entstanden mit einer Tafel aus mehreren Bildern). Bis auf 77 sind inzwischen alle frühen Sticker auf diese Weise neu erzeugt worden; diese 77 haben die strengere Prüfung unverändert bestanden. Anschließend prüft ein separater Prüfer die Zeichnung anhand der Bestimmungsmerkmale. Dieses Repository enthält keine Referenzfotos.

**Nennung und Entfernung.** Die Referenzfotos, die wir zu jedem Sticker festgehalten haben (Seite sowie, soweit bekannt, Urheber und Lizenz), stehen in `sticker.reference` in `data/species.json`; Sticker, die nur nach einer schriftlichen Beschreibung erzeugt wurden, haben `"reference": null`. Eine Aufschlüsselung nach Lizenz der Referenzfotos steht in [data/README.md](data/README.md#reference-photos). Wenn eines Ihrer Fotos als Referenz verwendet wurde und Sie das nicht möchten, stellen Sie einen [Antrag auf Entfernung](../../issues/new?template=takedown.yml). Wir ersetzen den Sticker innerhalb von 7 Tagen.

## Verwendung

Die Dateien lassen sich direkt laden:

```
https://raw.githubusercontent.com/alchaincyf/huashu-bird-sticker/main/stickers/Accipitriformes/Accipitridae/Accipiter_nisus.webp
```

```python
import json
species = json.load(open("data/species.json"))["species"]
by_name = {s["scientificName"]: s for s in species}
print(by_name["Pica pica"]["names"]["ja"], by_name["Pica pica"]["sticker"]["file"])
```

Das Repository ist etwa 700 MB groß. So holt man nur die Daten und einige Sticker:

```bash
git clone --filter=blob:none --sparse https://github.com/alchaincyf/huashu-bird-sticker
cd huashu-bird-sticker && git sparse-checkout set data stickers/Strigiformes
```

## Wer es nutzt

- [水杉输入法 MSIME](https://github.com/metasequoiaime/msime): eine plattformübergreifende chinesische Eingabemethode; ihr Vogelnamen-Wörterbuch wird aus `data/species.json` erzeugt.
- [Everybird](https://github.com/yusuftaleb/everybird-stickers) von Yusuf Taleb: die Sticker, verkleinert und nach eBird-Code benannt.
- Gelistet in [Awesome Public Datasets](https://github.com/awesomedata/apd-core) unter Biology.

Sie nutzen es irgendwo? Eröffnen Sie ein Issue, dann nehmen wir Sie hier auf.

## Quellen

- Taxonomie, englische Namen, Verbreitung sowie eBird- und Avibase-IDs: AviList Core Team. 2026. AviList: The Global Avian Checklist, v2026. https://doi.org/10.2173/avilist.v2026, CC BY 4.0.
- Namen in anderen Sprachen: IOC World Bird List v15.2, Gill, Donsker & Rasmussen (Hrsg.), CC BY 3.0.
- Weitere datenbankübergreifende IDs: Wikidata (CC0).
- Körpermaße und Ökologie: AVONET, Tobias et al., 2022, *Ecology Letters*, CC BY 4.0.
- Fotografen der Referenzfotos: pro Art in `data/species.json` genannt. Die Referenzfotos sind nicht Teil dieses Repositorys.
- Die Sticker wurden für 鸣迹 (Mingji) gezeichnet, ein Vogelbeobachtungs-Notizbuch für iOS.

Wenn eines Ihrer Fotos als Referenz für einen Sticker verwendet wurde und Sie das nicht möchten, stellen Sie einen [Antrag auf Entfernung](../../issues/new?template=takedown.yml). Wir ersetzen den Sticker innerhalb von 7 Tagen.
