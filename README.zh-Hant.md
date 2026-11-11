# 全世界現存鳥類的貼紙

<img src="previews/header.webp" alt="huashu-bird-sticker: specimen drawer, body-size lineup and family plates" width="100%">

[English](README.md) · [简体中文](README.zh-Hans.md) · **繁體中文** · [日本語](README.ja.md) · [한국어](README.ko.md) · [Español](README.es.md) · [Français](README.fr.md) · [Deutsch](README.de.md) · [Português](README.pt.md) · [Русский](README.ru.md) · [العربية](README.ar.md)

<a href="https://birdalbum.com/zh-hant/?utm_source=github&utm_medium=readme&utm_campaign=bird-sticker"><img src="previews/birdalbum.webp" alt="Bird Album：世界上每一種鳥，一種一張貼紙。birdalbum.com" width="100%"></a>

**這套貼紙的完整用法，請到 [birdalbum.com](https://birdalbum.com/zh-hant/?utm_source=github&utm_medium=readme&utm_campaign=bird-sticker) 看看。** Bird Album 是用這個貼紙庫做的免費鳥類網站：15 種語言都能搜尋鳥名，看每種鳥分布在哪裡、幾月看得到；地圖上有 8,171 個賞鳥點，每處都列出這個月大家常記錄到的鳥。

1.1 萬多種鳥，每種一張貼紙，共 45 目 249 科，依全球統一鳥類名錄 [AviList v2026](https://www.avilist.org/) 整理。AviList 是 2025 年首次發布的全球統一名錄（IOC 名錄已停止更新，轉而採用它）。AviList 沒有標為滅絕或可能滅絕的物種全部收錄；另有 43 種帶滅絕相關標記、已有貼紙的物種也保留了：滅絕、野外滅絕、可能滅絕，其中兩種曾野外滅絕、現已重新引入（見 `extinctionStatus`）。每個物種都有貼紙。每種鳥都附有結構化資料：分類、最多 43 種語言的鳥名、各大資料庫的編號，以及每張貼紙是依據什麼生成的。

> **2.0 版把分類從 IOC 15.2 換成了 AviList v2026。** 82 個物種改了學名（`id` 與貼紙路徑隨之改變），91 個原本獨立的種現在成了別種的亞種，另有 30 個新種從原有物種中拆出。每一處變動都列在 [`data/crosswalk-ioc15.2-avilist2026.csv`](data/crosswalk-ioc15.2-avilist2026.csv)，每筆紀錄的 `previous` 保留了舊的 IOC 編號。詳見 [CHANGELOG](CHANGELOG.md)。

![40張貼紙，來自15個目](previews/hero.webp)

**AI 生成，每個檔案裡都寫明了。** 每個貼紙檔案的 XMP/IPTC 中繼資料都寫著：這是 AI 生成的插畫，不是照片（IPTC 數位來源類型 `trainedAlgorithmicMedia`），用的是哪個 AI 系統，未經專家核對、可能有錯，以及授權和本儲存庫的連結。

**授權一句話：** 貼紙採用 [CC BY 4.0](LICENSE.md) 授權，可以免費用於任何用途，包括商業用途、修改與再散布，只要標明來自 huashu-bird-sticker 並附上本儲存庫連結。資料採用 MIT，第三方部分請見 [NOTICE](NOTICE.md)。

## 一行程式碼用上

每張貼紙都能直接從 jsDelivr CDN 載入（已開跨網域），放進網頁即可：

```html
<img src="https://cdn.jsdelivr.net/gh/alchaincyf/huashu-bird-sticker@main/stickers/Coraciiformes/Alcedinidae/Alcedo_atthis.webp" alt="普通翠鳥" width="240">
```

要按鳥名查貼紙，載入 [`data/stickers.json`](data/stickers.json)（2.7 MB，每種一筆：學名、英文名、簡體中文名、檔案路徑和 birdalbum.com 上的鳥種頁；91 張亞種貼紙在 `data/species.json` 的 `forms` 裡）。43 種語言的鳥名在 [`data/names.csv`](data/names.csv)。

```js
const idx = await (await fetch("https://cdn.jsdelivr.net/gh/alchaincyf/huashu-bird-sticker@main/data/stickers.json")).json();
const s = idx.stickers.find(x => x.en === "Eurasian Magpie");
const url = idx.cdn + s.file;  // 貼紙網址
```

在圖片旁邊這樣署名，並連結到鳥種頁：

`Illustration: [Bird Album](https://birdalbum.com/birds/common-kingfisher/) / [huashu-bird-sticker](https://github.com/alchaincyf/huashu-bird-sticker), CC BY 4.0`

## 每日一鳥

在 GitHub 個人頁、部落格或 Notion 放一張每天換一隻的鳥卡片，把這行貼進任何 Markdown（`?lang=` 支援15種語言，`?theme=dark` 或 `auto` 切深色）：

```markdown
[![今日一鳥](https://birdalbum.com/today.svg?lang=zh-Hant)](https://birdalbum.com/today/?lang=zh-Hant)
```

[![今日一鳥](https://birdalbum.com/today.svg?lang=zh-Hant)](https://birdalbum.com/today/?lang=zh-Hant)

## 圖鑑一覽

十八個最鮮豔、最有特色的類群，每個類群 24 張貼紙，挑選時力求彼此看起來不重複。這裡展示的貼紙全都達到品質標準。

### 蜂鳥 · *Trochilidae* — 361 種

![蜂鳥](previews/families/trochilidae.webp)

### 鸚鵡與鳳頭鸚鵡 · *Psittaciformes* — 391 種

![鸚鵡與鳳頭鸚鵡](previews/families/parrots.webp)

### 翠鳥 · *Alcedinidae* — 123 種

![翠鳥](previews/families/alcedinidae.webp)

### 蜂虎、佛法僧與翠鴗 · *Meropidae* · *Coraciidae* · *Brachypteraciidae* · *Momotidae* · *Todidae* — 69 種

![蜂虎、佛法僧與翠鴗](previews/families/coraciiformes.webp)

### 巨嘴鳥與擬啄木 · *Ramphastidae* · *Capitonidae* · *Semnornithidae* · *Megalaimidae* · *Lybiidae* — 132 種

![巨嘴鳥與擬啄木](previews/families/toucans.webp)

### 天堂鳥與園丁鳥 · *Paradisaeidae* · *Ptilonorhynchidae* — 67 種

![天堂鳥與園丁鳥](previews/families/paradisaeidae.webp)

### 八色鳥 · *Pittidae* — 46 種

![八色鳥](previews/families/pittidae.webp)

### 唐納雀 · *Thraupidae* — 392 種

![唐納雀](previews/families/thraupidae.webp)

### 太陽鳥與啄花鳥 · *Nectariniidae* · *Dicaeidae* — 207 種

![太陽鳥與啄花鳥](previews/families/nectariniidae.webp)

### 傘鳥與侏儒鳥 · *Cotingidae* · *Pipridae* — 120 種

![傘鳥與侏儒鳥](previews/families/cotingas.webp)

### 雉與鷓鴣 · *Phasianidae* — 185 種

![雉與鷓鴣](previews/families/phasianidae.webp)

### 鴨、鵝與天鵝 · *Anatidae* — 164 種

![鴨、鵝與天鵝](previews/families/anatidae.webp)

### 鴿與鳩 · *Columbidae* — 338 種

![鴿與鳩](previews/families/columbidae.webp)

### 梅花雀與文鳥 · *Estrildidae* — 138 種

![梅花雀與文鳥](previews/families/estrildidae.webp)

### 松鴉與喜鵲 · *Corvidae* — 135 種

![松鴉與喜鵲](previews/families/corvidae.webp)

### 新大陸擬鸝與擬椋鳥 · *Icteridae* — 107 種

![新大陸擬鸝與擬椋鳥](previews/families/icteridae.webp)

### 犀鳥 · *Bucerotidae* — 64 種

![犀鳥](previews/families/bucerotidae.webp)

### 椋鳥與八哥 · *Sturnidae* — 118 種

![椋鳥與八哥](previews/families/sturnidae.webp)

### 每個目各一張

![每個目各一張](previews/orders.webp)

## 內容

| | |
|---|---|
| `stickers/<Order>/<Family>/<Genus_species>.webp` | 每個物種一張帶白邊的透明貼紙，長邊約 1,000 px。`<Genus_species>.<subspecies>.webp` 是 91 張亞種貼紙，這些亞種原本是獨立的種 |
| `data/species.json` | 每個物種一筆紀錄，完整資料集：分類、鳥名、編號、分布與亞種、體型測量與生態、保育狀態、貼紙及其來源。欄位說明見 [data/README.md](data/README.md) |
| `data/species.csv` | 同上，攤平成適合試算表開啟的格式 |
| `data/crosswalk-ioc15.2-avilist2026.csv` | IOC 15.2 的每個物種在 AviList v2026 裡對應什麼：不變、改名、併入、拆分 |
| `data/names.csv` | 43 種語言的鳥名（共 46 欄：中文、法文、葡萄牙文各有兩種版本） |
| `data/languages.json` | 語言代碼，以及每種語言對應 IOC 多語名錄的哪一欄 |
| `data/field-guide.zh-Hans.json` | 1,596 種鳥的簡體中文野外圖鑑筆記（外觀、野外辨識特徵、性別與年齡、相似種），CC BY-SA 4.0 |

一筆紀錄長這樣（鳥名有刪節）：

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

## 涵蓋範圍

- 鳥名：英文採用 AviList 的英文名，涵蓋全部物種。其他語言來自 IOC 多語名錄，只在分類範圍沒變的種上沿用；有 129 個物種因合併、拆分改變了範圍，或是新種，舊名可能指的是另一群鳥，我們寧可留白也不硬套。簡體中文涵蓋 10,947 種，範圍變動的種逐一人工核對過；法文、西班牙文、德文、俄文、日文和繁體中文都超過 94%。韓文、阿拉伯文、泰文、波斯文等目前只有幾百到一千種左右，因為 IOC 名錄只有這麼多。詳見 `data/names.csv`。
- 繁體中文鳥名直接取自 IOC，涵蓋 11,011 種中的 10,375 種；中國臺灣、中國香港慣用的鳥名有時並不相同，歡迎補充。
- 編號：eBird 10,983 種、Avibase 11,011 種，皆取自 AviList；Wikidata 10,757、GBIF 10,477。
- 貼紙：11,011 種全部都有，另有 91 張亞種貼紙，共 11,102 個檔案。

## 貼紙怎麼做的，品質如何

全部 11,102 個貼紙檔案都是 AI 插畫。我們為每個物種找參考照片（2026 年 11 月起，在能找到的情況下，改用多位拍攝者的照片拼成的參考板），用 GPT-image 畫出貼紙，放大後去背。想做類似東西的話，提示詞、姿勢規範和審核標準都寫在[docs/how-the-stickers-are-made.zh-Hans.md](docs/how-the-stickers-are-made.zh-Hans.md)（簡體中文）。

每張貼紙之後都由另一位AI審查者評分。2026年11月，我們按野外圖鑑圖版的更嚴格標準把全部貼紙重新審查了一遍：辨識、羽色與斑紋、嘴喙與眼睛、腳與趾、比例五項評分均至少3分（每項滿分4分），辨識項達到4分，且審查者認可其可用作野外圖鑑圖版，才算達標。77張原樣通過，其餘11,025張重新生成，直到新版達標為止。

- **全部11,102張都達到我們的品質標準**（`"meetsQualityBar": true`）：每一張都通過了上述更嚴格審查。審查者是AI，不是鳥類專家，達標不代表沒有錯誤；賞鳥人發現過哪一類錯誤，請見[issue #1](../../issues/1)和[issue #3](../../issues/3)。
- **少數貼紙只依據文字描述生成**，沒有用參考照片（`data/species.json` 裡 `"reference": null`，數量見 [data/README.md](data/README.md#reference-photos)）。它們比對照過照片的貼紙更容易畫錯。在 [birdalbum.com](https://birdalbum.com/) 上，這些貼紙的鳥種頁面都會另外提示。

這些是插畫，不是野外圖鑑的圖版。請把它們當作鳥的親切示意圖；需要仰賴細節時，請再對照圖鑑。如果你發現錯誤，歡迎[開一個 issue](../../issues/new/choose)——賞鳥人的指正，是這個專案最珍貴的貢獻。

**熟悉某一類鳥？**歡迎[幫忙審一個科](../../issues/new?template=family-review.yml)，告訴我們這個科裡哪些貼紙畫錯了。你指出的每一張都會重新生成、重新審核，你的名字會寫進 [CONTRIBUTORS.md](CONTRIBUTORS.md)。

## 關於參考照片

**參考照片的用途**。一張貼紙要呈現的是這種鳥的樣子：羽色與斑紋、喙、眼、腳和身體比例。這些是關於這種鳥的事實，也是野外圖鑑用文字描述的同一批內容。只靠文字說明，生圖模型常常畫不準，所以我們使用參考照片。

**我們怎麼使用參考照片**。畫每一種鳥時，生圖模型會看到一張或幾張參考照片和一段辨識特徵的文字說明，然後畫出一張新的插畫。照片怎麼使用，取決於貼紙是什麼時候生成的。2026 年 11 月以前生成的早期貼紙，每種鳥用一張照片，照片裡鳥的樣貌和姿態都作為參考。2026 年 11 月起，照片只用來核對鳥的樣貌，不使用照片裡的姿態、構圖、背景和光線；每隻鳥都畫成我們訂的標準姿勢，背景留白（多數類群是站立的正側面，游水、飛行等少數類群有各自的姿勢）。在能找到的情況下，照片來自多位拍攝者（6,369 張貼紙用了數張圖片拼成的參考板），讓貼紙反映的是這個物種，而不是某一張照片。早期貼紙除 77 張外都已依這種方式重新生成，這 77 張在更嚴格審查下原樣通過。畫完後由另一個審核模型依辨識特徵檢查。儲存庫中不含任何參考照片。

**署名與移除**。我們記錄下來的每張貼紙的參考照片（頁面，以及已知的作者和授權）都記在 `data/species.json` 的 `sticker.reference` 裡；只憑文字描述生成的貼紙寫 `"reference": null`。依參考照片授權分類的統計請見 [data/README.md](data/README.md#reference-photos)。如果你的照片被用作參考，而你不希望如此，請[提交移除申請](../../issues/new?template=takedown.yml)，我們會在 7 天內更換這張貼紙。

## 使用方式

原始檔案可以直接載入：

```
https://raw.githubusercontent.com/alchaincyf/huashu-bird-sticker/main/stickers/Accipitriformes/Accipitridae/Accipiter_nisus.webp
```

```python
import json
species = json.load(open("data/species.json"))["species"]
by_name = {s["scientificName"]: s for s in species}
print(by_name["Pica pica"]["names"]["ja"], by_name["Pica pica"]["sticker"]["file"])
```

整個儲存庫約 700 MB。如果只想取得資料和少數貼紙：

```bash
git clone --filter=blob:none --sparse https://github.com/alchaincyf/huashu-bird-sticker
cd huashu-bird-sticker && git sparse-checkout set data stickers/Strigiformes
```

## 誰在用

- [水杉输入法 MSIME](https://github.com/metasequoiaime/msime)：跨平台中文輸入法，鳥名詞庫由 `data/species.json` 產生。
- [Everybird](https://github.com/yusuftaleb/everybird-stickers)（Yusuf Taleb）：把貼紙縮小後按 eBird 代碼命名使用。
- 收錄於 [Awesome Public Datasets](https://github.com/awesomedata/apd-core) 的 Biology 分類。

你也在用？開個 issue 告訴我們，我們加到這裡。

## 致謝

- 分類、英文名、分布、eBird 與 Avibase 編號：AviList Core Team. 2026. AviList: The Global Avian Checklist, v2026. https://doi.org/10.2173/avilist.v2026，CC BY 4.0。
- 其他語言的鳥名：IOC World Bird List v15.2，Gill、Donsker 與 Rasmussen 編，CC BY 3.0。
- 其他跨資料庫編號：Wikidata（CC0）。
- 體型測量與生態：AVONET，Tobias 等，2022，*Ecology Letters*，CC BY 4.0。
- 參考照片的攝影者：逐物種標示於 `data/species.json`。本儲存庫不包含參考照片。
- 貼紙為 鸣迹（Mingji）所繪，這是一款 iOS 賞鳥筆記 App。

如果你的照片被用作某張貼紙的參考，而你不希望如此，請[提交移除申請](../../issues/new?template=takedown.yml)，我們會在 7 天內更換這張貼紙。
