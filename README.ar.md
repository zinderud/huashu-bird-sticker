# ملصقات لأنواع الطيور الحية في العالم

<img src="previews/header.webp" alt="huashu-bird-sticker: specimen drawer, body-size lineup and family plates" width="100%">

[English](README.md) · [简体中文](README.zh-Hans.md) · [繁體中文](README.zh-Hant.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Español](README.es.md) · [Français](README.fr.md) · [Deutsch](README.de.md) · [Português](README.pt.md) · [Русский](README.ru.md) · **العربية**

<a href="https://birdalbum.com/?utm_source=github&utm_medium=readme&utm_campaign=bird-sticker"><img src="previews/birdalbum.webp" alt="Bird Album: كل طيور العالم، ملصق واحد لكل نوع. birdalbum.com" width="100%"></a>

**شاهد المكتبة كاملةً قيد الاستخدام على [birdalbum.com](https://birdalbum.com/?utm_source=github&utm_medium=readme&utm_campaign=bird-sticker).** Bird Album دليل مجاني للطيور مبني على هذه الملصقات: ابحث عن أي نوع باسمه بـ15 لغة، وتعرّف على موطنه والأشهر التي يظهر فيها، وافتح خريطة تضم 8,171 موقعًا لمراقبة الطيور تعرض ما يراه الناس في كل موقع خلال هذا الشهر. (يتوفر الموقع بـ15 لغة، ويفتح الرابط صفحته الإنجليزية.)

أكثر من 11,000 نوع من الطيور موزعة على 45 رتبة و249 فصيلة، وفق [AviList v2026](https://www.avilist.org/)، القائمة العالمية الموحّدة التي صدرت لأول مرة عام 2025 (وقد توقفت قائمة IOC لصالحها). جميع الأنواع التي لا تصنّفها AviList منقرضة أو يُحتمل انقراضها مشمولة، إضافةً إلى 43 نوعًا مصنّفة كان لها ملصق من قبل: منقرضة، أو منقرضة في البرية، أو يُحتمل انقراضها، أو، في حالتين، انقرضت في البرية ثم أُعيد إدخالها (انظر `extinctionStatus`). لكل نوع ملصق. ويأتي مع كل نوع بيانات منظمة: التصنيف، وأسماء بما يصل إلى 43 لغة، ومعرّفات من قواعد بيانات أخرى، وما الذي وُلّد منه كل ملصق.

> **نقلت النسخة 2.0 التصنيف من IOC 15.2 إلى AviList v2026.** تغيّر الاسم العلمي لـ82 نوعًا (وتغيّر معه `id` ومسار الملصق)، وأصبح 91 نوعًا سابقًا نوعًا فرعيًا ضمن نوع آخر، وانفصل 30 نوعًا جديدًا. جميع التغييرات مدرجة في [`data/crosswalk-ioc15.2-avilist2026.csv`](data/crosswalk-ioc15.2-avilist2026.csv)، ويحتفظ كل سجل بمعرّف IOC القديم في الحقل `previous`. انظر [CHANGELOG](CHANGELOG.md).

![40 ملصقًا من 15 رتبة من الطيور](previews/hero.webp)

**مولَّدة بالذكاء الاصطناعي، وكل ملف يذكر ذلك.** تذكر بيانات XMP/IPTC الوصفية في كل ملصق أنه رسم مولَّد بالذكاء الاصطناعي وليس صورة فوتوغرافية (نوع المصدر الرقمي في IPTC‏ `trainedAlgorithmicMedia`)، ونظام الذكاء الاصطناعي المستخدم، وأنه لم يتحقق منه خبراء وقد يحتوي على أخطاء، إضافةً إلى الرخصة ورابط هذا المستودع.

**الرخصة باختصار:** الملصقات مرخّصة بموجب [CC BY 4.0](LICENSE.md): يمكنك استخدامها في أي غرض، بما في ذلك الاستخدام التجاري والتعديل وإعادة التوزيع، بشرط أن تذكر huashu-bird-sticker مع رابط هذا المستودع. البيانات برخصة MIT، والأجزاء التي تعود إلى أطراف ثالثة مذكورة في [NOTICE](NOTICE.md).

## استخدم ملصقًا بسطر واحد

كل الملصقات متاحة عبر شبكة jsDelivr لتوزيع المحتوى (مع تفعيل CORS)، فيمكنك وضعها مباشرة في أي صفحة:

```html
<img src="https://cdn.jsdelivr.net/gh/alchaincyf/huashu-bird-sticker@main/stickers/Coraciiformes/Alcedinidae/Alcedo_atthis.webp" alt="Common Kingfisher" width="240">
```

للبحث عن طائر باسمه، حمّل [`data/stickers.json`](data/stickers.json) (2.7 ميغابايت: الاسم العلمي والإنجليزي والصيني ومسار الملف وصفحة النوع على birdalbum.com لكل نوع؛ أما ملصقات الأنواع الفرعية الـ91 فمدرجة تحت `forms` في `data/species.json`). الأسماء بـ43 لغة موجودة في [`data/names.csv`](data/names.csv).

```js
const idx = await (await fetch("https://cdn.jsdelivr.net/gh/alchaincyf/huashu-bird-sticker@main/data/stickers.json")).json();
const s = idx.stickers.find(x => x.en === "Eurasian Magpie");
const url = idx.cdn + s.file;  // رابط الملصق
```

انسب الملصق بجانب الصورة هكذا، مع رابط إلى صفحة النوع:

`Illustration: [Bird Album](https://birdalbum.com/birds/common-kingfisher/) / [huashu-bird-sticker](https://github.com/alchaincyf/huashu-bird-sticker), CC BY 4.0`

## طائر اليوم

طائر جديد كل يوم في ملفك الشخصي على GitHub أو مدونتك أو صفحة Notion. الصق هذا السطر في أي ملف Markdown (`?lang=` لخمس عشرة لغة، و`?theme=dark` أو `auto`):

```markdown
[![Bird of the day](https://birdalbum.com/today.svg)](https://birdalbum.com/today/)
```

[![Bird of the day](https://birdalbum.com/today.svg)](https://birdalbum.com/today/)

## المعرض

ثماني عشرة من أكثر المجموعات ألوانًا وتميّزًا، في كل منها 24 ملصقًا، اخترناها بحيث لا يتشابه اثنان منها. جميع الملصقات المعروضة هنا تستوفي معيار الجودة.

### الطنان · *Trochilidae* — 361 نوعًا

![الطنان](previews/families/trochilidae.webp)

### الببغاوات والكوكاتو · *Psittaciformes* — 391 نوعًا

![الببغاوات والكوكاتو](previews/families/parrots.webp)

### الرفراف · *Alcedinidae* — 123 نوعًا

![الرفراف](previews/families/alcedinidae.webp)

### الوروار والشقراق والموتموت · *Meropidae* · *Coraciidae* · *Brachypteraciidae* · *Momotidae* · *Todidae* — 69 نوعًا

![الوروار والشقراق والموتموت](previews/families/coraciiformes.webp)

### التوكان والبربت · *Ramphastidae* · *Capitonidae* · *Semnornithidae* · *Megalaimidae* · *Lybiidae* — 132 نوعًا

![التوكان والبربت](previews/families/toucans.webp)

### طيور الجنة وطيور العريشة · *Paradisaeidae* · *Ptilonorhynchidae* — 67 نوعًا

![طيور الجنة وطيور العريشة](previews/families/paradisaeidae.webp)

### البيتا · *Pittidae* — 46 نوعًا

![البيتا](previews/families/pittidae.webp)

### التناجر · *Thraupidae* — 392 نوعًا

![التناجر](previews/families/thraupidae.webp)

### طيور الشمس وطيور الأزهار · *Nectariniidae* · *Dicaeidae* — 207 نوعًا

![طيور الشمس وطيور الأزهار](previews/families/nectariniidae.webp)

### الكوتنغا والمانكين · *Cotingidae* · *Pipridae* — 120 نوعًا

![الكوتنغا والمانكين](previews/families/cotingas.webp)

### الدراج والحجل · *Phasianidae* — 185 نوعًا

![الدراج والحجل](previews/families/phasianidae.webp)

### البط والإوز والبجع · *Anatidae* — 164 نوعًا

![البط والإوز والبجع](previews/families/anatidae.webp)

### الحمام · *Columbidae* — 338 نوعًا

![الحمام](previews/families/columbidae.webp)

### الأمادين · *Estrildidae* — 138 نوعًا

![الأمادين](previews/families/estrildidae.webp)

### القيق والعقعق · *Corvidae* — 135 نوعًا

![القيق والعقعق](previews/families/corvidae.webp)

### الإكتيريات (الأوريول والأوروبندولا) في العالم الجديد · *Icteridae* — 107 نوعًا

![الإكتيريات (الأوريول والأوروبندولا) في العالم الجديد](previews/families/icteridae.webp)

### أبو قرن · *Bucerotidae* — 64 نوعًا

![أبو قرن](previews/families/bucerotidae.webp)

### الزرازير والمينا · *Sturnidae* — 118 نوعًا

![الزرازير والمينا](previews/families/sturnidae.webp)

### واحد من كل رتبة

![واحد من كل رتبة](previews/orders.webp)

## المحتويات

| | |
|---|---|
| `stickers/<Order>/<Family>/<Genus_species>.webp` | ملصق شفاف واحد لكل نوع بحافة بيضاء، بطول يقارب 1,000 px للضلع الأطول. الملفات `<Genus_species>.<subspecies>.webp` هي 91 ملصقًا إضافيًا لأنواع فرعية كانت تُعدّ أنواعًا مستقلة |
| `data/species.json` | سجل واحد لكل نوع، وهو مجموعة البيانات الكاملة: التصنيف والأسماء والمعرّفات والانتشار والأنواع الفرعية والقياسات الجسدية والبيئة وحالة الحفظ والملصق ومصدره. وصف الحقول في [data/README.md](data/README.md) |
| `data/crosswalk-ioc15.2-avilist2026.csv` | كيف يقابل كل نوع في IOC 15.2 ما يقابله في AviList v2026: دون تغيير، أو أُعيدت تسميته، أو دُمج، أو انقسم |
| `data/species.csv` | المحتوى نفسه في صيغة مسطّحة لجداول البيانات |
| `data/names.csv` | الأسماء بـ43 لغة (46 عمودًا: للصينية والفرنسية والبرتغالية صيغتان لكل منها) |
| `data/languages.json` | رموز اللغات، وعمود قائمة IOC متعددة اللغات الذي تأتي منه كل لغة |
| `data/field-guide.zh-Hans.json` | ملاحظات دليل ميداني بالصينية المبسطة (المظهر وعلامات التمييز الميدانية والجنس والعمر والأنواع المشابهة) لـ1,596 نوعًا، رخصة CC BY-SA 4.0 |

يبدو السجل هكذا (مع اختصار الأسماء):

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

## التغطية

- الأسماء: الإنجليزية (AviList) تغطي جميع الأنواع. أما اللغات الأخرى فتأتي من قائمة IOC متعددة اللغات ولم نُبقِ فيها إلا ما لم يتغير فيه مفهوم النوع؛ ففي الأنواع الـ129 التي تغيّرت حدودها (بالدمج أو الفصل) أو المستجدة، قد يشير الاسم القديم إلى مجموعة أخرى من الطيور، فآثرنا حذفه على التخمين. وتغطي الصينية المبسطة 10,947 نوعًا (روجع كل نوع تغيّر يدويًا)، وتتجاوز الفرنسية والإسبانية والألمانية والروسية واليابانية والصينية التقليدية 94%. وتغطي الكورية والعربية والتايلاندية والفارسية وبعض اللغات الأخرى بضع مئات من الأنواع إلى نحو ألف نوع فقط، لأن هذا ما تتضمنه قائمة IOC. انظر `data/names.csv`.
- الأسماء العربية متوفرة لـ575 نوعًا فقط من أصل 11,011، فالتغطية ما زالت ضعيفة. المساهمات مرحَّب بها.
- المعرّفات: eBird 10,983 وAvibase 11,011، وكلاهما مأخوذ من AviList؛ وWikidata 10,757، وGBIF 10,477.
- الملصقات: جميع الأنواع الـ11,011، إضافةً إلى 91 ملصقًا للأنواع الفرعية، أي 11,102 ملفًا في المجموع.

## كيف صُنعت الملصقات وما مستوى جودتها

جميع ملفات الملصقات البالغ عددها 11,102 هي رسوم من إنتاج الذكاء الاصطناعي. بحثنا لكل نوع عن صور مرجعية (ومنذ نوفمبر 2026، حيثما استطعنا العثور عليها، لوحة من صور لعدة مصورين)، ورسمنا الملصق بواسطة GPT-image، ثم كبّرناه وقصصناه. لمن يريد صنع شيء مشابه: التعليمات (prompts) وقواعد الوضعية ومعايير المراجعة موجودة في [docs/how-the-stickers-are-made.md](docs/how-the-stickers-are-made.md) (بالإنجليزية).

بعد ذلك قيّم مراجعٌ مستقل من الذكاء الاصطناعي كل ملصق. في نوفمبر 2026 أعدنا فحص جميع الملصقات وفق معيار أشد صرامة، بوصفها لوحات لدليل ميداني: لا يجتاز الملصق المراجعة إلا إذا حصل كل محور من المحاور الخمسة — تحديد النوع، والريش، والمنقار والعين، والساقان والقدمان، والتناسب — على 3 نقاط على الأقل من أصل 4، وحصل تحديد النوع على 4 نقاط، وقَبِل المراجع استخدامه لوحةً في دليل ميداني. اجتاز 77 ملصقًا المراجعة كما هي، أما الـ11,025 الباقية فأُعيد توليدها حتى اجتازت نسخة جديدة منها المراجعة.

- **جميع الملصقات الـ11,102 تستوفي معيار الجودة لدينا** (`"meetsQualityBar": true`): فكلها اجتازت المراجعة الأشد صرامة المذكورة أعلاه. المراجع ذكاء اصطناعي وليس خبيرًا في الطيور، لذا فاجتياز المراجعة لا يعني خلوّ الملصق من الأخطاء؛ انظر [issue #1](../../issues/1) و[issue #3](../../issues/3) لمعرفة أنواع الأخطاء التي وجدها هواة مراقبة الطيور.
- **بعض الملصقات وُلّدت من وصف مكتوب فقط**، دون أي صورة مرجعية (`"reference": null` في `data/species.json`؛ العدد مذكور في [data/README.md](data/README.md#reference-photos)). احتمال وجود أخطاء فيها أكبر من الملصقات التي قورنت بصورة. على [birdalbum.com](https://birdalbum.com/) تحمل صفحة النوع تنبيهًا إضافيًا لهذه الملصقات.

هذه رسوم توضيحية وليست لوحات دليل ميداني. تعامل معها بوصفها صورة ودودة للطائر، وراجع دليلًا ميدانيًا قبل الاعتماد على أي تفصيل دقيق. وإذا لاحظت خطأً فنرجو [فتح issue](../../issues/new/choose): فتصحيحات هواة مراقبة الطيور هي أثمن مساهمة يمكن أن يتلقاها هذا المشروع.

**هل تعرف مجموعة من الطيور معرفة جيدة؟** [راجع فصيلة واحدة](../../issues/new?template=family-review.yml) وأخبرنا أي الملصقات فيها خاطئة. سنعيد إنشاء كل ملصق تشير إليه ونراجعه من جديد، وسيُضاف اسمك إلى [CONTRIBUTORS.md](CONTRIBUTORS.md).

## عن الصور المرجعية

**ما الغرض من الصورة المرجعية.** يُظهر الملصق شكل النوع: ألوان الريش ونقوشه، والمنقار، والعين، والساقين والقدمين، والنِّسب. هذه حقائق عن الطائر، وهي الأشياء نفسها التي يصفها الدليل الميداني بالكلمات. وكثيرًا ما لا يكفي الوصف المكتوب وحده لكي يرسمها نموذج الصور بدقة، لذلك نستخدم صورًا مرجعية.

**كيف نستخدمها.** لكل نوع، نعرض على نموذج الصور صورة مرجعية واحدة أو أكثر مع وصف مكتوب لعلامات التمييز، فيرسم رسمًا توضيحيًا جديدًا. تختلف طريقة استخدام الصور بحسب وقت صنع الملصق. فالملصقات المبكرة، التي وُلّدت قبل نوفمبر 2026، استخدمت صورة واحدة لكل نوع، وكان مظهر الطائر ووضعيته في تلك الصورة كلاهما مرجعًا. ومنذ نوفمبر 2026 لا تُستخدم الصور إلا للتحقق من مظهر الطائر؛ ولا نستخدم وضعية الطائر في الصورة ولا تكوينها ولا خلفيتها ولا إضاءتها. ويُرسم كل طائر بوضعية قياسية حددناها، على خلفية سادة (واقفًا من الجانب في معظم المجموعات؛ وللطيور السابحة والطائرة وبضع مجموعات أخرى وضعيات خاصة بها). وحيثما استطعنا العثور عليها، تأتي الصور من عدة مصورين، حتى يعكس الملصق النوع لا صورة بعينها (صُنع 6,369 ملصقًا بلوحة من عدة صور). ومنذ ذلك الحين أُعيد توليد جميع الملصقات المبكرة بهذه الطريقة عدا 77 ملصقًا اجتازت المراجعة الأشد صرامة كما هي. ثم يراجع مراجِع مستقل الرسم بناءً على علامات التمييز. ولا يتضمن هذا المستودع أي صورة مرجعية.

**النسبة والإزالة.** الصور المرجعية التي سجّلناها لكل ملصق (الصفحة، والمؤلف والرخصة حيثما عُرفا) مدرجة في `sticker.reference` داخل `data/species.json`؛ أما الملصقات المولّدة من وصف مكتوب فقط فقيمتها `"reference": null`. وتجد تصنيفًا حسب رخصة الصور المرجعية في [data/README.md](data/README.md#reference-photos). إذا استُخدمت إحدى صورك مرجعًا وتفضّل ألا يحدث ذلك، فقدّم [طلب إزالة](../../issues/new?template=takedown.yml) وسنستبدل الملصق خلال 7 أيام.

## الاستخدام

يمكن تحميل الملفات مباشرة:

```
https://raw.githubusercontent.com/alchaincyf/huashu-bird-sticker/main/stickers/Accipitriformes/Accipitridae/Accipiter_nisus.webp
```

```python
import json
species = json.load(open("data/species.json"))["species"]
by_name = {s["scientificName"]: s for s in species}
print(by_name["Pica pica"]["names"]["ja"], by_name["Pica pica"]["sticker"]["file"])
```

حجم المستودع نحو 700 MB. ولجلب البيانات وبعض الملصقات فقط:

```bash
git clone --filter=blob:none --sparse https://github.com/alchaincyf/huashu-bird-sticker
cd huashu-bird-sticker && git sparse-checkout set data stickers/Strigiformes
```

## من يستخدمه

- [水杉输入法 MSIME](https://github.com/metasequoiaime/msime): طريقة إدخال صينية متعددة المنصات، يُبنى قاموس أسماء الطيور فيها من `data/species.json`.
- [Everybird](https://github.com/yusuftaleb/everybird-stickers) من Yusuf Taleb: الملصقات بعد تصغيرها وتسميتها برمز eBird.
- مُدرج في [Awesome Public Datasets](https://github.com/awesomedata/apd-core) ضمن تصنيف Biology.

هل تستخدمه في مكان ما؟ افتح issue وسنضيفك هنا.

## شكر وإسناد

- التصنيف والأسماء الإنجليزية والانتشار ومعرّفا eBird وAvibase: AviList Core Team. 2026. AviList: The Global Avian Checklist, v2026. https://doi.org/10.2173/avilist.v2026، رخصة CC BY 4.0.
- الأسماء بلغات أخرى: IOC World Bird List v15.2، تحرير Gill وDonsker وRasmussen، رخصة CC BY 3.0.
- المعرّفات الأخرى بين قواعد البيانات: Wikidata (CC0).
- القياسات الجسدية والبيئة: AVONET، Tobias وآخرون، 2022، *Ecology Letters*، رخصة CC BY 4.0.
- مصوّرو الصور المرجعية: مذكورون لكل نوع في `data/species.json`. الصور المرجعية غير مضمّنة في هذا المستودع.
- رُسمت الملصقات من أجل 鸣迹 (Mingji)، وهو دفتر لمراقبة الطيور على نظام iOS.

إذا استُخدمت إحدى صورك مرجعًا لملصق وتفضّل ألا يحدث ذلك، فقدّم [طلب إزالة](../../issues/new?template=takedown.yml) وسنستبدل الملصق خلال 7 أيام.
