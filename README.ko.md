# 전 세계 현생 조류의 스티커

<img src="previews/header.webp" alt="huashu-bird-sticker: specimen drawer, body-size lineup and family plates" width="100%">

[English](README.md) · [简体中文](README.zh-Hans.md) · [繁體中文](README.zh-Hant.md) · [日本語](README.ja.md) · **한국어** · [Español](README.es.md) · [Français](README.fr.md) · [Deutsch](README.de.md) · [Português](README.pt.md) · [Русский](README.ru.md) · [العربية](README.ar.md)

<a href="https://birdalbum.com/ko/?utm_source=github&utm_medium=readme&utm_campaign=bird-sticker"><img src="previews/birdalbum.webp" alt="Bird Album: 세계의 모든 새, 종마다 스티커 한 장. birdalbum.com" width="100%"></a>

**라이브러리 전체가 실제로 쓰이는 모습은 [birdalbum.com](https://birdalbum.com/ko/?utm_source=github&utm_medium=readme&utm_campaign=bird-sticker)에서 볼 수 있습니다.** Bird Album은 이 스티커로 만든 무료 조류 가이드입니다. 15개 언어로 종 이름을 검색하고, 그 새가 어디에 살고 어느 달에 볼 수 있는지 확인할 수 있으며, 탐조지 8,171곳이 표시된 지도에서 각 장소에서 이번 달 사람들이 어떤 새를 보고 있는지 열어 볼 수 있습니다.

새 1만 1천여 종, 45개 목 249개 과. 전 세계 통합 조류 목록 [AviList v2026](https://www.avilist.org/)을 따라 정리했습니다. AviList는 2025년에 처음 공개된 전 세계 통합 목록입니다(IOC 목록은 업데이트를 마치고 AviList로 넘어갔습니다). AviList가 멸종이나 멸종 가능성으로 분류하지 않은 종은 모두 들어 있고, 멸종 관련 표시가 있지만 이미 스티커가 있던 43종도 남겨 두었습니다. 표시는 멸종, 야생 절멸, 멸종 가능성이며, 그중 2종은 야생에서 절멸했다가 다시 도입된 종입니다(`extinctionStatus` 참고). 모든 종에 스티커가 있습니다. 각 종에는 분류, 최대 43개 언어의 이름, 여러 데이터베이스의 ID, 각 스티커가 무엇을 바탕으로 생성되었는지 같은 구조화된 데이터가 함께 들어 있습니다.

> **2.0 버전에서 분류를 IOC 15.2에서 AviList v2026으로 바꿨습니다.** 82종의 학명이 바뀌었고(그에 따라 `id`와 스티커 경로도 바뀝니다), 독립종이었던 91종이 다른 종의 아종이 되었으며, 30종이 새로 분할되었습니다. 모든 변경 사항은 [`data/crosswalk-ioc15.2-avilist2026.csv`](data/crosswalk-ioc15.2-avilist2026.csv)에 정리했고, 각 레코드의 `previous`에는 예전 IOC ID를 남겨 두었습니다. [CHANGELOG](CHANGELOG.md)도 참고하세요.

![15개 목에서 고른 스티커 40장](previews/hero.webp)

**AI 생성이라는 사실을 모든 파일에 적어 두었습니다.** 각 스티커 파일의 XMP/IPTC 메타데이터에는 AI로 생성한 일러스트이며 사진이 아니라는 점(IPTC 디지털 소스 유형 `trainedAlgorithmicMedia`), 사용한 AI 시스템, 전문가 검증을 거치지 않아 오류가 있을 수 있다는 점, 라이선스, 이 저장소 링크가 들어 있습니다.

**라이선스 한눈에 보기:** 스티커는 [CC BY 4.0](LICENSE.md)입니다. huashu-bird-sticker를 밝히고 이 저장소 링크를 달면 상업적 이용을 포함해 어떤 용도로든 쓸 수 있고, 수정과 재배포도 가능합니다. 데이터는 MIT이며, 제3자에게서 온 부분은 [NOTICE](NOTICE.md)에 정리되어 있습니다.

## 한 줄로 쓰기

모든 스티커는 jsDelivr CDN에서 바로 불러올 수 있습니다(CORS 허용). 페이지에 그대로 넣으면 됩니다:

```html
<img src="https://cdn.jsdelivr.net/gh/alchaincyf/huashu-bird-sticker@main/stickers/Coraciiformes/Alcedinidae/Alcedo_atthis.webp" alt="물총새" width="240">
```

이름으로 스티커를 찾으려면 [`data/stickers.json`](data/stickers.json)을 불러오세요(2.7 MB. 각 종의 학명, 영어명, 중국어명, 파일 경로, birdalbum.com 종 페이지. 아종 스티커 91장은 `data/species.json`의 `forms`에 있습니다). 43개 언어의 이름은 [`data/names.csv`](data/names.csv)에 있습니다.

```js
const idx = await (await fetch("https://cdn.jsdelivr.net/gh/alchaincyf/huashu-bird-sticker@main/data/stickers.json")).json();
const s = idx.stickers.find(x => x.en === "Eurasian Magpie");
const url = idx.cdn + s.file;  // 스티커 URL
```

이미지 옆에 종 페이지 링크와 함께 이렇게 표기해 주세요:

`Illustration: [Bird Album](https://birdalbum.com/birds/common-kingfisher/) / [huashu-bird-sticker](https://github.com/alchaincyf/huashu-bird-sticker), CC BY 4.0`

## 오늘의 새

GitHub 프로필, 블로그, Notion에 매일 바뀌는 새 카드를 넣어 보세요. 이 한 줄을 Markdown에 붙이면 됩니다(`?lang=`으로 15개 언어, `?theme=dark` 또는 `auto`):

```markdown
[![오늘의 새](https://birdalbum.com/today.svg?lang=ko)](https://birdalbum.com/today/?lang=ko)
```

[![오늘의 새](https://birdalbum.com/today.svg?lang=ko)](https://birdalbum.com/today/?lang=ko)

## 갤러리

가장 색이 화려하고 특징 있는 18개 무리를 무리마다 24장씩, 서로 비슷해 보이지 않도록 골랐습니다. 여기 실린 스티커는 모두 품질 기준을 충족합니다.

### 벌새 · *Trochilidae* — 361 종

![벌새](previews/families/trochilidae.webp)

### 앵무와 코카투 · *Psittaciformes* — 391 종

![앵무와 코카투](previews/families/parrots.webp)

### 물총새 · *Alcedinidae* — 123 종

![물총새](previews/families/alcedinidae.webp)

### 벌잡이새·파랑샛과·모트모트 · *Meropidae* · *Coraciidae* · *Brachypteraciidae* · *Momotidae* · *Todidae* — 69 종

![벌잡이새·파랑샛과·모트모트](previews/families/coraciiformes.webp)

### 큰부리새와 바벳 · *Ramphastidae* · *Capitonidae* · *Semnornithidae* · *Megalaimidae* · *Lybiidae* — 132 종

![큰부리새와 바벳](previews/families/toucans.webp)

### 극락조와 바우어새 · *Paradisaeidae* · *Ptilonorhynchidae* — 67 종

![극락조와 바우어새](previews/families/paradisaeidae.webp)

### 팔색조 · *Pittidae* — 46 종

![팔색조](previews/families/pittidae.webp)

### 풍금조 · *Thraupidae* — 392 종

![풍금조](previews/families/thraupidae.webp)

### 태양새와 꽃쪼기새 · *Nectariniidae* · *Dicaeidae* — 207 종

![태양새와 꽃쪼기새](previews/families/nectariniidae.webp)

### 코팅가와 마나킨 · *Cotingidae* · *Pipridae* — 120 종

![코팅가와 마나킨](previews/families/cotingas.webp)

### 꿩과 자고새 · *Phasianidae* — 185 종

![꿩과 자고새](previews/families/phasianidae.webp)

### 오리·기러기·고니 · *Anatidae* — 164 종

![오리·기러기·고니](previews/families/anatidae.webp)

### 비둘기 · *Columbidae* — 338 종

![비둘기](previews/families/columbidae.webp)

### 납부리새 · *Estrildidae* — 138 종

![납부리새](previews/families/estrildidae.webp)

### 어치와 까치 · *Corvidae* — 135 종

![어치와 까치](previews/families/corvidae.webp)

### 신대륙 꾀꼬리·오로펜돌라 · *Icteridae* — 107 종

![신대륙 꾀꼬리·오로펜돌라](previews/families/icteridae.webp)

### 코뿔새 · *Bucerotidae* — 64 종

![코뿔새](previews/families/bucerotidae.webp)

### 찌르레기와 구관조 · *Sturnidae* — 118 종

![찌르레기와 구관조](previews/families/sturnidae.webp)

### 목마다 한 장씩

![목마다 한 장씩](previews/orders.webp)

## 구성

| | |
|---|---|
| `stickers/<Order>/<Family>/<Genus_species>.webp` | 종마다 흰 테두리가 있는 투명 스티커 한 장, 긴 변 기준 약 1,000 px. `<Genus_species>.<subspecies>.webp`는 예전에 독립종이었던 아종의 스티커 91장 |
| `data/species.json` | 종마다 레코드 하나, 전체 데이터셋. 분류, 이름, ID, 분포와 아종, 신체 측정값과 생태, 보전 상태, 스티커와 그 출처가 들어 있습니다. 필드 설명은 [data/README.md](data/README.md) |
| `data/species.csv` | 같은 내용을 스프레드시트용으로 평평하게 편 것 |
| `data/crosswalk-ioc15.2-avilist2026.csv` | IOC 15.2의 각 종이 AviList v2026에서 어떻게 되었는지: 그대로, 이름 변경, 통합, 분할 |
| `data/names.csv` | 43개 언어의 이름(46개 열: 중국어, 프랑스어, 포르투갈어는 각각 두 가지 변종이 있음) |
| `data/languages.json` | 언어 코드와, 각 언어가 IOC 다국어 표의 어느 열에서 왔는지 |
| `data/field-guide.zh-Hans.json` | 1,596종에 대한 중국어 간체 도감 해설(생김새, 식별 특징, 성별·연령, 비슷한 종), CC BY-SA 4.0 |

레코드는 이런 모양입니다(이름은 줄임).

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

## 포함 범위

- 이름: 영어는 AviList의 영어 이름으로 모든 종을 포함합니다. 다른 언어는 IOC 다국어 목록에서 왔고, 종의 범위가 달라지지 않은 경우에만 이어받았습니다. 통합·분할로 범위가 바뀌었거나 새로 생긴 129종은 옛 이름이 다른 새 무리를 가리킬 수 있어서, 억지로 끼워 맞추지 않고 비워 두었습니다. 중국어 간체는 10,947종을 포함하며 범위가 바뀐 종은 하나씩 사람이 확인했습니다. 프랑스어, 스페인어, 독일어, 러시아어, 일본어, 중국어 번체는 94%를 넘습니다. 한국어, 아랍어, 태국어, 페르시아어 등은 IOC 목록에 있는 만큼만 담겨 있어서 아직은 수백 종에서 1,000종 안팎입니다. 자세한 내용은 `data/names.csv`를 보세요.
- 한국어 이름은 11,011종 중 554종에만 있어 아직 적습니다. 보태 주시는 기여를 환영합니다.
- ID: eBird 10,983, Avibase 11,011(둘 다 AviList에서 가져왔습니다), Wikidata 10,757, GBIF 10,477.
- 스티커: 11,011종 전부, 그리고 아종 스티커 91장. 파일은 모두 11,102장입니다.

## 스티커를 만든 방법과 품질

스티커 파일 11,102장은 모두 AI 일러스트입니다. 종마다 참고 사진을 찾고(2026년 11월부터는 찾을 수 있는 경우 여러 촬영자의 사진을 모은 참고판을 사용), GPT-image로 스티커를 그린 뒤 해상도를 키우고 오려 냈습니다. 비슷한 것을 만들고 싶다면, 프롬프트와 자세 규칙, 검수 기준을 [docs/how-the-stickers-are-made.md](docs/how-the-stickers-are-made.md)(영어)에 정리해 두었습니다.

모든 스티커는 이후 별도의 AI 검수자가 채점했습니다. 2026년 11월에는 도감의 도판으로 쓸 수 있는지를 기준으로 더 엄격하게 모든 스티커를 재검수했습니다. 통과하려면 종 식별, 깃털, 부리와 눈, 다리와 발, 비율의 각 항목에서 4점 만점에 3점 이상을 받아야 하고, 종 식별은 4점이어야 하며, 검수자가 도감의 도판으로 받아들일 수 있다고 판단해야 합니다. 77장은 그대로 통과했고, 나머지 11,025장은 새 버전이 통과할 때까지 다시 생성했습니다.

- **11,102장 모두 품질 기준을 충족합니다**(`"meetsQualityBar": true`). 모두 위의 더 엄격한 검수를 통과했습니다. 다만 검수자는 조류 전문가가 아니라 AI이므로, 통과했다고 해서 틀린 부분이 없다는 뜻은 아닙니다. 탐조인들이 찾아낸 오류의 종류는 [이슈 #1](../../issues/1)과 [이슈 #3](../../issues/3)을 보세요.
- **일부 스티커는 참고 사진 없이 글로 된 설명만으로 생성했습니다**(`data/species.json`의 `"reference": null`, 개수는 [data/README.md](data/README.md#reference-photos) 참고). 사진과 대조한 스티커보다 틀린 부분이 있을 가능성이 큽니다. [birdalbum.com](https://birdalbum.com/)에서는 이런 스티커의 종 페이지에 따로 안내를 붙입니다.

이것은 일러스트이지 도감의 도판이 아닙니다. 새의 모습을 친근하게 보여 주는 그림으로 보시고, 세부 특징에 의존할 때는 도감으로 확인해 주세요. 잘못된 부분을 발견하면 [이슈를 열어](../../issues/new/choose) 주세요. 탐조인의 정정은 이 프로젝트가 받을 수 있는 가장 값진 기여입니다.

**특정 조류 무리를 잘 아신다면** [한 과를 검토](../../issues/new?template=family-review.yml)해 어떤 스티커가 틀렸는지 알려 주세요. 지적해 주신 스티커는 모두 다시 생성해 재검토하고, 이름을 [CONTRIBUTORS.md](CONTRIBUTORS.md)에 올립니다.

## 참고 사진 안내

**참고 사진의 용도.** 스티커가 보여 주는 것은 그 종의 생김새입니다. 깃털 색과 무늬, 부리, 눈, 다리와 발, 몸의 비율이 그것입니다. 이것들은 그 새에 관한 사실이며, 야외 도감이 글로 설명하는 바로 그 내용입니다. 글로 된 설명만으로는 이미지 생성 모델이 정확하게 그리지 못하는 경우가 많아서 참고 사진을 사용합니다.

**참고 사진을 쓰는 방법.** 각 종을 그릴 때 이미지 생성 모델에 참고 사진 한 장 또는 여러 장과 식별 특징을 적은 설명을 함께 보여 주고, 새 일러스트를 그리게 합니다. 사진을 어떻게 썼는지는 스티커를 만든 시기에 따라 다릅니다. 2026년 11월 이전에 생성한 초기 스티커는 종마다 사진 한 장을 썼고, 그 사진 속 새의 생김새와 자세를 모두 참고했습니다. 2026년 11월부터는 사진을 새의 생김새를 확인하는 데만 쓰고, 사진의 자세, 구도, 배경, 조명은 사용하지 않습니다. 모든 새는 우리가 정한 표준 자세로, 배경 없이 그렸습니다(대부분의 무리는 서 있는 옆모습이고, 헤엄치는 새, 나는 새 등 몇몇 무리는 따로 정한 자세가 있습니다). 찾을 수 있는 경우에는 여러 촬영자의 사진을 사용해, 스티커가 특정한 사진 한 장이 아니라 그 종을 반영하도록 했습니다(여러 이미지를 모은 참고판으로 만든 스티커는 6,369장). 초기 스티커도 77장을 빼고는 모두 이 방식으로 다시 생성했고, 그 77장은 더 엄격한 검수를 그대로 통과했습니다. 그린 뒤에는 별도의 검토 모델이 식별 특징을 기준으로 확인합니다. 이 저장소에는 참고 사진이 들어 있지 않습니다.

**출처 표기와 삭제 요청.** 저희가 기록해 둔 각 스티커의 참고 사진(페이지, 그리고 알려진 경우 작성자와 라이선스)은 `data/species.json`의 `sticker.reference`에 있습니다. 글로 된 설명만으로 생성한 스티커는 `"reference": null`입니다. 참고 사진 라이선스별 집계는 [data/README.md](data/README.md#reference-photos)에서 볼 수 있습니다. 본인이 촬영한 사진이 참고 자료로 사용되는 것을 원하지 않으시면, [삭제 요청](../../issues/new?template=takedown.yml)을 남겨 주세요. 7일 안에 그 스티커를 교체하겠습니다.

## 사용하기

원본 파일은 바로 불러올 수 있습니다.

```
https://raw.githubusercontent.com/alchaincyf/huashu-bird-sticker/main/stickers/Accipitriformes/Accipitridae/Accipiter_nisus.webp
```

```python
import json
species = json.load(open("data/species.json"))["species"]
by_name = {s["scientificName"]: s for s in species}
print(by_name["Pica pica"]["names"]["ja"], by_name["Pica pica"]["sticker"]["file"])
```

저장소 전체는 약 700 MB입니다. 데이터와 일부 스티커만 받으려면 다음과 같이 합니다.

```bash
git clone --filter=blob:none --sparse https://github.com/alchaincyf/huashu-bird-sticker
cd huashu-bird-sticker && git sparse-checkout set data stickers/Strigiformes
```

## 사용 사례

- [水杉输入法 MSIME](https://github.com/metasequoiaime/msime): 크로스플랫폼 중국어 입력기. 새 이름 사전 팩을 `data/species.json`으로 만듭니다.
- [Everybird](https://github.com/yusuftaleb/everybird-stickers) (Yusuf Taleb): 스티커를 축소해 eBird 코드로 관리해 사용합니다.
- [Awesome Public Datasets](https://github.com/awesomedata/apd-core)의 Biology 분류에 수록.

사용하고 계신다면 issue로 알려 주세요. 여기에 추가하겠습니다.

## 출처 표기

- 분류, 영어 이름, 분포, eBird·Avibase ID: AviList Core Team. 2026. AviList: The Global Avian Checklist, v2026. https://doi.org/10.2173/avilist.v2026, CC BY 4.0.
- 다른 언어의 이름: IOC World Bird List v15.2, Gill, Donsker & Rasmussen(편), CC BY 3.0.
- 그 밖의 데이터베이스 간 ID: Wikidata(CC0).
- 신체 측정값과 생태: AVONET, Tobias 외, 2022, *Ecology Letters*, CC BY 4.0.
- 참고 사진 촬영자: 종별로 `data/species.json`에 표기했습니다. 참고 사진은 이 저장소에 포함되어 있지 않습니다.
- 스티커는 iOS용 탐조 기록 앱 鸣迹(Mingji)를 위해 그렸습니다.

본인이 촬영한 사진이 참고 자료로 사용되는 것을 원하지 않으시면, [삭제 요청](../../issues/new?template=takedown.yml)을 남겨 주세요. 7일 안에 그 스티커를 교체하겠습니다.
