# 世界の現生鳥類のステッカー

<img src="previews/header.webp" alt="huashu-bird-sticker: specimen drawer, body-size lineup and family plates" width="100%">

[English](README.md) · [简体中文](README.zh-Hans.md) · [繁體中文](README.zh-Hant.md) · **日本語** · [한국어](README.ko.md) · [Español](README.es.md) · [Français](README.fr.md) · [Deutsch](README.de.md) · [Português](README.pt.md) · [Русский](README.ru.md) · [العربية](README.ar.md)

<a href="https://birdalbum.com/ja/?utm_source=github&utm_medium=readme&utm_campaign=bird-sticker"><img src="previews/birdalbum.webp" alt="Bird Album：世界中の鳥を、1種につき1枚のステッカーで。birdalbum.com" width="100%"></a>

**ライブラリ全体の使われ方は[birdalbum.com](https://birdalbum.com/ja/?utm_source=github&utm_medium=readme&utm_campaign=bird-sticker)で見られます。** Bird Albumは、このステッカーを土台にした無料の野鳥図鑑サイトです。15言語で種名を検索でき、その鳥がどこにいて何月ごろ見られるかがわかります。地図には8,171か所の探鳥地が載っていて、各地点で今月どんな鳥がよく記録されているかを確認できます。

鳥1万1千種あまり、45目249科。全球統一の鳥類リスト[AviList v2026](https://www.avilist.org/)に沿って整理しています。AviListは2025年に初めて公開された全球統一リストです（IOCのリストは更新を終え、AviListに移行しました）。AviListで絶滅・絶滅の可能性ありとされていない種はすべて含み、さらに絶滅関連の区分が付いていても、すでにステッカーのあった43種を残してあります。区分は絶滅、野生絶滅、絶滅の可能性あり、そして2種は一度野生絶滅したあと再導入されたものです（`extinctionStatus`を参照）。すべての種にステッカーがあります。各種には、分類、最大43言語の名前、各データベースのID、そして各ステッカーが何をもとに生成されたかといった構造化データが付いています。

> **2.0版で、分類をIOC 15.2からAviList v2026に切り替えました。** 82種の学名が変わり（それに伴って`id`とステッカーのパスも変わりました）、従来は独立種だった91種が別種の亜種になり、30種が新たに分割されました。変更はすべて[`data/crosswalk-ioc15.2-avilist2026.csv`](data/crosswalk-ioc15.2-avilist2026.csv)に載せてあり、各レコードの`previous`には旧IOCのIDを残しています。[CHANGELOG](CHANGELOG.md)も参照してください。

![15の目から選んだ40枚のステッカー](previews/hero.webp)

**AI生成であることを、すべてのファイルに明記しています。** 各ステッカーファイルのXMP/IPTCメタデータには、AIで生成したイラストであり写真ではないこと（IPTCデジタルソースタイプ`trainedAlgorithmicMedia`）、使用したAIシステム、専門家による確認を経ておらず誤りを含む可能性があること、ライセンス、このリポジトリへのリンクを記載しています。

**ライセンスを一言で:** ステッカーは[CC BY 4.0](LICENSE.md)です。huashu-bird-stickerの名前とこのリポジトリへのリンクを添えれば、商用を含むどんな用途にも使え、加工や再配布もできます。データはMITで、第三者に由来する部分は[NOTICE](NOTICE.md)に記載しています。

## 1行で使う

ステッカーはすべてjsDelivr CDNから直接読み込めます（CORS対応）。そのままページに貼れます：

```html
<img src="https://cdn.jsdelivr.net/gh/alchaincyf/huashu-bird-sticker@main/stickers/Coraciiformes/Alcedinidae/Alcedo_atthis.webp" alt="カワセミ" width="240">
```

名前でステッカーを探すには[`data/stickers.json`](data/stickers.json)を読み込みます（2.7 MB。各種の学名、英名、中国語名、ファイルパス、birdalbum.comの種ページ。亜種ステッカー91枚は`data/species.json`の`forms`にあります）。43言語の名前は[`data/names.csv`](data/names.csv)にあります。

```js
const idx = await (await fetch("https://cdn.jsdelivr.net/gh/alchaincyf/huashu-bird-sticker@main/data/stickers.json")).json();
const s = idx.stickers.find(x => x.en === "Eurasian Magpie");
const url = idx.cdn + s.file;  // ステッカーのURL
```

画像の近くに、種ページへのリンクを付けてこう表記してください：

`Illustration: [Bird Album](https://birdalbum.com/birds/common-kingfisher/) / [huashu-bird-sticker](https://github.com/alchaincyf/huashu-bird-sticker), CC BY 4.0`

## 今日の鳥

GitHub のプロフィール、ブログ、Notion に毎日ちがう鳥のカードを。この1行を Markdown に貼るだけです（`?lang=` で15言語、`?theme=dark` または `auto` で暗い色）：

```markdown
[![今日の鳥](https://birdalbum.com/today.svg?lang=ja)](https://birdalbum.com/today/?lang=ja)
```

[![今日の鳥](https://birdalbum.com/today.svg?lang=ja)](https://birdalbum.com/today/?lang=ja)

## ギャラリー

色彩が豊かで特徴のある18のグループを、それぞれ24枚ずつ、互いに似て見えないように選びました。ここに載せたステッカーはすべて品質基準を満たしています。

### ハチドリ · *Trochilidae* — 361 種

![ハチドリ](previews/families/trochilidae.webp)

### オウム・インコ · *Psittaciformes* — 391 種

![オウム・インコ](previews/families/parrots.webp)

### カワセミ · *Alcedinidae* — 123 種

![カワセミ](previews/families/alcedinidae.webp)

### ハチクイ・ブッポウソウ・ハチクイモドキ · *Meropidae* · *Coraciidae* · *Brachypteraciidae* · *Momotidae* · *Todidae* — 69 種

![ハチクイ・ブッポウソウ・ハチクイモドキ](previews/families/coraciiformes.webp)

### オオハシ・ゴシキドリ · *Ramphastidae* · *Capitonidae* · *Semnornithidae* · *Megalaimidae* · *Lybiidae* — 132 種

![オオハシ・ゴシキドリ](previews/families/toucans.webp)

### フウチョウ・ニワシドリ · *Paradisaeidae* · *Ptilonorhynchidae* — 67 種

![フウチョウ・ニワシドリ](previews/families/paradisaeidae.webp)

### ヤイロチョウ · *Pittidae* — 46 種

![ヤイロチョウ](previews/families/pittidae.webp)

### フウキンチョウ · *Thraupidae* — 392 種

![フウキンチョウ](previews/families/thraupidae.webp)

### タイヨウチョウ・ハナドリ · *Nectariniidae* · *Dicaeidae* — 207 種

![タイヨウチョウ・ハナドリ](previews/families/nectariniidae.webp)

### カザリドリ・マイコドリ · *Cotingidae* · *Pipridae* — 120 種

![カザリドリ・マイコドリ](previews/families/cotingas.webp)

### キジ・ウズラ · *Phasianidae* — 185 種

![キジ・ウズラ](previews/families/phasianidae.webp)

### カモ・ガン・ハクチョウ · *Anatidae* — 164 種

![カモ・ガン・ハクチョウ](previews/families/anatidae.webp)

### ハト · *Columbidae* — 338 種

![ハト](previews/families/columbidae.webp)

### カエデチョウ · *Estrildidae* — 138 種

![カエデチョウ](previews/families/estrildidae.webp)

### カケス・カササギ · *Corvidae* — 135 種

![カケス・カササギ](previews/families/corvidae.webp)

### 新世界のムクドリモドキ・オオツリスドリ · *Icteridae* — 107 種

![新世界のムクドリモドキ・オオツリスドリ](previews/families/icteridae.webp)

### サイチョウ · *Bucerotidae* — 64 種

![サイチョウ](previews/families/bucerotidae.webp)

### ムクドリ・キュウカンチョウ · *Sturnidae* — 118 種

![ムクドリ・キュウカンチョウ](previews/families/sturnidae.webp)

### 目ごとに1枚ずつ

![目ごとに1枚ずつ](previews/orders.webp)

## 収録内容

| | |
|---|---|
| `stickers/<Order>/<Family>/<Genus_species>.webp` | 1種につき1枚の、白い縁取り付き透過ステッカー。長辺は約1,000 px。`<Genus_species>.<subspecies>.webp`は、かつて独立種だったものの亜種ステッカー91枚 |
| `data/species.json` | 1種につき1レコード。完全なデータセットで、分類、名前、ID、分布と亜種、体の計測値と生態、保全状況、ステッカーとその出典を含みます。フィールドの説明は[data/README.md](data/README.md) |
| `data/species.csv` | 同じ内容を表計算ソフト向けに平坦化したもの |
| `data/crosswalk-ioc15.2-avilist2026.csv` | IOC 15.2の各種がAviList v2026でどうなったか：同じ、改名、統合、分割 |
| `data/names.csv` | 43言語の名前（46列：中国語、フランス語、ポルトガル語はそれぞれ2種類ある） |
| `data/languages.json` | 言語コードと、それぞれがIOCの多言語表のどの列に由来するか |
| `data/field-guide.zh-Hans.json` | 1,596種の簡体字中国語によるフィールドガイドの解説（外見、識別点、雌雄・年齢、似た種）、CC BY-SA 4.0 |

レコードはこのような形です（名前は一部省略）。

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

## 収録範囲

- 名前：英語はAviListの英語名で、全種をカバーしています。ほかの言語はIOCの多言語リストに由来し、種の範囲が変わっていないものだけに引き継いでいます。統合・分割で範囲が変わった種と新種の計129種は、古い名前が別の鳥の集まりを指しているおそれがあるため、当てはめずに空けてあります。簡体字中国語は10,947種をカバーし、範囲が変わった種は1つずつ人の目で確認しました。フランス語、スペイン語、ドイツ語、ロシア語、日本語、繁体字中国語は94%以上です。韓国語、アラビア語、タイ語、ペルシア語などは、IOCのリストにある分だけなので、今のところ数百種から1,000種ほどにとどまります。詳しくは`data/names.csv`を見てください。
- 日本語名はIOCのリストから直接取っており、11,011種のうち10,418種に付いています。
- ID：eBird 10,983、Avibase 11,011（どちらもAviList由来）、Wikidata 10,757、GBIF 10,477。
- ステッカー：11,011種すべてに加えて、亜種ステッカー91枚。ファイルは合計11,102枚です。

## ステッカーの作り方と品質

ステッカーのファイル11,102枚はすべてAIイラストです。種ごとに参考写真を探し（2026年11月以降は、見つかった場合、複数の撮影者の写真を並べた参考ボード）、GPT-imageでステッカーを描き、拡大して切り抜きました。似たものを作りたい方へ：プロンプト、ポーズの指定方法、審査基準を[docs/how-the-stickers-are-made.md](docs/how-the-stickers-are-made.md)（英語）にまとめています。

ステッカーはすべて、別のAI審査者が採点しました。2026年11月には、フィールドガイドの図版として使えるかという、より厳しい基準ですべてのステッカーを再審査しました。合格するには、識別、羽色と模様、嘴と目、脚と足、体の比率の各項目が4点満点で3点以上、識別は4点であり、審査者がフィールドガイドの図版として受け入れられると判断する必要があります。77枚はそのまま合格し、残る11,025枚は新しい版が合格するまで生成し直しました。

- **11,102枚すべてが品質基準を満たしています**（`"meetsQualityBar": true`）。どれも上記のより厳しい審査に合格しています。ただし審査者は鳥の専門家ではなくAIなので、合格したからといって誤りがないわけではありません。バードウォッチャーが見つけた誤りの種類は[issue #1](../../issues/1)と[issue #3](../../issues/3)を見てください。
- **一部のステッカーは参考写真を使わず、文章による説明だけで生成しています**（`data/species.json` の `"reference": null`。枚数は [data/README.md](data/README.md#reference-photos) を参照）。写真と照らし合わせたステッカーより誤りが含まれやすくなっています。[birdalbum.com](https://birdalbum.com/) では、これらのステッカーの種のページに、別に注意書きを付けています。

これらはイラストであり、フィールドガイドの図版ではありません。鳥の雰囲気を伝える絵として扱い、細部に頼る場合は図鑑で確認してください。間違いを見つけたら[issueを立てて](../../issues/new/choose)ください。バードウォッチャーからの訂正は、このプロジェクトにとって何よりありがたい貢献です。

**ある鳥のグループに詳しい方へ。**[科をひとつレビュー](../../issues/new?template=family-review.yml)して、間違っているステッカーを教えてください。指摘されたものはすべて生成し直して再審査し、お名前を [CONTRIBUTORS.md](CONTRIBUTORS.md) に記載します。

## 参考写真について

**参考写真の役割**。ステッカーが表すのは、その種の見た目です。羽色と斑紋、くちばし、目、脚、体の比率。これらはその鳥についての事実であり、野外図鑑が文章で説明しているのと同じ内容です。文章の説明だけでは画像生成モデルが正しく描けないことが多いため、参考写真を使っています。

**参考写真の使い方**。各種を描くとき、画像生成モデルには1枚または数枚の参考写真と、識別点を書いた説明文を見せ、新しいイラストを描かせます。写真の使い方は、ステッカーを作った時期によって違います。2026年11月より前に生成した初期のステッカーは、1種につき写真を1枚使い、その写真の鳥の見た目と姿勢の両方を参考にしました。2026年11月以降は、写真は鳥の見た目を確かめるためだけに使い、写真の姿勢、構図、背景、光は使いません。どの鳥も私たちが決めた標準姿勢で、背景なしで描いています（ほとんどのグループは立った真横の姿、泳ぐ鳥や飛ぶ鳥など一部のグループには専用の姿勢があります）。見つかった場合は複数の撮影者の写真を使い、ステッカーが特定の1枚ではなくその種を表すようにしています（複数の画像を並べた参考ボードで作ったステッカーは6,369枚）。初期のステッカーも、77枚を除いてすでにこの方法で生成し直しました。その77枚は、より厳しい審査にそのまま合格したものです。描いたあとは、別のモデルが識別点に照らして確認します。このリポジトリに参考写真は含まれていません。

**クレジットと取り下げ**。記録してある各ステッカーの参考写真（ページと、わかっている場合は作者とライセンス）は`data/species.json`の`sticker.reference`に載っています。文章による説明だけで生成したステッカーは`"reference": null`です。参考写真のライセンス別の内訳は[data/README.md](data/README.md#reference-photos)にあります。あなたの写真が参考として使われていて、そうしてほしくない場合は、[ステッカーの削除・差し替えを申請](../../issues/new?template=takedown.yml)してください。7日以内にそのステッカーを差し替えます。

## 使い方

ファイルはそのまま読み込めます。

```
https://raw.githubusercontent.com/alchaincyf/huashu-bird-sticker/main/stickers/Accipitriformes/Accipitridae/Accipiter_nisus.webp
```

```python
import json
species = json.load(open("data/species.json"))["species"]
by_name = {s["scientificName"]: s for s in species}
print(by_name["Pica pica"]["names"]["ja"], by_name["Pica pica"]["sticker"]["file"])
```

リポジトリ全体は約700 MBあります。データと一部のステッカーだけを取得するには次のようにします。

```bash
git clone --filter=blob:none --sparse https://github.com/alchaincyf/huashu-bird-sticker
cd huashu-bird-sticker && git sparse-checkout set data stickers/Strigiformes
```

## 利用例

- [水杉输入法 MSIME](https://github.com/metasequoiaime/msime)：クロスプラットフォームの中国語入力システム。鳥名辞書パックは `data/species.json` から作られています。
- [Everybird](https://github.com/yusuftaleb/everybird-stickers)（Yusuf Taleb）：ステッカーを縮小し、eBird コードで管理して使用。
- [Awesome Public Datasets](https://github.com/awesomedata/apd-core) の Biology に掲載。

どこかで使っていたら issue で教えてください。ここに追加します。

## クレジット

- 分類、英語名、分布、eBirdとAvibaseのID：AviList Core Team. 2026. AviList: The Global Avian Checklist, v2026. https://doi.org/10.2173/avilist.v2026、CC BY 4.0。
- ほかの言語の名前：IOC World Bird List v15.2、Gill、Donsker & Rasmussen（編）、CC BY 3.0。
- ほかのデータベース間のID：Wikidata（CC0）。
- 体の計測値と生態：AVONET、Tobias他、2022年、*Ecology Letters*、CC BY 4.0。
- 参考写真の撮影者：種ごとに`data/species.json`に記載しています。参考写真はこのリポジトリには含まれていません。
- ステッカーは、iOS向けのバードウォッチング記録アプリ「鸣迹（Mingji）」のために描いたものです。

あなたの写真がステッカーの参考として使われていて、そうしてほしくない場合は、[ステッカーの削除・差し替えを申請](../../issues/new?template=takedown.yml)してください。7日以内にそのステッカーを差し替えます。
