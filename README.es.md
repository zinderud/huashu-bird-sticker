# Pegatinas de las especies de aves vivas del mundo

<img src="previews/header.webp" alt="huashu-bird-sticker: specimen drawer, body-size lineup and family plates" width="100%">

[English](README.md) · [简体中文](README.zh-Hans.md) · [繁體中文](README.zh-Hant.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · **Español** · [Français](README.fr.md) · [Deutsch](README.de.md) · [Português](README.pt.md) · [Русский](README.ru.md) · [العربية](README.ar.md)

<a href="https://birdalbum.com/es/?utm_source=github&utm_medium=readme&utm_campaign=bird-sticker"><img src="previews/birdalbum.webp" alt="Bird Album: todas las aves del mundo, una pegatina por cada una. birdalbum.com" width="100%"></a>

**Vea toda la biblioteca en uso en [birdalbum.com](https://birdalbum.com/es/?utm_source=github&utm_medium=readme&utm_campaign=bird-sticker).** Bird Album es una guía de aves gratuita creada con estas pegatinas: busque cualquier especie por su nombre en 15 idiomas, consulte dónde vive y en qué meses se la puede ver, y abra un mapa de 8171 puntos de observación de aves que muestra lo que la gente está viendo en cada uno este mes.

Más de 11 000 especies de aves en 45 órdenes y 249 familias, según [AviList v2026](https://www.avilist.org/), la lista global unificada publicada por primera vez en 2025 (la lista de la IOC dejó de actualizarse en su favor). Están todas las especies que AviList no marca como extintas o posiblemente extintas, más 43 especies marcadas que ya tenían pegatina: extintas, extintas en estado silvestre, posiblemente extintas o, en dos casos, extintas en estado silvestre en el pasado y reintroducidas después (véase `extinctionStatus`). Todas las especies tienen pegatina. Cada especie viene con datos estructurados: taxonomía, nombres en hasta 43 idiomas, identificadores de otras bases de datos y a partir de qué se generó cada pegatina.

> **La versión 2.0 pasó la taxonomía de la IOC 15.2 a AviList v2026.** 82 especies cambiaron de nombre científico (y con ello su `id` y la ruta de su pegatina), 91 antiguas especies son ahora subespecies de otra especie y se separaron 30 especies nuevas. Todos los cambios están en [`data/crosswalk-ioc15.2-avilist2026.csv`](data/crosswalk-ioc15.2-avilist2026.csv), y cada registro conserva su antiguo identificador de la IOC en `previous`. Véase el [CHANGELOG](CHANGELOG.md).

![40 pegatinas de 15 órdenes de aves](previews/hero.webp)

**Generadas con IA, y cada archivo lo indica.** Los metadatos XMP/IPTC de cada pegatina señalan que es una ilustración generada con IA y no una fotografía (tipo de fuente digital IPTC `trainedAlgorithmicMedia`), el sistema de IA utilizado, que no ha sido verificada por expertos y puede contener errores, la licencia y un enlace a este repositorio.

**Licencia en breve:** las pegatinas tienen licencia [CC BY 4.0](LICENSE.md): puede usarlas para cualquier fin, incluido el comercial, y también editarlas y redistribuirlas, siempre que mencione huashu-bird-sticker con un enlace a este repositorio. Los datos están bajo licencia MIT y las partes de terceros figuran en [NOTICE](NOTICE.md).

## Usar una pegatina en una línea

Todas las pegatinas se sirven desde la CDN de jsDelivr (con CORS), así que puede ponerlas directamente en una página:

```html
<img src="https://cdn.jsdelivr.net/gh/alchaincyf/huashu-bird-sticker@main/stickers/Coraciiformes/Alcedinidae/Alcedo_atthis.webp" alt="Martín pescador común" width="240">
```

Para buscar un ave por su nombre, cargue [`data/stickers.json`](data/stickers.json) (2,7 MB: nombre científico, inglés y chino, ruta del archivo y la página de la especie en birdalbum.com para cada especie; las 91 pegatinas de subespecies figuran en `forms`, dentro de `data/species.json`). Los nombres en 43 idiomas están en [`data/names.csv`](data/names.csv).

```js
const idx = await (await fetch("https://cdn.jsdelivr.net/gh/alchaincyf/huashu-bird-sticker@main/data/stickers.json")).json();
const s = idx.stickers.find(x => x.en === "Eurasian Magpie");
const url = idx.cdn + s.file;  // URL de la pegatina
```

Cite la fuente junto a la imagen así, con el enlace a la página de la especie:

`Illustration: [Bird Album](https://birdalbum.com/birds/common-kingfisher/) / [huashu-bird-sticker](https://github.com/alchaincyf/huashu-bird-sticker), CC BY 4.0`

## El ave del día

Un ave distinta cada día en tu perfil de GitHub, blog o Notion. Pega esta línea en cualquier Markdown (`?lang=` para 15 idiomas, `?theme=dark` o `auto`):

```markdown
[![El ave del día](https://birdalbum.com/today.svg?lang=es)](https://birdalbum.com/today/?lang=es)
```

[![El ave del día](https://birdalbum.com/today.svg?lang=es)](https://birdalbum.com/today/?lang=es)

## Galería

Dieciocho de los grupos más coloridos y característicos, 24 pegatinas de cada uno, elegidas para que no haya dos que se parezcan. Todas las pegatinas que se muestran aquí cumplen el nivel de calidad.

### Colibríes · *Trochilidae* — 361 especies

![Colibríes](previews/families/trochilidae.webp)

### Loros y cacatúas · *Psittaciformes* — 391 especies

![Loros y cacatúas](previews/families/parrots.webp)

### Martines pescadores · *Alcedinidae* — 123 especies

![Martines pescadores](previews/families/alcedinidae.webp)

### Abejarucos, carracas y momotos · *Meropidae* · *Coraciidae* · *Brachypteraciidae* · *Momotidae* · *Todidae* — 69 especies

![Abejarucos, carracas y momotos](previews/families/coraciiformes.webp)

### Tucanes y barbudos · *Ramphastidae* · *Capitonidae* · *Semnornithidae* · *Megalaimidae* · *Lybiidae* — 132 especies

![Tucanes y barbudos](previews/families/toucans.webp)

### Aves del paraíso y ptilonorrincos · *Paradisaeidae* · *Ptilonorhynchidae* — 67 especies

![Aves del paraíso y ptilonorrincos](previews/families/paradisaeidae.webp)

### Pitas · *Pittidae* — 46 especies

![Pitas](previews/families/pittidae.webp)

### Tangaras · *Thraupidae* — 392 especies

![Tangaras](previews/families/thraupidae.webp)

### Suimangas y picaflores · *Nectariniidae* · *Dicaeidae* — 207 especies

![Suimangas y picaflores](previews/families/nectariniidae.webp)

### Cotingas y saltarines · *Cotingidae* · *Pipridae* — 120 especies

![Cotingas y saltarines](previews/families/cotingas.webp)

### Faisanes y perdices · *Phasianidae* — 185 especies

![Faisanes y perdices](previews/families/phasianidae.webp)

### Patos, gansos y cisnes · *Anatidae* — 164 especies

![Patos, gansos y cisnes](previews/families/anatidae.webp)

### Palomas · *Columbidae* — 338 especies

![Palomas](previews/families/columbidae.webp)

### Estríldidos · *Estrildidae* — 138 especies

![Estríldidos](previews/families/estrildidae.webp)

### Arrendajos y urracas · *Corvidae* — 135 especies

![Arrendajos y urracas](previews/families/corvidae.webp)

### Ictéridos del Nuevo Mundo (turpiales y oropéndolas) · *Icteridae* — 107 especies

![Ictéridos del Nuevo Mundo (turpiales y oropéndolas)](previews/families/icteridae.webp)

### Cálaos · *Bucerotidae* — 64 especies

![Cálaos](previews/families/bucerotidae.webp)

### Estorninos y mainás · *Sturnidae* — 118 especies

![Estorninos y mainás](previews/families/sturnidae.webp)

### Una de cada orden

![Una de cada orden](previews/orders.webp)

## Contenido

| | |
|---|---|
| `stickers/<Order>/<Family>/<Genus_species>.webp` | Una pegatina transparente con borde blanco por especie, de unos 1000 px en el lado largo. Los `<Genus_species>.<subspecies>.webp` son 91 pegatinas adicionales de subespecies que antes eran especies independientes |
| `data/species.json` | Un registro por especie, el conjunto de datos completo: taxonomía, nombres, identificadores, distribución y subespecies, medidas corporales y ecología, estado de conservación, pegatina y su origen. Descripción de los campos: [data/README.md](data/README.md) |
| `data/crosswalk-ioc15.2-avilist2026.csv` | Cómo se corresponde cada especie de la IOC 15.2 con AviList v2026: igual, rebautizada, fusionada, dividida |
| `data/species.csv` | Lo mismo, aplanado para hojas de cálculo |
| `data/names.csv` | Nombres en 43 idiomas (46 columnas: el chino, el francés y el portugués tienen dos variantes cada uno) |
| `data/languages.json` | Códigos de idioma y la columna multilingüe de la IOC de la que procede cada uno |
| `data/field-guide.zh-Hans.json` | Notas de guía de campo en chino simplificado (aspecto, marcas de campo, sexos y edades, especies parecidas) de 1596 especies, CC BY-SA 4.0 |

Un registro tiene este aspecto (nombres abreviados):

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

## Cobertura

- Nombres: el inglés (AviList) cubre todas las especies. Los demás idiomas proceden de la lista multilingüe de la IOC y se conservan solo donde el concepto de especie no cambió; en las 129 especies cuyos límites cambiaron (fusiones y divisiones) o que son nuevas, un nombre antiguo puede referirse a otro conjunto de aves, así que lo omitimos en lugar de adivinar. El chino simplificado cubre 10 947 especies (cada especie modificada se comprobó a mano); el francés, el español, el alemán, el ruso, el japonés y el chino tradicional superan el 94 %. El coreano, el árabe, el tailandés, el persa y algunos más cubren solo desde unos cientos hasta alrededor de mil especies, porque es lo que ofrece la lista de la IOC. Véase `data/names.csv`.
- Identificadores: eBird 10 983 y Avibase 11 011, ambos tomados de AviList; Wikidata 10 757, GBIF 10 477.
- Pegatinas: las 11 011 especies, más 91 pegatinas de subespecies, 11 102 archivos en total.

## Cómo se hicieron las pegatinas y qué calidad tienen

Los 11 102 archivos de pegatinas son ilustraciones hechas con IA. Para cada especie buscamos fotografías de referencia (desde noviembre de 2026, cuando pudimos encontrarlas, un tablero con fotos de varios fotógrafos), dibujamos la pegatina con GPT-image, la ampliamos y la recortamos. Si quieres hacer algo parecido, los prompts, las reglas de postura y los criterios de revisión están en [docs/how-the-stickers-are-made.md](docs/how-the-stickers-are-made.md) (en inglés).

Después, un revisor de IA independiente puntuó cada pegatina. En noviembre de 2026 volvimos a revisar todas las pegatinas con un criterio más estricto, como láminas de guía de campo: una pegatina solo supera la revisión si la identificación, el plumaje, el pico y el ojo, las patas y los pies, y las proporciones obtienen al menos 3 puntos de 4 en cada apartado, la identificación obtiene 4 y el revisor la aceptaría como lámina de guía de campo. 77 pegatinas la superaron tal como estaban; las otras 11 025 se generaron de nuevo hasta que una versión nueva la superó.

- **Las 11 102 cumplen nuestro nivel de calidad** (`"meetsQualityBar": true`): todas superaron la revisión más estricta descrita arriba. El revisor es una IA, no un experto en aves, así que superarla no significa que una pegatina no tenga errores; véanse la [incidencia n.º 1](../../issues/1) y la [incidencia n.º 3](../../issues/3) para ver los tipos de error que han encontrado los observadores de aves.
- **Algunas se generaron solo a partir de una descripción escrita**, sin foto de referencia (`"reference": null` en `data/species.json`; el número está en [data/README.md](data/README.md#reference-photos)). Es más probable que tengan errores que las pegatinas cotejadas con una foto. En [birdalbum.com](https://birdalbum.com/), la página de la especie lleva un aviso adicional para estas pegatinas.

Son ilustraciones, no láminas de guía de campo. Tómelas como un dibujo amable del ave y consulte una guía de campo antes de fiarse de un detalle fino. Si encuentra un error, [abra una incidencia](../../issues/new/choose): las correcciones de observadores de aves son la contribución más valiosa que puede recibir este proyecto.

**¿Conoces bien un grupo de aves?** [Revisa una familia](../../issues/new?template=family-review.yml) y dinos qué stickers están mal. Cada uno que señales se vuelve a generar y a revisar, y tu nombre aparecerá en [CONTRIBUTORS.md](CONTRIBUTORS.md).

## Sobre las fotografías de referencia

**Para qué sirve una referencia.** Una pegatina muestra cómo es una especie: los colores y las marcas del plumaje, el pico, el ojo, las patas y las proporciones. Son hechos sobre el ave, lo mismo que una guía de campo describe con palabras. Una descripción escrita a menudo no basta para que el modelo de imagen los acierte, así que usamos fotografías de referencia.

**Cómo la usamos.** Para cada especie, al modelo de imagen se le muestran una o varias fotografías de referencia junto con una descripción escrita de los rasgos de identificación, y dibuja una ilustración nueva. Cómo se usaron las fotos depende de cuándo se hizo la pegatina. Las pegatinas antiguas, generadas antes de noviembre de 2026, usaron una foto por especie, y tanto el aspecto del ave como su postura en esa foto sirvieron de referencia. Desde noviembre de 2026, las fotos solo se usan para comprobar cómo es el ave; no usamos la postura, la composición, el fondo ni la iluminación de la foto. Cada ave se dibuja en una postura estándar que fijamos nosotros, sobre un fondo liso (de pie y de perfil en la mayoría de los grupos; las aves que nadan, las que vuelan y algunos otros grupos tienen posturas propias). Cuando pudimos encontrarlas, las fotos proceden de varios fotógrafos, de modo que la pegatina refleje la especie y no una imagen concreta (6369 pegatinas se hicieron con un tablero de varias imágenes). Desde entonces, todas las pegatinas antiguas salvo 77 se han generado de nuevo de esta manera; esas 77 superaron tal como estaban la revisión más estricta. Después, un revisor independiente comprueba el dibujo según los rasgos de identificación. Este repositorio no incluye ninguna fotografía de referencia.

**Créditos y retirada.** Las fotografías de referencia que registramos para cada pegatina (página y, cuando se conocen, autor y licencia) figuran en `sticker.reference`, dentro de `data/species.json`; las pegatinas generadas solo a partir de una descripción escrita tienen `"reference": null`. Un desglose por licencia de las fotografías de referencia está en [data/README.md](data/README.md#reference-photos). Si una de sus fotos se usó como referencia y prefiere que no sea así, [envíe una solicitud de retirada](../../issues/new?template=takedown.yml) y sustituiremos la pegatina en un plazo de 7 días.

## Cómo usarlo

Los archivos se pueden cargar directamente:

```
https://raw.githubusercontent.com/alchaincyf/huashu-bird-sticker/main/stickers/Accipitriformes/Accipitridae/Accipiter_nisus.webp
```

```python
import json
species = json.load(open("data/species.json"))["species"]
by_name = {s["scientificName"]: s for s in species}
print(by_name["Pica pica"]["names"]["ja"], by_name["Pica pica"]["sticker"]["file"])
```

El repositorio pesa unos 700 MB. Para descargar solo los datos y unas pocas pegatinas:

```bash
git clone --filter=blob:none --sparse https://github.com/alchaincyf/huashu-bird-sticker
cd huashu-bird-sticker && git sparse-checkout set data stickers/Strigiformes
```

## Quién lo usa

- [水杉输入法 MSIME](https://github.com/metasequoiaime/msime): un método de entrada de chino multiplataforma; su diccionario de nombres de aves se genera a partir de `data/species.json`.
- [Everybird](https://github.com/yusuftaleb/everybird-stickers), de Yusuf Taleb: los stickers, reducidos y nombrados por código de eBird.
- Incluido en [Awesome Public Datasets](https://github.com/awesomedata/apd-core), en la categoría Biology.

¿Lo usas en algún sitio? Abre un issue y te añadimos aquí.

## Créditos

- Taxonomía, nombres en inglés, distribución e identificadores de eBird y Avibase: AviList Core Team. 2026. AviList: The Global Avian Checklist, v2026. https://doi.org/10.2173/avilist.v2026, CC BY 4.0.
- Nombres en otros idiomas: IOC World Bird List v15.2, Gill, Donsker y Rasmussen (eds.), CC BY 3.0.
- Otros identificadores entre bases de datos: Wikidata (CC0).
- Medidas corporales y ecología: AVONET, Tobias et al., 2022, *Ecology Letters*, CC BY 4.0.
- Fotógrafos de las imágenes de referencia: se citan por especie en `data/species.json`. Las fotografías de referencia no se incluyen en este repositorio.
- Pegatinas dibujadas para 鸣迹 (Mingji), una libreta de observación de aves para iOS.

Si una de sus fotos se usó como referencia para una pegatina y prefiere que no sea así, [envíe una solicitud de retirada](../../issues/new?template=takedown.yml) y sustituiremos la pegatina en un plazo de 7 días.
