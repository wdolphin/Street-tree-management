# Street-tree-management
## 本文
## 住民による街路樹管理支援のためのGISツールとLocalWikiの活用

## 目次
1. はじめに
2. 研究方法
3. 考察
4. 結論
5. 参考文献

## 1. はじめに
都市における街路樹は、街の景観向上（シンボルツリー、新芽・花・紅葉などで四季を感じるなど）、生活環境の保全（騒音低下、夏の緑陰確保、ヒートアイランド現象の抑制、大気の浄化）、交通安全（歩道と車道の分離、眩しさを遮る）、防災（火事の延焼を防ぐ）などの役割がある。しかし自然界ではなく、道路沿いという環境に植えられた現代の街路樹は、道路標識の視認性確保のためや安全通行のため強剪定されたり、強風・地震・積雪などで倒れ歩行者が人命を奪われたり、交通障害を起こしたりする。また、災害時は避難や救助活動の障害になることもある。日本では住宅開発が進んだ1960年～1980年代に大量に植えられた街路樹が老齢化し、倒木被害などの問題も顕在化しつつある。植えられた街路樹は管理を怠らず日常的な点検・剪定・改善措置などを行い、異常や危険などの問題を回避する必要がある。そのためには、行政だけでなく、住民も日頃から身近な街路樹に対し関心を持ち行政と住民の協働が望まれる。
現在の街路樹管理の問題点として以下の点があげられる。
1. 紙の帳簿で樹木の管理情報を記録し、街路樹をGISを利用したデジタル地図にマッピングしていない自治体が多い。また、街路樹についてオープンデータを提供している自治体は少なく、提供している自治体も樹種とその本数などに限られているものがほとんどである。
2. 樹木医による診断や樹木健全度調査は多大なコストと労力が必要であり、同じ街路樹の診断調査を毎年実施するのはむずかしい。　
3. 異状木に対し住民から街路樹専門に情報提供（苦情等）を受ける方法が確立されていない。スマートフォン用アプリを使用している自治体もある。（例　相模原市の「パッ！撮るん」）しかし、これらアプリは道路全般の障害通報が主目的で街路樹専門ではない。
4. 街路樹管理を担当する職員数の不足。  

上記問題点を解決するため、本研究では誰でも簡単に利用・編集できるOpenStreetMapに街路樹をマッピングし、街路樹の位置情報、属性を共有し、Mapillaryで街路樹の時系列変化を記録、LocalWikiで樹木（特に問題のある樹木）の生育状態の経時的変化を過去の写真も利用しながら観察記録をとり、街路樹管理支援のため住民が使いやすく継続して利用できる方法の構築を試みる。

## 2. 方法
### 2-1 OpenStreetMapにマッピング   
#### [OpenStreetMap](https://ja.wikipedia.org/wiki/%E3%82%AA%E3%83%BC%E3%83%97%E3%83%B3%E3%82%B9%E3%83%88%E3%83%AA%E3%83%BC%E3%83%88%E3%83%9E%E3%83%83%E3%83%97) とは

OpenStreetMapは自由に利用でき、地物の地理情報を自由に編集できる機能を持った世界地図を作る世界的な共同プロジェクトである。提供されたデータはOpen Database(ODbl)1.0のもと再利用可能である。

#### [Go Map!!](https://wiki.openstreetmap.org/wiki/JA:Go_Map!!)とは

OpenStreetMap内の情報を編集したり新規作成できるiphone用のiOSアプリ。Nodeを素早く登録できるため、フィールドでの個々の街路樹の位置情報登録に使用。

#### 対象街路樹とOpenStreetMapへの入力方法

横浜市都筑土木事務所が2018年度に樹木医により街路樹診断をした樹木を中心に1100本余りの樹木をOpenStreetMapにGo Mapを使用してマッピングした。樹種はケヤキ、クス、ソメイヨシノ、ユリノキ、ヤマザクラ、イチョウ、ハクウンボク、ハナミズキ、アラカシ、サクラ（八重桜）、シラカシ、カツラ、エンジュ、アメリカフウ、こぶし、サルスベリ、シダレザクラ、ナンキンハゼ、メタセコイア、ナツツバキ、モチノキ、ハクモクレン、フジ、不明など25種。サクラは種がはっきりわかるものはヤマザクラ、ヨウコウザクラ、シダレザクラなど分けた。  

![list-1.png](https://user-images.githubusercontent.com/15658355/71581253-b22a2400-2b47-11ea-801a-408b1b45ebe7.png)
 図1　OpenStreetMap入力　樹木リスト 


Tagの入力にはOpenStreetMapのtreeのTagづけを参考にdenotation, genus, genus:ja, leaf_cycle, leaf_type, natural, source, species, species:ja, tree:ref の10keyとvalueを入力した。tree:refには2018年度の樹木診断で表示された樹木番号を入力した。樹木診断されなかった樹木で番号がないものも、現地調査で樹木に番号タグが付いていたものはそれを入力した。  

<img src="https://user-images.githubusercontent.com/15658355/71581533-f964e480-2b48-11ea-89ea-ccc69618375f.jpg" height="250px">  <img src="https://user-images.githubusercontent.com/15658355/71581540-fd910200-2b48-11ea-859f-76f91ead1779.jpg" height="250px">   
画像1  Go Mapのスマホ画面2例

### 2-2 Mapillaryで街路樹を撮影
#### [Mapillary](https://www.mapillary.com/)とは

スマホなどで撮影した写真に位置情報を付加し写真共有をするサービスのアプリ。クラウドソーシング方式で世界のあらゆる場所を投稿できるが、最近はほとんどストリートビュー作成に重きを置いている。ライセンスはCC-BY-SA.  

#### 撮影方法
2－1でOpenStreetMapにマッピングした路線を歩行し街路樹をMapillary アプリを使用し撮影しアップロード。時間列変化を見るために半年くらいの間隔で同じ場所を撮影する. 

画像2　MapillaryのPC画面3例  

![](https://user-images.githubusercontent.com/15658355/71606892-213f6100-2bb8-11ea-99c8-b6c114c43598.jpg)|![](https://user-images.githubusercontent.com/15658355/71606894-23a1bb00-2bb8-11ea-8083-6fca8e2f4d88.jpg)|![](https://user-images.githubusercontent.com/15658355/71606895-27cdd880-2bb8-11ea-92e5-536262f1cd7b.jpg)
:--------:|:--------:|:--------:
区役所通りケヤキ街路樹|池辺歩専(南)2019年4月ヤマザクラ|池辺歩専(南)2019年11月ヤマザクラ

### 2-3　Local Wikiで街路樹観察を記録 
#### [LocalWiki](https://localwiki.org/) とは

草の根で住民が自分の街の情報収集、発信し共有するためのサーバとその活動を指す。コンテンツはオープンデータで誰でも二次利用できる。
カリフォルニアのデービスで2004年Dais Wikiが発祥し、2010年にLocalWikiプロジェクトが始まる。そして2015年からはグローバルにローカル知識を共有するプラットフォームになる。地図にOpenStreetMapを利用できる。今回の研究目的と合致し、PCだけでなくスマホからも入力できる携帯性、データ格納量から街路樹観察記録にLocalWikiを使用する。

#### LocalWikiの対象街路樹・対象場所・記録方法
2-1と2-2では1100本余りの樹木を入力し,　ストリートビュー的に街路樹の写真撮影をしたが、LocalWikiには日本人が愛着を感じる樹木で,　毎年住民が花見を楽しみにし、良好な生育状態を維持するために個々の樹木の観察管理が重要なサクラを対象街路樹にし、対象場所は池辺歩専道（北側）と池辺歩専道（南側）の80本あまりを対象としLocalWikiの横浜市都筑区内に都筑の樹木のページを作成した。　
（[LocalWikiの都筑の樹木サイト](https://ja.localwiki.org/yokohama/tags/%E9%83%BD%E7%AD%91%E3%81%AE%E6%A8%B9%E6%9C%A8))　　

LocalWikiの都筑の樹木の各ページを見た人が問題樹木に速やかに気が付くように、観察する全てのサクラの木の状況を毎回アップロードしていく方法ではなく、観察したサクラの中から問題がある樹木の写真とコメントをアップロードする方法をとった。また過去に撮影したサクラの開花の写真などもアップロードし経年変化を示した。サクラの写真のキャプション内に樹木番号表示をし、OpenStreetMap上の樹木位置のサイトとリンクをはり、当該樹木の位置が確認できるようにした。



画像3　LocalWikiのスマホ画面  3例  

<img src="https://user-images.githubusercontent.com/15658355/71637028-46e26e00-2c7d-11ea-96e6-17ce6bfa0def.jpg" height="250px">  <img src="https://user-images.githubusercontent.com/15658355/71637029-4b0e8b80-2c7d-11ea-9b9c-2aca469656ee.jpg" height="250px">  <img src="https://user-images.githubusercontent.com/15658355/71637031-519d0300-2c7d-11ea-8156-97a7f1fc2ad4.jpg" height="250px">  


画像4　LocalWikiのPC画面例  

<img src="https://user-images.githubusercontent.com/15658355/71637193-9d9d7700-2c80-11ea-89e0-5bb0560fcca5.png" width="400px">  

### 3 成果
本研究は横浜市都筑区内の街路樹1100本あまりをOpenStreetMapにマッピングし、街路樹の時系列変化を見るためにMapillaryを使用し、樹木の健全性を住民が観察し発信するためにサクラを例にLocalWikiを使用するという統合的に運用する方法を提案した。OpenStreetMap上に樹木番号付きの樹木マッピングをすることにより行政と住民が樹木の位置情報など基本情報を共有できた。　行政は現地に足を運ばなくてもLocalWikiを通じ問題樹木の状況を知ることができた。行政と住民が問題のある樹木の改善措置などを話し合う時にLocalWikiを通じ樹木状況の情報が共有されているのでコミュニケーションがスムーズになる。この統合方法は地域の街路樹維持管理ばかりでなく、将来的な街路樹計画の策定や、住民参加のまちづくりにも役立つと思われる。　　

街路樹や道路全般の障害を自治体に知らせるスマホアプリとLocalWikiを利用した観察記録を比較すると、観察記録は一過性でないため日頃の手入れなど樹木管理の改善措置をとる際に有効に活用できると思われる。、


### 4 課題
*本研究で使用したMapillaryは街路樹の外観風景をストリートビュー的に時系列で記録するには良いアプリであるが、樹木観察用のアプリではない。街路樹管理という観点から目的にふさわしい記録がとれるアプリかどうか時間をかけて検証すると同時に、より良いアプリがあるか探し続ける必要がある。  

*LocalWikiのスマホ入力ではリンクを貼る機能を使えなかった。またさらに使い易くするために樹木観察用のスマホ入力Templateを作成することが望ましい。  

*この統合的方法を地域の樹木に関心のある住民や緑化推進ボランティアグループなどに推進するためにはマッピングパーティのイベントを開催したり、講習会を開く必要があるが今回はそこまでできなかった。  

*本研究では観察樹種でサクラを扱ったが、他のどの樹種だったら住民が関心を持ちLocalWikiで観察記録を発信できるか調査することが望ましい。

*観察記録という観点では突発的な事故時と四季の変化が認められる３か月おきくらいに樹木が観察され発信されることが望ましい。

### 5 結論
本研究では行政と住民の協働が望まれる街路樹管理において、住民が使いやすく継続して利用できる方法として既存の無料ツールを統合的運用する方法を提案した。オープンソースかにより行政と住民が情報共有でき、その有効性が確認できた。　しかし、樹木管理に最適なアプリかどうかや、アプリの使いやすさ改善などの課題がまだある。実用性と信頼性を高めるために、今後さらに検証する必要がある。


### 参考文献：

1.[国土交通省　国土技術政策総合研究所　研究資料　第１編　街路樹の点検・診断](http://www.nilim.go.jp/lab/bcg/siryou/tnn/tnn1059pdf/Ks1059018.pdf)　　

2.[国土交通省　国土技術政策総合研究所　研究資料　第２編　街路樹の点検・診断事例集](http://www.nilim.go.jp/lab/bcg/siryou/tnn/tnn1059pdf/Ks1059013.pdf)　　

3.[環境省　街路樹ケース検討のための事前調査-ヒートアイランド現象に対する適応検討調査業務](https://www.env.go.jp/air/report/h23-01/04-ref2-3.pdf)  

4.[タブレット端末を利用した植物学習と樹木管理のためのサクラ属のデータベース(CerasusDB)の開発　中村彰宏、守村敦郎](https://www.jstage.jst.go.jp/article/jjsrt/43/1/43_174/_article/-char/ja/)  

5.[相模原市道路通報アプリ「パッ！撮るん」](http://www.city.sagamihara.kanagawa.jp/patrun/)  

6.[樹木医](http://www.jpgreen.or.jp/treedoctor/info.html)  

7.[JA:Tag:natural=tree](https://wiki.openstreetmap.org/wiki/JA:Tag:natural%3Dtree) 

8.[野田市街路樹管理マニュアル　素案](https://www.city.noda.chiba.jp/_res/projects/default_project/_page_/001/010/216/gairozyuizi.pdf)

9.[Wikipedia 街路樹](https://ja.wikipedia.org/wiki/%E8%A1%97%E8%B7%AF%E6%A8%B9)

