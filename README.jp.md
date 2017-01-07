# [Gamemakin](https://gamemak.in) UE4 Style Guide() {

*Unreal Engine 4 への最も合理的なアプローチ*

[Airbnb Javascript Style Guide](https://github.com/airbnb/javascript) に大きな影響を受けています。

[![Analytics](https://ga-beacon.appspot.com/UA-80567399-1/repo?useReferrer)](#) ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

## Unreal Engine 4 Linter Plugin

このスタイルガイドに対してプロジェクトをチェックする自動化された方法は、[the Unreal Engine marketplace](https://www.unrealengine.com/marketplace/linter) で購入できます。 このプラグインのソースコードは最終的に無料になりますが、ソースコードからエンジンを構築せずにUE4で使用するには、マーケットプレイス版を使用してください。

## 本ドキュメントへリンクする場合

このスタイルガイドの各セクションは、簡単な参照と簡単なリンクのために番号が付けられています。 http://ue4.style の最後にハッシュタグとセクション番号を付加するだけで、任意のセクションに直接リンクすることができます
たとえば、このスタイルガイドの第1原則に誰かを送りたい場合は、http：//ue4.style#0.1という結果になる `＃0.1` を追加します。

## Forks と翻訳

このレポへのプルリクエストに適していない注目すべきフォークまたは翻訳を行った場合は、ここにフォークまたは翻訳を追加するプルリクエストを提出してください。

* [Korean Translation](https://github.com/ymkim50/ue4-style-guide/blob/master/README_Kor.md) by ymkim50
* [Russian Translation](https://github.com/CosmoMyzrailGorynych/ue4-style-guide-rus/blob/master/README.md) by CosmoMyzrailGorynych

## 重要用語

<a name="terms-level-map"></a>
##### Levels/Maps

'map' という語は一般に、平均的な人が'level'と呼んでいるものを指し、互換的に使用することができます。この用語の歴史については[こちら](https://en.wikipedia.org/wiki/Level_(video_gaming))を参照してください。

<a name="terms-cases"></a>
##### Cases

物事に名前を付ける方法はいくつかあります。 いくつかの一般的なケーシングタイプがあります:

> ###### PascalCase
>
> すべての単語を大文字にし、スペースをすべて削除します。, e.g. `DesertEagle`, `StyleGuide`, `ASeriesOfWords`.
> 
> ###### camelCase
>
> 最初の文字は常に小文字ですが、その後のすべての単語は大文字で始まります。, e.g. `desertEagle`, `styleGuide`, `aSeriesOfWords`.
>
> ###### Snake_case
>
> 単語は任意に大文字または小文字を開始できますが、単語はアンダースコアで区切られます。, e.g. `desert_Eagle`, `Style_Guide`, `a_Series_of_Words`.


<a name="0"></a>
## 0. 原則

これらの原則は[idomatic.js style guide](https://github.com/rwaldron/idiomatic.js/)に即します。

<a name="0.1"></a>
### 0.1 あなたのUE4プロジェクトにすでにスタイルガイドがある場合は、それに従ってください。

既存のスタイルガイドがあるチームまたはプロジェクトで作業している場合は、それを尊重する必要があります。 既存のスタイルガイドとこのガイドとの間に矛盾がある場合は、既存のスタイルガイドに従わなくてはなりません。

スタイルガイドは生き生きしたドキュメントでなければなりません。すべての用途に変更のメリットがあると感じる場合は、既存のスタイルガイドとこのガイドのスタイルガイドの変更を提案する必要があります。

> #### "スタイル上の議論は無意味です。スタイルガイドが必要です。それに従うべきです"
> [_Rebecca Murphey_](https://rmurphey.com)

<a name="0.2"></a>
### 0.2 すべてのUnreal Engine 4プロジェクトの構造、アセット、およびコードは、どれだけの人が貢献しても、1人の人が作成したように見えるはずです。

あるプロジェクトから別のプロジェクトに移っても、スタイルや構造を再学習してはいけません。 スタイルガイドに従うことで、不必要な推測やあいまいがなくなります。

また、スタイルについて考える必要もなく、指示に従うだけで、より生産的な作成と保守が可能です。 このスタイルガイドはベストプラクティスを念頭に置いて書かれています。つまり、このスタイルガイドに従って、問題を追跡するのを最小限に抑えることができます。

<a name="0.3"></a>
### 0.3 友人は友人に悪いスタイルをさせません。

スタイルガイドまたはスタイルガイドなしのいずれかで作業している人がいる場合は、修正するようにしてください。

チーム内で働いたり、[Unreal Slackers](http://join.unrealslackers.org/) などのコミュニティで議論するときは、一貫性があるときに助けて助けを求めるのがはるかに簡単です。 誰も、誰かの青写真スパゲッティを解くのを手伝ったり、理解できない名前の資産を扱ったりするのを好む人はいません。

あなたの仕事の人が異なるが、一貫性があり、正真正銘のスタイルガイドに従うのを手助けしているなら、あなたはそれに適応できるはずです。 スタイルガイドに準拠していない場合は、ここで指示してください。

<a name="0.4"></a>
### 0.4 スタイルガイドのないチームは私のチームではありません。

Unreal Engine 4チームに参加するときは、最初の質問の1つが「あなたはスタイルガイドを持っていますか？」でなければなりません。 答えがノーなら、あなたはチームとして働く能力について懐疑的でなければなりません。

<a name="toc"></a>
## 目次

> 1. [Asset Naming Conventions](#anc)
> 1. [Directory Structure](#structure)
> 1. [Blueprints](#bp)

<a name="anc"></a>
<a name="1"></a>
## 1. アセットの命名規則 ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

命名規則は法律として扱うべきです。 命名規則に準拠したプロジェクトでは、アセットの管理、検索、解析、維持管理が非常に簡単です。

ほとんどのものに接頭辞が付いています。接頭辞は一般的にアセットタイプの略語で、その後にアンダースコアが続きます。

<a name="base-asset-name"></a>
<a name="1.1"></a>
### 1.1 基本アセット名 - `Prefix_BaseAssetName_Variant_Suffix` ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

すべてのアセットに _Base Asset Name_ が必要です。基本資産名は、関連する資産の論理的なグループを表します。この論理グループの一部である資産は、 `Prefix_BaseAssetName_Variant_Suffix`の標準に従うべきです。

パターン `Prefix_BaseAssetName_Variant_Suffix` を念頭に置いて常識的に使うことは、一般的には良い資産名を保証するのに十分です。各要素に関するいくつかの詳細なルールがあります。

`Prefix`と` Suffix`は、以下の [Asset Name Modifier](#asset-name-modifiers) テーブルを介して、資産タイプによって決定されます。

`BaseAssetName`は、この資産群の文脈に関連した簡単で分かりやすい名前によって決定されるべきです。たとえば、Bobという名前のキャラクターがあった場合、Bobのすべてのアセットは `Base`の` Bob`という名前になります。

独特で特殊な資産のバリエーションの場合、 `Variant` は、資産の基本名のサブセットである資産の論理的なグループ分けを表す簡単で分かりやすい名前のいずれかです。例えば、Bobが複数のスキンを持っていた場合、これらのスキンは `BaseAssetName`として` Bob`を使用しますが、認識可能な `Variant`を含みます。 「Evil」スキンは `Bob_Evil` と呼ばれ、「Retro」スキンは `Bob_Retro` と呼ばれる。

ユニークではあるが一般的な資産のバリエーションでは、 `Variant` は `01` から始まる2桁の数字です。例えば、謎めいた岩石を生成する環境アーティストがいる場合、名前は `Rock_01`、` Rock_02`、 `Rock_03` などとなります。まれな例外を除いて、3桁の変種番号は必要ありません。資産が100以上ある場合は、異なるベース名で複数のバリアント名を使用して整理することを検討する必要があります。

資産バリアントの作成方法に応じて、バリアント名を連結することができます。たとえば、Arch Vizプロジェクトのフロアリングアセットを作成する場合は、`Flooring_Marble_01`, `Flooring_Maple_01`, `Flooring_Tile_Squares_01` などの連鎖変形を含むベース名 `Flooring` を使用する必要があります。

<a name="1.1-examples"></a>
#### 1.1 例

##### 1.1e1 Bob

| Asset Type              | Asset Name                                                 |
| ----------------------- | ---------------------------------------------------------- |
| Skeletal Mesh           | SK_Bob                                                     |
| Material                | M_Bob                                                      |
| Texture (Diffuse/Albedo)| T_Bob_D                                                    |
| Texture (Normal)        | T_Bob_N                                                    |
| Texture (Evil Diffuse)  | T_Bob_Evil_D                                               |

##### 1.1e2 Rocks

| Asset Type              | Asset Name                                                 |
| ----------------------- | ---------------------------------------------------------- |
| Static Mesh (01)        | S_Rock_01                                                  |
| Static Mesh (02)        | S_Rock_02                                                  |
| Static Mesh (03)        | S_Rock_03                                                  |
| Material                | M_Rock                                                     |
| Material Instance (Snow)| MI_Rock_Snow                                               |

### 1.2 アセット名修飾子　![#](https://img.shields.io/badge/lint-supported-green.svg)

アセットの名前を付けるときは、これらのテーブルを使用してアセットの　[Base Asset Name](#base-asset-name)　で使用する接頭辞と接尾辞を決定します。

#### Sections

> 1.2.1 [Most Common](#anc-common)

> 1.2.2 [Animations](#anc-animations)

> 1.2.3 [Artificial Intelligence](#anc-ai)

> 1.2.4 [Blueprints](#anc-bp)

> 1.2.5 [Materials](#anc-materials)

> 1.2.6 [Textures](#anc-textures)

> 1.2.7 [Miscellaneous](#anc-misc)

> 1.2.8 [Paper 2D](#anc-paper2d)

> 1.2.9 [Physics](#anc-physics)

> 1.2.10 [Sound](#anc-sound)

> 1.2.11 [User Interface](#anc-ui)

> 1.2.12 [Effects](#anc-effects)

<a name="anc-common"></a>
<a name="1.2.1"></a>
#### 1.2.1 Most Common ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | Notes                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Level / Map             |            |            | [ <Maps></Maps> フォルダ内に配置するべき.](#2.3) |
| Level (Persistent)      |            | _P         |                                  |
| Level (Audio)           |            | _Audio     |                                  |
| Level (Lighting)        |            | _Lighting  |                                  |
| Level (Geometry)        |            | _Geo       |                                  |
| Level (Gameplay)        |            | _Gameplay  |                                  |
| Blueprint               | BP_        |            |                                  |
| Material                | M_         |            |                                  |
| Static Mesh             | S_ or SM_  |            | どちらか1つだけを選択。 S_ を優先する。        |
| Skeletal Mesh           | SK_        |            |                                  |
| Texture                 | T_         | _?         | [Textures](#anc-textures) を参照してください。   |
| Particle System         | PS_        |            |                                  |
| Widget Blueprint        | WBP_ or WB_|            | どちらか1つだけを選択。 WBP_ を優先する。      |

マップと呼ばれるフォルダにある必要があります

<a name="anc-animations"></a>
<a name="1.2.2"></a>
#### 1.2.2 Animations ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | Notes                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Aim Offset              | AO_        |            |                                  |
| Aim Offset 1D           | AO_        |            |                                  |
| Animation Blueprint     | ABP_       |            |                                  |
| Animation Composite     | AC_        |            |                                  |
| Animation Montage       | AM_        |            |                                  |
| Animation Sequence      | A_ or AS_  |            | どちらか1つだけを選択。 A_ を優先する。        |
| Blend Space             | BS_        |            |                                  |
| Blend Space 1D          | BS_        |            |                                  |
| Level Sequence          | LS_        |            |                                  |
| Morph Target            | MT_        |            |                                  |
| Paper Flipbook          | PFB_       |            |                                  |
| Rig                     | Rig_       |            |                                  |
| Skeletal Mesh           | SK_        |            |                                  |
| Skeleton                | SKEL_      |            |                                  |

<a name="anc-ai"></a>
<a name="1.2.3"></a>
### 1.2.3 Artificial Intelligence ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | Notes                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| AI Controller           | AIC_       |            |                                  |
| Behavior Tree           | BT_        |            |                                  |
| Blackboard              | BB_        |            |                                  |
| Decorator               | BTDecorator_ |          |                                  |
| Service                 | BTService_ |            |                                  |
| Task                    | BTTask_    |            |                                  |

<a name="anc-bp"></a>
<a name="1.2.4"></a>
### 1.2.4 Blueprints ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | Notes                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Blueprint               | BP_        |            |                                  |
| Blueprint Function Library | BPFL_   |            |                                  |
| Blueprint Interface     | BPI_       |            |                                  |
| Blueprint Macro Library | BPML_      |            | 可能な限り、マクロライブライを使うべきでない。 |
| Enumeration             | E          |            | アンダースコアを付けない。                   |
| Structure               | F or S     |            | アンダースコアを付けない。                   |
| Widget Blueprint        | WBP_ or WB_|            | どちらか1つだけを選択。 WBP_ を優先する。      |

<a name="anc-materials"></a>
<a name="1.2.5"></a>
### 1.2.5 Materials ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | Notes                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Material                | M_         |            |                                  |
| Material (Post Process) | PP_        |            |                                  |
| Material Function       | MF_        |            |                                  |
| Material Instance       | MI_        |            |                                  |
| Material Parameter Collection | MPC_ |            |                                  |
| Subsurface Profile      | SP_ or SSP_|            | どちらか1つだけを選択。 SP_ を優先する。       |
| Physical Materials      | PM_        |            |                                  |

<a name="anc-textures"></a>
<a name="1.2.6"></a>
### 1.2.6 Textures ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | Notes                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Texture                 | T_         |            |                                  |
| Texture (Diffuse/Albedo/Base Color)| T_ | _D      |                                  |
| Texture (Normal)        | T_         | _N         |                                  |
| Texture (Roughness)     | T_         | _R         |                                  |
| Texture (Alpha/Opacity) | T_         | _A         |                                  |
| Texture (Ambient Occlusion) | T_     | _O or _AO  | どちらか1つだけを選択。 _O を優先する。       |
| Texture (Bump)          | T_         | _B         |                                  |
| Texture (Emissive)      | T_         | _E         |                                  |
| Texture (Mask)          | T_         | _M         |                                  |
| Texture (Specular)      | T_         | _S         |                                  |
| Texture (Packed)        | T_         | _*         | 下記の注記 [packing](#anc-textures-packing) を参照 |
| Texture Cube            | TC_        |            |                                  |
| Media Texture           | MT_        |            |                                  |
| Render Target           | RT_ or RTT_|            | どちらか1つだけを選択。 RT_ を優先する。       |
| Cube Render Target      | RTC_       |            |                                  |
| Texture Light Profile   | TLP        |            |                                  |

<a name="anc-textures-packing"</a>
<a name="1.2.6.1"></a>
#### 1.2.6.1 Texture Packing ![#](https://img.shields.io/badge/lint-unsupported-red.svg)
テクスチャデータの複数のレイヤを1つのテクスチャにパックするのが一般的な方法です。 これの一例は、エミッシブ、ラフネス、アンビエントオクルージョンをテクスチャの赤、緑、青のチャンネルとしてまとめたものです。 接尾辞を決定するには、上の指定された接尾辞の文字を単純にスタックします。 `_ERO`。

> Diffuse/AlbedoのアルファチャンネルにAlpha/Opacityレイヤーを含めることは一般的に受け入れられます。これは一般的な方法で、 `_D` 接尾辞に ` A` を追加することはオプションです。

Diffuse/AlbedoのアルファチャンネルのAlpha/Opacityマスク以外の4チャンネルのデータをテクスチャ（RGBA）にパッキングするのはお勧めできません。

<a name="anc-misc"></a>
<a name="1.2.7"></a>
### 1.2.7 Miscellaneous ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | Notes                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Animated Vector Field   | VFA_       |            |                                  |
| Camera Anim             | CA_        |            |                                  |
| Color Curve             | Curve_     | _Color     |                                  |
| Curve Table             | Curve_     | _Table     |                                  |
| Data Asset              | *_         |            | 接頭辞はクラスに基づいている必要があります。 |
| Data Table              | DT_        |            |                                  |
| Float Curve             | Curve_     | _Float     |                                  |
| Foliage Type            | FT_        |            |                                  |
| Force Feedback Effect   | FFE_       |            |                                  |
| Landscape Grass Type    | LG_        |            |                                  |
| Landscape Layer         | LL_        |            |                                  |
| Matinee Data            | Matinee_   |            |                                  |
| Media Player            | MP_        |            |                                  |
| Object Library          | OL_        |            |                                  |
| Redirector              |            |            | これらはできるだけ早く修正する必要があります。 |
| Sprite Sheet            | SS_        |            |                                  |
| Static Vector Field     | VF_        |            |                                  |
| Touch Interface Setup   | TI_        |            |                                  |
| Vector Curve            | Curve_     | _Vector    |                                  |

<a name="anc-paper2d"></a>
<a name="1.2.8"></a>
### 1.2.8 Paper 2D ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | Notes                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Paper Flipbook          | PFB_       |            |                                  |
| Sprite                  | SPR_       |            |                                  |
| Sprite Atlas Group      | SPRG_      |            |                                  |
| Tile Map                | TM_        |            |                                  |
| Tile Set                | TS_        |            |                                  |

<a name="anc-physics"></a>
<a name="1.2.9"></a>
### 1.2.9 Physics ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | Notes                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Physical Material       | PM_        |            |                                  |
| Physical Asset	  | PHYS_      |            |                                  |
| Destructible Mesh       | DM_        |            |                                  |

<a name="anc-sounds"></a>
<a name="1.2.10"></a>
### 1.2.10 Sounds ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | Notes                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Dialogue Voice          | DV_        |            |                                  |
| Dialogue Wave           | DW_        |            |                                  |
| Media Sound Wave        | MSW_       |            |                                  |
| Reverb Effect           | Reverb_    |            |                                  |
| Sound Attenuation       | ATT_       |            |                                  |
| Sound Class             |            |            | 接頭辞/接尾辞を付けません。 SoundClassesフォルダ配下に置べき |
| Sound Concurrency       |            | _SC        | SoundClassの後に名前付けるべき |
| Sound Cue               | A_         | _Cue       |                                  |
| Sound Mix               | Mix_       |            |                                  |
| Sound Wave              | A_         |            |                                  |

<a name="anc-ui"></a>
<a name="1.2.11"></a>
### 1.2.11 User Interface ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | Notes                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Font                    | Font_      |            |                                  |
| Slate Brush             | Brush_     |            |                                  |
| Slate Widget Style      | Style_     |            |                                  |
| Widget Blueprint        | WBP_ or WB_|            | どちらか1つだけを選択。 WBP_ を優先する。      |

<a name="anc-effects"></a>
<a name="1.2.12"></a>
### 1.2.12 Effects ![#](https://img.shields.io/badge/lint-supported-green.svg)

| Asset Type              | Prefix     | Suffix     | Notes                            |
| ----------------------- | ---------- | ---------- | -------------------------------- |
| Particle System         | PS_        |            |                                  |
| Material (Post Process) | PP_        |            |                                  |

<a name="2"></a>
<a name="structure"></a>
## 2. コンテンツディレクトリの構造 ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

アセット名と同様に重要なことに、プロジェクトのディレクトリ構造は法律とみなすべきです。 資産の命名規則とコンテンツディレクトリ構造が両立し、いずれかの違反は不要な混乱の原因となります。

UE4プロジェクトのコンテンツをレイアウトする方法は複数あります。 このスタイルでは、アセットをグループ化する別の共通構造ではなく、特定のタイプのアセットを検索するために、コンテンツブラウザのフィルタリングと検索機能にもっと依存する構造を使用します。

>上の [naming convention](#1.2) を使用している場合、フォルダに `Meshes`, `Textures`, および `Materials`などの類似の型のアセットを格納することは、アセットの型がすでにソートされているため、 プレフィックスだけでなく、コンテンツブラウザでフィルタリングすることができます。


<a name="2e1"><a>
### 2e1 プロジェクトのコンテンツ構造の例
<pre>
|-- Content
    |-- <a href="#2.2">GenericShooter</a>
        |-- Art
        |   |-- Industrial
        |   |   |-- Ambient
        |   |   |-- Machinery
        |   |   |-- Pipes
        |   |-- Nature
        |   |   |-- Ambient
        |   |   |-- Foliage
        |   |   |-- Rocks
        |   |   |-- Trees
        |   |-- Office
        |-- Characters
        |   |-- Bob
        |   |-- Common
        |   |   |-- <a href="#2.7">Animations</a>
        |   |   |-- Audio
        |   |-- Jack
        |   |-- Steve
        |   |-- <a href="#2.1.3">Zoe</a>
        |-- <a href="#2.5">Core</a>
        |   |-- Characters
        |   |-- Engine
        |   |-- <a href="#2.1.2">GameModes</a>
        |   |-- Interactables
        |   |-- Pickups
        |   |-- Weapons
        |-- Effects
        |   |-- Electrical
        |   |-- Fire
        |   |-- Weather
        |-- <a href="#2.4">Maps</a>
        |   |-- Campaign1
        |   |-- Campaign2
        |-- <a href="#2.8">MaterialLibrary</a>
        |   |-- Debug
        |   |-- Metal
        |   |-- Paint
        |   |-- Utility
        |   |-- Weathering
        |-- Placeables
        |   |-- Pickups
        |-- Weapons
            |-- Common
            |-- Pistols
            |   |-- DesertEagle
            |   |-- RocketPistol
            |-- Rifles
</pre>

The reasons for this structure are listed in the following sub-sections.

### 章

> 2.1 [Folder Names](#structure-folder-names)

> 2.2 [Top-Level Folders](#structure-top-level)

> 2.3 [Developer Folders](#structure-developers)

> 2.4 [Maps](#structure-maps)

> 2.5 [Core](#structure-core)

> 2.6 [`Assets` and `AssetTypes`](#structure-assettypes)

> 2.7 [Large Sets](#structure-large-sets)

> 2.8 [Material Library](#structure-material-library)


<a name="2.1"></a>
<a name="structure-folder-names"><a>
### 2.1  フォルダ名 ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

これらは、コンテンツ構造内の任意のフォルダに名前を付ける一般的な規則です。

<a name="2.1.1"></a>
#### 2.1.1 常に PascalCase を使用 [<sup>*</sup>](#terms-cases) ![#](https://img.shields.io/badge/lint-supported-green.svg)

PascalCaseは、大文字で名前を始めることを意味し、スペースを使用する代わりに、すべての次の単語も大文字で始まります。 たとえば、`DesertEagle`, `RocketPistol`,および`ASeriesOfWords` などです。

See [Cases](#terms-cases).

<a name="2.1.2"></a>
#### 2.1.2 決してスペースを使用しないでください ![#](https://img.shields.io/badge/lint-supported-green.svg)

[2.1.1](#2.1.1) を再実施し、決してスペースを使用しないでください。 スペースによって、さまざまなエンジニアリングツールやバッチ処理が失敗する可能性があります。 理想的には、プロジェクトのルートには空白が含まれておらず、 `C:\Users\My Name\My Documents\Unreal Projects` の代わりに `D:\Project`のような場所に置かれているのが理想的です。

<a name="2.1.3"></a>
#### 2.1.3 Unicode文字とその他の記号を使用しないでください ![#](https://img.shields.io/badge/lint-supported-green.svg)

あなたのゲームキャラクターの名前が「Zoë」の場合、そのフォルダー名は `Zoe`でなければなりません。 Unicode文字はエンジニアリングツールの [Spaces](#2.1.2) より悪くなり、UE4の一部ではパス内のUnicode文字もサポートされません。

これに関連して、プロジェクトに [説明できない問題](https://answers.unrealengine.com/questions/101207/undefined.html) があり、コンピュータのユーザー名がUnicode文字（つまり、あなたの名前は `Zoë`）である場合、 あなたの `My Documents`フォルダにあるプロジェクトはこの問題を抱えています。 単にプロジェクトを `D:\Project`のようなものに移動するだけで、これらの不思議な問題が修正されます。

`@`, `-`, `_`, `,`, `*`, と `#` のような `a-z`, `A-Z`, 及び `0-9` 以外の文字を使うと、 他のプラットフォーム、ソース管理、および弱いエンジニアリングツールの問題を追跡することは困難です。

<a name="2.2"></a>
<a name="structure-top-level"><a>
### 2.2 Use A Top Level Folder For Project Specific Assets ![#](https://img.shields.io/badge/lint-supported-green.svg)

All of a project's assets should exist in a folder named after the project. For example, if your project is named 'Generic Shooter', _all_ of it's content should exist in `Content/GenericShooter`.

> The `Developers` folder is not for assets that your project relies on and therefore is not project specific. See [2.2](#2.2) for details about this.

There are multiple reasons for this approach.

<a name="2.2.1"></a>
#### 2.2.1 No Global Assets

Often in code style guides it is written that you should not pollute the global namespace and this follows the same principle. When assets are allowed to exist outside of a project folder it often becomes much harder to enforce a strict structure layout as assets not in a folder encourages the bad behavior of not having to organize assets.

Every asset should have a purpose, otherwise it does not belong in a project. If an asset is an experimental test and shouldn't be used by the project it should be put in a [`Developer`](#2.3) folder.

<a name="2.2.2"></a>
#### 2.2.2 Reduce Migration Conflicts

When working on multiple projects it is common for a team to copy assets from one project to another if they have made something useful for both. When this occurs, the easiest way to perform the copy is to use the Content Browser's Migrate functionality as it will copy over not just the selected asset but all of its dependencies.

These dependencies are what can easily get you into trouble. If two project's assets do not have a top level folder and they happen to have similarly named or already previously migrated assets, a new migration can accidentally wipe any changes to the existing assets.

This is also the primary reason why Epic's Marketplace staff enforces the same policy for submitted assets.

After a migration, safe merging of assets can be done using the 'Replace References' tool in the content browser with the added clarity of assets not belonging to a project's top level folder are clearly pending a merge. Once assets are merged and fully migrated, there shouldn't be another top level folder in your Content tree. This method is _100%_ guaranteed to make any migrations that occur completely safe.

<a name="2.2.2e1"></a>
##### 2.2.2e1 Master Material Example

For example, say you created a master material in one project that you would like to use in another project so you migrated that asset over. If this asset is not in a top level folder, it may have a name like `Content/MaterialLibrary/M_Master`. If the target project doesn't have a master material already, this should work without issue.

As work on one or both projects progress their respective master materials may change to be tailored for their specific projects due to the course of normal development.

The issue comes when, for example, an artist for one project created a nice generic modular set of static meshes and someone wants to include that set of static meshes in the second project. If the artist who created the assets used material instances based on `Content/MaterialLibrary/M_Master` as they're instructed to, when a migration is performed there is a great chance of conflict for the previously migrated `Content/MaterialLibrary/M_Master` asset.

This issue can be hard to predict and hard to account for. The person migrating the static meshes may not be the same person who is familiar with the development of both project's master material, and they may not be even aware that the static meshes in question rely on material instances which then rely on the master material. The Migrate tool requires the entire chain of dependencies to work however, and so it will be forced to grab `Content/MaterialLibrary/M_Master` when it copies these assets to the other project and it will overwrite the existing asset.

It is at this point where if the master materials for both projects are incompatible in _any way_, you risk breaking possibly the entire material library for a project as well as any other dependencies that may have already been migrated, simply because assets were not stored in a top level folder. The simple migration of static meshes now becomes a very ugly task.

<a name="2.2.3"></a>
#### 2.2.3 Samples, Templates, and Marketplace Content Are Risk-Free

An extension to [2.2.2](#2.2.2), if a team member decides to add sample content, template files, or assets they bought from the marketplace, it is guaranteed that these new assets will not interfere with the project in any way unless your project's top level folder is not uniquely named.

You can not trust marketplace content to fully conform to the [top level folder rule](#2.2). There exist many assets that have the majority of their content in a top level folder but also have possibly modified Epic sample content as well as level files polluting the global `Content` folder.

When adhering to [2.2](#2.2), the worst marketplace conflict you can have is if two marketplace assets both have the same Epic sample content. If all your assets are in a project specific folder, including sample content you may have moved into your folder, your project will never break.

#### 2.2.4 DLC, Sub-Projects, and Patches Are Easily Maintained

If your project plans to release DLC or has multiple sub-projects associated with it that may either be migrated out or simply not cooked in a build, assets relating to these projects should have their own separate top level content folder. This make cooking DLC separate from main project content far easier. Sub-projects can also be migrated in and out with minimal effort. If you need to change a material of an asset or add some very specific asset override behavior in a patch, you can easily put these changes in a patch folder and work safely without the chance of breaking the core project.

<a name="2.3"></a>
<a name="structure-developers"></a>
### 2.3 ローカルテスト用にDevelopersフォルダを使用してください ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

プロジェクトの開発中に、チームメンバーがコアプロジェクトを危険にさらすことなく自由に実験できる「サンドボックス」を持つことは非常に一般的です。この作業が進行中である可能性があるため、これらのチームメンバはプロジェクトのソース管理サーバーに資産を配置することができます。すべてのチームがデベロッパーフォルダの使用を必要とするわけではありませんが、それらを使用するチームはソース管理に提出された資産に共通の問題に遭遇することがよくあります。

チームメンバーが、使用準備が整っていない資産を誤って使用することは非常に簡単で、その資産が削除されると問題が発生する可能性があります。たとえば、アーティストが静的メッシュのモジュラセットを反復処理していて、サイジングとグリッドのスナッピングが正しく行われているとします。世界の建築家がこれらの資産をメインプロジェクトフォルダに見た場合、彼らは信じられないほどの変更や削除を受ける可能性があることを知らずに、レベル全体でそれらの資産を使用するかもしれません。これにより、チームの全員が大量の再作業を行うことになります。

これらのモジュラーアセットがDeveloperフォルダに配置されている場合、世界の建築家は決してそれらを使用する理由があってはならず、問題は起こりません。コンテンツブラウザには、デベロッパーフォルダを非表示にする特定の表示オプションがあります（デフォルトでは非表示になっています）ので、通常の使用状態で誤ってデベロッパーアセットを使用することはできません。

アセットを使用できるようになると、アーティストはアセットをプロジェクト固有のフォルダに移動し、リダイレクタを修正するだけです。これは本質的に資産を実験から生産に「促進」しています。

<a name="2.4"></a>
<a name="structure-maps"></a>
### 2.4 すべてのMap[<sup>*</sup>](#terms-level-map) ファイルは、マップと呼ばれるフォルダに所属しています ![#](https://img.shields.io/badge/lint-supported-green.svg)

Map ファイルは信じられないほど特殊で、特にサブレベルやストリーミングレベルで作業する場合は、すべてのプロジェクトで独自のマップ命名システムを使用するのが一般的です。特定のプロジェクトでどのようなマップ体系が整っていても、すべてのレベルは `/Content/Project/Maps` に属している必要があります。

場所を説明することなく特定の地図を開くように誰かに指示できることは、時間の節約と一般的な「クオリティ・オブ・ライフ」改善です。 `Maps/Campaign1/`や `Maps/Arenas`のように、レベルが`Maps`のサブフォルダ内にあるのが一般的ですが、ここで最も重要なのは  `/Content/Project/Maps`。

これにより、エンジニア向けの調理作業も簡単になります。ビルドプロセスのレベルを狂わせることは、それらのために任意のフォルダを掘り下げなければならない場合、非常に不快になります。チームの地図がすべて1か所にある場合、誤ってビルド内の地図を調理するのはずっと難しくなります。また、QAプロセスだけでなくビルドスクリプトも簡単に作成できます。

<a name="2.5"></a>
<a name="structure-core"></a>
### 2.5 Use A `Core` Folder For Critical Blueprints And Other Assets ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

Use `/Content/Project/Core` folder for assets that are absolutely fundamental to a project's workings. For example, base `GameMode`, `Character`, `PlayerController`, `GameState`, `PlayerState`, and related Blueprints should live here.

This creates a very clear "don't touch these" message for other team members. Non-engineers should have very little reason to enter the `Core` folder. Following good code structure style, designers should be making their gameplay tweaks in child classes that expose functionality. World builders should be using prefab Blueprints in designated folders instead of potentially abusing base classes.

For example if your project requires pickups that can be placed in a level, there should exist a base Pickup class in `Core/Pickups` that defines base behavior for a pickup. Specific pickups such as a Health or Ammo should exist in a folder such as `/Content/Project/Placeables/Pickups/`. Game designers can define and tweak pickups in this folder however they please, but they should not touch `Core/Pickups` as they may unintentionally break pickups project-wide.

<a name="2.6"></a>
<a name="structure-assettypes"></a>
### 2.6 Do Not Create Folders Called `Assets` or `AssetTypes` ![#](https://img.shields.io/badge/lint-supported-green.svg)

<a name="2.6.1"></a>
#### 2.6.1 Creating a folder named `Assets` is redundant. ![#](https://img.shields.io/badge/lint-supported-green.svg)

All assets are assets.

<a name="2.6.2"></a>
#### 2.6.2 Creating a folder named `Meshes`, `Textures`, or `Materials` is redundant. ![#](https://img.shields.io/badge/lint-supported-green.svg)

All asset names are named with their asset type in mind. These folders offer only redundant information and the use of these folders can easily be replaced with the robust and easy to use filtering system the Content Browser provides.

Want to view only static mesh in `Environment/Rocks/`? Simply turn on the Static Mesh filter. If all assets are named correctly, they will also be sorted in alphabetical order regardless of prefixes. Want to view both static meshes and skeletal meshes? Simply turn on both filters. this eliminates the need to potentially have to `Control-Click` select two folders in the Content Browser's tree view.

> This also extends the full path name of an asset for very little benefit. The `S_` prefix for a static mesh is only two characters, whereas `Meshes/` is seven characters.

Not doing this also prevents the inevitability of someone putting a static mesh or a texture in a `Materials` folder.

<a name="2.7"></a>
<a name="structure-large-sets"></a>
### 2.7 Very Large Asset Sets Get Their Own Folder Layout ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

This can be seen as a pseudo-exception to [2.6](#2.6).

There are certain asset types that have a huge volume of related files where each asset has a unique purpose. The two most common are Animation and Audio assets. If you find yourself having 15+ of these assets that belong together, they should be together.

For example, animations that are shared across multiple characters should lay in `Characters/Common/Animations` and may have sub-folders such as `Locomotion` or `Cinematic`.

> This does not apply to assets like textures and materials. It is common for a `Rocks` folder to have a large amount of textures if there are a large amount of rocks, however these textures are generally only related to a few specific rocks and should be named appropriately. Even if these textures are part of a [Material Library](#2.8).

<a name="2.8"></a>
<a name="structure-material-library"></a>
### 2.8 `MaterialLibrary` ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

If your project makes use of master materials, layered materials, or any form of reusable materials or textures that do not belong to any subset of assets, these assets should be located in `Content/Project/MaterialLibrary`.

This way all 'global' materials have a place to live and are easily located.

> This also makes it incredibly easy to enforce a 'use material instances only' policy within a project. If all artists and assets should be using material instances, then the only regular material assets that should exist are within this folder. You can easily verify this by searching for base materials in any folder that isn't the `MaterialLibrary`.

The `MaterialLibrary` doesn't have to consist of purely materials. Shared utility textures, material functions, and other things of this nature should be stored here as well within folders that designate their intended purpose. For example, generic noise textures should be located in `MaterialLibrary/Utility`.

Any testing or debug materials should be within `MaterialLibrary/Debug`. This allows debug materials to be easily stripped from a project before shipping and makes it incredibly apparent if production assets are using them if reference errors are shown.

<a name="3"></a>
<a name="bp"></a>
## 3. Blueprints ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

This section will focus on Blueprint classes and their internals. When possible, style rules conform to [Epic's Coding Standard](https://docs.unrealengine.com/latest/INT/Programming/Development/CodingStandard).

### Sections

> 3.1 [Compiling](#bp-compiling)

> 3.2 [Variables](#bp-vars)

<a name="3.1"></a>
<a name="bp-compiling"></a>
### 3.1 Compiling ![#](https://img.shields.io/badge/lint-supported-green.svg)

All blueprints should compile with zero warnings and zero errors. You should fix blueprint warnings and errors immediately as they can quickly cascade into very scary unexpected behavior.

Do *not* submit broken blueprints to source control. If you must store them on source control, shelve them instead.

Broken blueprints can cause problems that manifest in other ways, such as broken references, unexpected behavior, cooking failures, and frequent unneeded recompilation. A broken blueprint has the power to break your entire game.

<a name="3.2"></a>
<a name="bp-vars"></a>
### 3.2 Variables ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

#### Sections

> 3.2.1 [Naming](#bp-vars)

> 3.2.2 [Editable](#bp-vars-editable)

> 3.2.3 [Categories](#bp-vars-categories)

> 3.2.4 [Access](#bp-vars-access)

> 3.2.5 [Advanced](#bp-vars-advanced)

> 3.2.6 [Transient](#bp-vars-transient)

> 3.2.7 [SaveGame](#bp-vars-savegame)

> 3.2.8 [Config](#bp-vars-config)

<a name="3.2.1"></a>
<a name="bp-var-naming"></a>
#### 3.2.1 Naming ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

<a name="3.2.1.1"></a>
<a name="bp-var-naming-nouns"></a>
##### 3.2.1.1 Nouns ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

All non-boolean variable names must be clear, unambiguous, and descriptive nouns.

<a name="3.2.1.2"></a>
<a name="bp-var-naming-case"></a>
##### 3.2.1.2 PascalCase ![#](https://img.shields.io/badge/lint-supported-green.svg)

All non-boolean variables should be in the form of [PascalCase](#terms-cases).

<a name="3.2.1.2e"></a>
###### 3.2.1.2e Examples:

* `Score`
* `Kills`
* `TargetPlayer`
* `Range`
* `CrosshairColor`
* `AbilityID`

<a name="3.2.1.3"></a>
<a name="bp-var-bool-prefix"></a>
##### 3.2.1.3 Boolean `b` Prefix ![#](https://img.shields.io/badge/lint-supported-green.svg)

All booleans should be named in PascalCase but prefixed with a lowercase `b`.

Example: Use `bDead` and `bEvil`, **not** `Dead` and `Evil`.

UE4 Blueprint editors know not to include the `b` in user-friendly displays of the variable.

<a name="3.2.1.4"></a>
<a name="bp-var-bool-names"></a>
##### 3.2.1.4 Boolean Names ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

<a name="3.2.1.4.1"></a>
###### 3.2.1.4.1 General And Independent State Information ![#](https://img.shields.io/badge/lint-supported-green.svg)

All booleans should be named as descriptive adjectives when possible if representing general information. Do not include words that phrase the variable as a question, such as `Is`. This is reserved for functions.

Example: Use `bDead` and `bHostile` **not** `bIsDead` and `bIsHostile`.

Try to not use verbs such as `bRunning`. Verbs tend to lead to complex states.

<a name="3.2.1.4.2"></a>
###### 3.2.1.4.2 Complex States ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

Do not to use booleans to represent complex and/or dependent states. This makes state adding and removing complex and no longer easily readable. Use an enumeration instead.

Example: When defining a weapon, do **not** use `bReloading` and `bEquipping` if a weapon can't be both reloading and equipping. Define an enumeration named `EWeaponState` and use a variable with this type named `WeaponState` instead. This makes it far easier to add new states to weapons.

Example: Do **not** use `bRunning` if you also need `bWalking` or `bSprinting`. This should be defined as an enumeration with clearly defined state names.

<a name="3.2.1.5"></a>
<a name="bp-vars-naming-context"></a>
##### 3.2.1.5 Considered Context ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

All variable names must not be redundant with their context as all variable references in Blueprint will always have context.

<a name="3.2.1.5e"></a>
###### 3.2.1.5e Examples:

Consider a Blueprint called `BP_PlayerCharacter`.

**Bad**

* `PlayerScore`
* `PlayerKills`
* `MyTargetPlayer`
* `MyCharacterName`
* `CharacterSkills`
* `ChosenCharacterSkin`

All of these variables are named redundantly. It is implied that the variable is representative of the `BP_PlayerCharacter` it belongs to because it is `BP_PlayerCharacter` that is defining these variables.

**Good**

* `Score`
* `Kills`
* `TargetPlayer`
* `Name`
* `Skills`
* `Skin`

<a name="3.2.1.6"></a>
<a name="bp-vars-naming-atomic"></a>
##### 3.2.1.6 Do _Not_ Include Atomic Type Names ![#](https://img.shields.io/badge/lint-supported-green.svg)

Atomic or primitive variables are variables that represent data in their simplest form, such as booleans, integers, floats, and enumerations.

Strings and vectors are considered atomic in terms of style when working with Blueprints, however they are technically not atomic.

> While vectors consist of three floats, vectors are often able to be manipulated as a whole, same with rotators.

> Do _not_ consider Text variables as atomic, they are secretly hiding localization functionality. The atomic type of a string of characters is `String`, not `Text`.

Atomic variables should not have their type name in their name.

Example: Use `Score`, `Kills`, and `Description` **not** `ScoreFloat`, `FloatKills`, `DescriptionString`.

The only exception to this rule is when a variable represents 'a number of' something to be counted _and_ when using a name without a variable type is not easy to read.

Example: A fence generator needs to generate X number of posts. Store X in `NumPosts` or `PostsCount` instead of `Posts` as `Posts` may potentially read as an Array of a variable type named `Post`.

<a name="3.2.1.7"></a>
<a name="bp-vars-naming-complex"></a>
##### 3.2.1.7 Do Include Non-Atomic Type Names ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

Non-atomic or complex variables are variables that represent data as a collection of atomic variables. Structs, Classes, Interfaces, and primitives with hidden behavior such as `Text` and `Name` all qualify under this rule.

> While an Array of an atomic variable type is a list of variables, Arrays do not change the 'atomicness' of a variable type.

These variables should include their type name while still considering their context.

If a class owns an instance of a complex variable, i.e. if a `BP_PlayerCharacter` owns a `BP_Hat`, it should be stored as the variable type as without any name modifications.

Example: Use `Hat`, `Flag`, and `Ability` **not** `MyHat`, `MyFlag`, and `PlayerAbility`.

If a class does not own the value a complex variable represents, you should use a noun along with the variable type.

Example: If a `BP_Turret` has the ability to target a `BP_PlayerCharacter`, it should store its target as `TargetPlayer` as when in the context of `BP_Turret` it should be clear that it is a reference to another complex variable type that it does not own.


<a name="3.2.1.8"></a>
<a name="bp-vars-naming-arrays"></a>
##### 3.2.1.8 Arrays ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

Arrays follow the same naming rules as above, but should be named as a plural noun.

Example: Use `Targets`, `Hats`, and `EnemyPlayers`, **not** `TargetList`, `HatArray`, `EnemyPlayerArray`.


<a name="3.2.2"></a>
<a name="bp-vars-editable"></a>
#### 3.2.2 Editable Variables ![#](https://img.shields.io/badge/lint-partial_support-yellow.svg)

All variables that are safe to change the value of in order to configure behavior of a blueprint should be marked as `Editable`.

Conversely, all variables that are not safe to change or should not be exposed to designers should _not_ be marked as editable, unless for engineering reasons the variable must be marked as `Expose On Spawn`.

Do not arbitrarily mark variables as `Editable`.

<a name="3.2.2.1"></a>
<a name="bp-vars-editable-tooltips"></a>
##### 3.2.2.1 Tooltips ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

All `Editable` variables, including those marked editable just so they can be marked as `Expose On Spawn`, should have a description in their `Tooltip` fields that explains how changing this value affects the behavior of the blueprint.

<a name="3.2.2.2"></a>
<a name="bp-vars-editable-ranges"></a>
##### 3.2.2.2 Slider And Value Ranges ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

All `Editable` variables should make use of slider and value ranges if there is ever a value that a variable should _not_ be set to.

Example: A blueprint that generates fence posts might have an editable variable named `PostsCount` and a value of -1 would not make any sense. Use the range fields to mark 0 as a minimum.

If an editable variable is used in a Construction Script, it should have a reasonable Slider Range defined so that someone can not accidentally assign it a large value that could crash the editor.

A Value Range only needs to be defined if the bounds of a value are known. While a Slider Range prevents accidental large number inputs, an undefined Value Range allows a user to specify a value outside the Slider Range that may be considered 'dangerous' but still valid.

<a name="3.2.3"></a>
<a name="bp-vars-categories"></a>
#### 3.2.3 Categories ![#](https://img.shields.io/badge/lint-supported-green.svg)

If a class has only a small number of variables, categories are not required.

If a class has a moderate amount of variables (5-10), all `Editable` variables should have a non-default category assigned. A common category is `Config`.

If a class has a large amount of variables, all `Editable` variables should be categorized into sub-categories using the category `Config` as the base category. Non-editable variables should be categorized into descriptive categories describing their usage. 

> You can define sub-categories by using the pipe character `|`, i.e. `Config | Animations`.

Example: A weapon class set of variables might be organized as:

	|-- Config
	|	|-- Animations
	|	|-- Effects
	|	|-- Audio
	|	|-- Recoil
	|	|-- Timings
	|-- Animations
	|-- State
	|-- Visuals

<a name="3.2.4"></a>
<a name="bp-vars-access"></a>
#### 3.2.4 Variable Access Level ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

In C++, variables have a concept of access level. Public means any code outside the class can access the variable. Protected means only the class and any child classes can access this variable internally. Private means only this class and no child classes can access this variable.

Blueprints do not have a defined concept of protected access currently.

Treat `Editable` variables as public variables. Treat non-editable variables as protected variables.

<a name="3.2.4.1"></a>
<a name="bp-vars-access-private"></a>
##### 3.2.4.1 Private Variables ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

Unless it is known that a variable should only be accessed within the class it is defined and never a child class, do not mark variables as private. Until variables are able to be marked `protected`, reserve private for when you absolutely know you want to restrict child class usage.

<a name="3.2.5"></a>
<a name="bp-vars-advanced"></a>
#### 3.2.5 Advanced Display ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

If a variable should be editable but often untouched, mark it as `Advanced Display`. This makes the variable hidden unless the advanced display arrow is clicked.

To find the `Advanced Display` option, it is listed as an advanced displayed variable in the variable details list.

<a name="3.2.6"></a>
<a name="bp-vars-transient"></a>
#### 3.2.6 Transient Variables ![#](https://img.shields.io/badge/lint-unsupported-red.svg)

All variables that are not editable and have a initial value of zero or null should be marked as `Transient`.

Transient variables are variables that do not need to have their value saved and loaded and have an initial value of zero or null. This is useful for references to other objects and actors who's value isn't known until run-time.

This forces the variable to always initialize as zero or null, prevents the editor from ever saving a reference to it, and speeds up saving and loading of the blueprint class.

<a name="3.2.7"></a>
<a name="bp-vars-savegame"></a>
#### 3.2.7 SaveGame Variables ![#](https://img.shields.io/badge/lint-supported-green.svg)

Only use the SaveGame property of variables when inside a class derived from `SaveGame`. Use this property only if the `SaveGame` class should save this value.

Do **not** mix `SaveGame` and `Transient`, this does not make any sense.

<a name="3.2.8"></a>
<a name="bp-vars-config"></a>
#### 3.2.8 Config Variables ![#](https://img.shields.io/badge/lint-supported-green.svg)

Do not use the `Config Variable` flag. This makes it harder for designers to control blueprint behavior. Config variables should only be used in C++ for rarely changed variables. Think of them as `Advanced Advanced Display` variables.

## Contributors

* [Michael Allar](http://allarsblog.com): [GitHub](https://github.com/Allar), [Twitter](https://twitter.com/michaelallar)
* [CosmoMyzrailGorynych](https://github.com/CosmoMyzrailGorynych)
* [billymcguffin](https://github.com/billymcguffin)

## License

Copyright (c) 2016 Gamemakin LLC

See [LICENSE](/LICENSE)

**[⬆ Back to Top](#table-of-contents)**


## Amendments

We encourage you to fork this guide and change the rules to fit your team's style guide. Below, you may list some amendments to the style guide. This allows you to periodically update your style guide without having to deal with merge conflicts.

# };