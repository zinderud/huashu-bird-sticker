# Стикеры для ныне живущих видов птиц мира

<img src="previews/header.webp" alt="huashu-bird-sticker: specimen drawer, body-size lineup and family plates" width="100%">

[English](README.md) · [简体中文](README.zh-Hans.md) · [繁體中文](README.zh-Hant.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Español](README.es.md) · [Français](README.fr.md) · [Deutsch](README.de.md) · [Português](README.pt.md) · **Русский** · [العربية](README.ar.md)

<a href="https://birdalbum.com/ru/?utm_source=github&utm_medium=readme&utm_campaign=bird-sticker"><img src="previews/birdalbum.webp" alt="Bird Album: все птицы мира, по одному стикеру на каждую. birdalbum.com" width="100%"></a>

**Всю библиотеку в деле можно увидеть на [birdalbum.com](https://birdalbum.com/ru/?utm_source=github&utm_medium=readme&utm_campaign=bird-sticker).** Bird Album — бесплатный определитель птиц на основе этих стикеров: ищите любой вид по названию на 15 языках, смотрите, где он обитает и в какие месяцы его можно встретить, и открывайте карту из 8 171 места наблюдения за птицами, где для каждого показано, кого там видят в этом месяце.

Более 11 000 видов птиц в 45 отрядах и 249 семействах по [AviList v2026](https://www.avilist.org/) — единому мировому списку, впервые опубликованному в 2025 году (список IOC прекратил обновляться в его пользу). Включены все виды, которые AviList не помечает как вымершие или возможно вымершие, а также 43 помеченных вида, для которых стикер уже был: вымершие, вымершие в дикой природе, возможно вымершие или, в двух случаях, когда-то вымершие в дикой природе и затем реинтродуцированные (см. `extinctionStatus`). Стикер есть у каждого вида. К каждому виду прилагаются структурированные данные: систематика, названия на 43 языках (максимум), идентификаторы в других базах данных и то, на основе чего создан каждый стикер.

> **В версии 2.0 систематика перешла с IOC 15.2 на AviList v2026.** У 82 видов изменилось научное название (а вместе с ним `id` и путь к стикеру), 91 бывший вид стал подвидом другого вида, и 30 новых видов были выделены. Все изменения перечислены в [`data/crosswalk-ioc15.2-avilist2026.csv`](data/crosswalk-ioc15.2-avilist2026.csv), а каждая запись хранит прежний идентификатор IOC в поле `previous`. См. [CHANGELOG](CHANGELOG.md).

![40 стикеров из 15 отрядов птиц](previews/hero.webp)

**Созданы ИИ, и это указано в каждом файле.** В метаданных XMP/IPTC каждого стикера указано, что это иллюстрация, созданная ИИ, а не фотография (тип цифрового источника IPTC `trainedAlgorithmicMedia`), какая система ИИ использовалась, что изображение не проверялось специалистами и может содержать ошибки, а также лицензия и ссылка на этот репозиторий.

**Лицензия кратко:** стикеры распространяются по лицензии [CC BY 4.0](LICENSE.md): их можно использовать для чего угодно, в том числе в коммерческих целях, а также изменять и распространять, если указать huashu-bird-sticker со ссылкой на этот репозиторий. Данные распространяются по лицензии MIT, а части от третьих лиц перечислены в [NOTICE](NOTICE.md).

## Стикер одной строкой

Все стикеры раздаются через CDN jsDelivr (CORS включён), их можно сразу вставить на страницу:

```html
<img src="https://cdn.jsdelivr.net/gh/alchaincyf/huashu-bird-sticker@main/stickers/Coraciiformes/Alcedinidae/Alcedo_atthis.webp" alt="Обыкновенный зимородок" width="240">
```

Чтобы найти птицу по названию, загрузите [`data/stickers.json`](data/stickers.json) (2,7 МБ: научное, английское и китайское название, путь к файлу и страница вида на birdalbum.com для каждого вида; 91 стикер подвидов указан в `forms` в файле `data/species.json`). Названия на 43 языках — в [`data/names.csv`](data/names.csv).

```js
const idx = await (await fetch("https://cdn.jsdelivr.net/gh/alchaincyf/huashu-bird-sticker@main/data/stickers.json")).json();
const s = idx.stickers.find(x => x.en === "Eurasian Magpie");
const url = idx.cdn + s.file;  // адрес стикера
```

Укажите авторство рядом с изображением так, со ссылкой на страницу вида:

`Illustration: [Bird Album](https://birdalbum.com/birds/common-kingfisher/) / [huashu-bird-sticker](https://github.com/alchaincyf/huashu-bird-sticker), CC BY 4.0`

## Птица дня

Каждый день новая птица в вашем профиле GitHub, блоге или Notion. Вставьте эту строку в любой Markdown (`?lang=` — 15 языков, `?theme=dark` или `auto`):

```markdown
[![Птица дня](https://birdalbum.com/today.svg?lang=ru)](https://birdalbum.com/today/?lang=ru)
```

[![Птица дня](https://birdalbum.com/today.svg?lang=ru)](https://birdalbum.com/today/?lang=ru)

## Галерея

Восемнадцать самых ярких и характерных групп, по 24 стикера из каждой, подобранных так, чтобы никакие два не были похожи. Все показанные здесь стикеры соответствуют порогу качества.

### Колибри · *Trochilidae* — 361 вид

![Колибри](previews/families/trochilidae.webp)

### Попугаи и какаду · *Psittaciformes* — 391 вид

![Попугаи и какаду](previews/families/parrots.webp)

### Зимородки · *Alcedinidae* — 123 вида

![Зимородки](previews/families/alcedinidae.webp)

### Щурки, сизоворонки и момоты · *Meropidae* · *Coraciidae* · *Brachypteraciidae* · *Momotidae* · *Todidae* — 69 видов

![Щурки, сизоворонки и момоты](previews/families/coraciiformes.webp)

### Туканы и бородатки · *Ramphastidae* · *Capitonidae* · *Semnornithidae* · *Megalaimidae* · *Lybiidae* — 132 вида

![Туканы и бородатки](previews/families/toucans.webp)

### Райские птицы и шалашники · *Paradisaeidae* · *Ptilonorhynchidae* — 67 видов

![Райские птицы и шалашники](previews/families/paradisaeidae.webp)

### Питты · *Pittidae* — 46 видов

![Питты](previews/families/pittidae.webp)

### Танагры · *Thraupidae* — 392 вида

![Танагры](previews/families/thraupidae.webp)

### Нектарницы и цветоеды · *Nectariniidae* · *Dicaeidae* — 207 видов

![Нектарницы и цветоеды](previews/families/nectariniidae.webp)

### Котинги и манакины · *Cotingidae* · *Pipridae* — 120 видов

![Котинги и манакины](previews/families/cotingas.webp)

### Фазаны и куропатки · *Phasianidae* — 185 видов

![Фазаны и куропатки](previews/families/phasianidae.webp)

### Утки, гуси и лебеди · *Anatidae* — 164 вида

![Утки, гуси и лебеди](previews/families/anatidae.webp)

### Голуби · *Columbidae* — 338 видов

![Голуби](previews/families/columbidae.webp)

### Вьюрковые ткачики · *Estrildidae* — 138 видов

![Вьюрковые ткачики](previews/families/estrildidae.webp)

### Сойки и сороки · *Corvidae* — 135 видов

![Сойки и сороки](previews/families/corvidae.webp)

### Трупиалы Нового Света · *Icteridae* — 107 видов

![Трупиалы Нового Света](previews/families/icteridae.webp)

### Птицы-носороги · *Bucerotidae* — 64 вида

![Птицы-носороги](previews/families/bucerotidae.webp)

### Скворцы и майны · *Sturnidae* — 118 видов

![Скворцы и майны](previews/families/sturnidae.webp)

### По одному из каждого отряда

![По одному из каждого отряда](previews/orders.webp)

## Что внутри

| | |
|---|---|
| `stickers/<Order>/<Family>/<Genus_species>.webp` | По одному прозрачному стикеру с белым контуром на вид, около 1000 px по длинной стороне. Файлы `<Genus_species>.<subspecies>.webp` — это 91 дополнительный стикер подвидов, которые раньше считались отдельными видами |
| `data/species.json` | Одна запись на вид, полный набор данных: систематика, названия, идентификаторы, ареал и подвиды, промеры тела и экология, охранный статус, стикер и его источник. Описание полей: [data/README.md](data/README.md) |
| `data/crosswalk-ioc15.2-avilist2026.csv` | Как каждый вид IOC 15.2 соответствует AviList v2026: без изменений, переименован, объединён, разделён |
| `data/species.csv` | То же самое, в плоском виде для электронных таблиц |
| `data/names.csv` | Названия на 43 языках (46 столбцов: у китайского, французского и португальского по два варианта) |
| `data/languages.json` | Коды языков и столбец многоязычного списка IOC, из которого взят каждый из них |
| `data/field-guide.zh-Hans.json` | Заметки полевого определителя на упрощённом китайском (внешность, полевые признаки, пол и возраст, похожие виды) для 1596 видов, CC BY-SA 4.0 |

Запись выглядит так (названия сокращены):

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

## Охват

- Названия: английский (AviList) охватывает все виды. Названия на других языках взяты из многоязычного списка IOC и оставлены только там, где понимание вида не изменилось; у 129 видов, границы которых изменились (объединения и разделения) или которые появились заново, старое название может относиться к другой группе птиц, поэтому мы не стали его переносить, а не гадать. Упрощённый китайский охватывает 10 947 видов (каждый изменённый вид проверен вручную); французский, испанский, немецкий, русский, японский и китайский (традиционный) — более 94%. Корейский, арабский, тайский, персидский и некоторые другие охватывают лишь от нескольких сотен до примерно тысячи видов, потому что больше в списке IOC нет. См. `data/names.csv`.
- Русские названия есть у 10 455 из 11 011 видов, они взяты прямо из IOC.
- Идентификаторы: eBird 10 983 и Avibase 11 011, оба взяты из AviList; Wikidata 10 757, GBIF 10 477.
- Стикеры: все 11 011 видов и ещё 91 стикер подвидов, всего 11 102 файла.

## Как делались стикеры и насколько они хороши

Все 11 102 файла стикеров — это иллюстрации, созданные ИИ. Для каждого вида мы подбирали эталонные фотографии (с ноября 2026 года, если удавалось их найти, — подборку снимков нескольких фотографов), рисовали стикер с помощью GPT-image, увеличивали и вырезали по контуру. Если хотите сделать что-то похожее: промпты, правила выбора позы и критерии проверки описаны в [docs/how-the-stickers-are-made.md](docs/how-the-stickers-are-made.md) (на английском).

Затем каждый стикер оценивал отдельный рецензент-ИИ. В ноябре 2026 года мы повторно проверили все стикеры по более строгому стандарту, как таблицы для полевого определителя: стикер проходит проверку, только если каждый из пяти критериев — определение вида, оперение, клюв и глаз, ноги и лапы, пропорции — получает не менее 3 баллов из 4, определение вида получает 4 балла, а рецензент готов принять его как таблицу для полевого определителя. 77 стикеров прошли её без изменений; остальные 11 025 создавались заново, пока новая версия не проходила проверку.

- **Все 11 102 соответствуют нашему порогу качества** (`"meetsQualityBar": true`): каждый прошёл описанную выше более строгую проверку. Рецензент — это ИИ, а не специалист по птицам, поэтому прохождение проверки не означает, что в стикере нет ошибок; какие ошибки находили орнитологи-любители, видно в [issue #1](../../issues/1) и [issue #3](../../issues/3).
- **Некоторые созданы только по текстовому описанию**, без эталонной фотографии (`"reference": null` в `data/species.json`; их число указано в [data/README.md](data/README.md#reference-photos)). В них скорее встречаются ошибки, чем в стикерах, сверенных с фотографией. На [birdalbum.com](https://birdalbum.com/) на странице вида у таких стикеров есть дополнительное предупреждение.

Это иллюстрации, а не таблицы из полевого определителя. Относитесь к ним как к дружелюбному изображению птицы, а прежде чем полагаться на тонкую деталь, сверьтесь с определителем. Если вы заметили ошибку, [создайте issue](../../issues/new/choose): поправки от орнитологов-любителей — самый ценный вклад в этот проект.

**Хорошо знаете какую-то группу птиц?** [Проверьте одно семейство](../../issues/new?template=family-review.yml) и сообщите, какие стикеры нарисованы неверно. Каждый отмеченный стикер будет создан заново и проверен ещё раз, а ваше имя появится в [CONTRIBUTORS.md](CONTRIBUTORS.md).

## Об эталонных фотографиях

**Зачем нужна справочная фотография.** Стикер показывает, как выглядит вид: окраску и рисунок оперения, клюв, глаз, ноги и пропорции. Это факты о птице — то же самое, что полевой определитель описывает словами. Одного текстового описания модели изображений часто не хватает, чтобы передать их верно, поэтому мы используем справочные фотографии.

**Как мы их используем.** Для каждого вида модели изображений показывают одну или несколько справочных фотографий вместе с текстовым описанием полевых признаков, и она рисует новую иллюстрацию. Как использовались фотографии, зависит от того, когда был сделан стикер. Для ранних стикеров, созданных до ноября 2026 года, брали одну фотографию на вид, и образцом служили и внешний вид птицы, и её поза на этом снимке. С ноября 2026 года фотографии используются только для того, чтобы сверить, как выглядит птица; позу, композицию, фон и освещение фотографии мы не используем. Каждая птица нарисована в заданной нами стандартной позе на однотонном фоне (у большинства групп — стоя в профиль; у плавающих, летящих и нескольких других групп свои позы). Фотографии нескольких фотографов мы брали там, где удавалось их найти, чтобы стикер отражал вид, а не какой-то один снимок (6369 стикеров сделаны по подборке из нескольких изображений). С тех пор все ранние стикеры, кроме 77, созданы заново этим способом; эти 77 прошли более строгую проверку без изменений. Затем отдельный проверяющий сверяет рисунок с полевыми признаками. Справочных фотографий в этом репозитории нет.

**Указание авторов и удаление.** Справочные фотографии, которые мы записали для каждого стикера (страница, а также автор и лицензия, если они известны), перечислены в `sticker.reference` в файле `data/species.json`; у стикеров, созданных только по текстовому описанию, указано `"reference": null`. Разбивка по лицензиям справочных фотографий приведена в [data/README.md](data/README.md#reference-photos). Если одна из ваших фотографий использовалась как справочная и вы этого не хотите, [отправьте запрос на удаление](../../issues/new?template=takedown.yml) — мы заменим стикер в течение 7 дней.

## Как пользоваться

Файлы можно загружать напрямую:

```
https://raw.githubusercontent.com/alchaincyf/huashu-bird-sticker/main/stickers/Accipitriformes/Accipitridae/Accipiter_nisus.webp
```

```python
import json
species = json.load(open("data/species.json"))["species"]
by_name = {s["scientificName"]: s for s in species}
print(by_name["Pica pica"]["names"]["ja"], by_name["Pica pica"]["sticker"]["file"])
```

Репозиторий занимает около 700 МБ. Чтобы получить только данные и несколько стикеров:

```bash
git clone --filter=blob:none --sparse https://github.com/alchaincyf/huashu-bird-sticker
cd huashu-bird-sticker && git sparse-checkout set data stickers/Strigiformes
```

## Кто использует

- [水杉输入法 MSIME](https://github.com/metasequoiaime/msime) — кроссплатформенный метод ввода китайского; его словарь названий птиц собран из `data/species.json`.
- [Everybird](https://github.com/yusuftaleb/everybird-stickers) (Yusuf Taleb) — стикеры, уменьшенные и названные по кодам eBird.
- Включён в [Awesome Public Datasets](https://github.com/awesomedata/apd-core), раздел Biology.

Используете где-то? Откройте issue, и мы добавим вас сюда.

## Источники

- Систематика, английские названия, ареалы, идентификаторы eBird и Avibase: AviList Core Team. 2026. AviList: The Global Avian Checklist, v2026. https://doi.org/10.2173/avilist.v2026, CC BY 4.0.
- Названия на других языках: IOC World Bird List v15.2, Gill, Donsker & Rasmussen (ред.), CC BY 3.0.
- Остальные идентификаторы в других базах данных: Wikidata (CC0).
- Промеры тела и экология: AVONET, Tobias et al., 2022, *Ecology Letters*, CC BY 4.0.
- Авторы эталонных фотографий: указаны по видам в `data/species.json`. Сами эталонные фотографии в этот репозиторий не входят.
- Стикеры нарисованы для 鸣迹 (Mingji) — блокнота наблюдателя птиц для iOS.

Если одна из ваших фотографий использовалась как справочная для стикера и вы этого не хотите, [отправьте запрос на удаление](../../issues/new?template=takedown.yml) — мы заменим стикер в течение 7 дней.
