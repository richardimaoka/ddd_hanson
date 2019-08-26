## 技術ブログに乗せるため途中何度か写真をとります！顔は映らないようにします。

## 本勉強会の目的

現実世界のビジネス課題を解決するソフトウェアを作る際は、そのビジネスの裏にある複雑なルールや業務フローを理解することが重要です。

DDD（Domain Driven Design）はそういった複雑なビジネスの理解をソフトウェアに反映するための手法のあつまりです。決まりきった型があるわけではなく各ソフトウェア開発チームが自分達で手法を取捨選択してソフトウェアの開発を行っていく必要があります。

本勉強会は練習を通して「ビジネスの裏にあるルールや業務フローを理解する」ということを学ぶことを目的とします。映画チケットシステムを題材にルールや業務フローをみんなで議論しながら分析してソフトウェアのモデル（ソースコードではない、それより抽象度の高い図みたいなもの）に反映します。

## 題材

ある映画館ウェブサイト https://cinemacity.co.jp/ の券売システムと、映画館においてある券売機システムを統合することになりました。我々はその統合システムの分析・開発をするプロジェクトを任されました。チケットの購入から発券にまつわるルールと業務フローを分析・モデリングしましょう。

参考 [#チケット料金モデリング](https://togetter.com/li/1378684)

## 勉強会の流れ  

1. 導入と題材の紹介
2. まずは題材のシステムを触ってみる 15min?  https://cinemacity.co.jp/ 
3. ユーザーストーリー分析: お客さんが見たい映画を選んでから映画が始まるまで (適宜ウェブサイトを触りながら) 1h
4. ドメインモデリング: ユーザーストーリーにもとづいて登場人物・役割（アクター）の抽出を行った後、ルールや業務フローをソフトウェアのモデルに起こしていく

## 議論におけるグランドルール  
当勉強会中の議論において以下のルールに従ってください  

|Good|Bad|
|:--|:--|
|発言の責任は追求しない|発言に責任を求める|
|積極的に発言する|全く発言しない|
|要点を絞って発言する|長々と発言しない|
|相手の話を聞く|相手の話を遮る|
|相互理解を深める|立場の違いを認めない|
|事実で判断する|思い込みで判断する|
|対案を出す|批判する|

## ユーザーストーリー  
ドメインを把握するための手法のひとつです  
「誰が(Who)/何を(What)/なぜ(Why)」を明確化し、業務の流れをストーリーとして記述する  
ことでサービスが何を実現しなければいないのか(要件)をはっきりさせます  
また、ドメインエキスパート(業務における有識者)が気づいていない(あるいは忘れている)要件を掘り出すこともできます  

初めてストーリーを構成する時点ではMVP(Minimum Viable Product)、つまりソリューションとしての最小構成のみを考え  
そこから肉付けしていくことを推奨します  

## ユーザーストーリー フォーマット  
ユーザーストーリーのフォーマットは今回は以下のものをベースに進めていきます  
(改案等あれば当日あるいは前日までに頂ければ取り入れます)  

https://docs.google.com/spreadsheets/d/1_wvL5o9DdNRZMpwabyCyfcYWswZxHlqjFDplygTKqwA/edit?usp=sharing  
ホワイトボードに項目を分割し、項目ごとに付箋を並べていく想定です  
横軸は時系列です  
項目は以下の3つに分割されます 
項目ごとに同じ色の付箋を使います  
- アクター(Who)  
誰が行動を起こしているのかをはっきりさせるための項目です  
空欄の場合は直前のアクターと同じを意味する  
実際の人だけでなくシステムや外部サービスなどもひとつのアクターとして扱います  
- ナラティブフロー(What)  
実際のストーリーを並べていく項目です  
この時点では実際に実装する機能のことは考えずストーリーとして何が必要かを考えます  
必要に応じて付箋に「なぜ(Why)」を記載します  
- 機能  
サービスが実際に実装すべき機能です  
サービスが実現すべき範囲が定まっていない場合は範囲外になりそうな機能でも  
書き出すことを推奨します  
書き出した機能の中で不要なものはあとから取り除くかマークをしましょう(例では紫色なものが不要となったものです)  
