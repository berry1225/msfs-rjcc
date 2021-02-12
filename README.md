# msfs-rjcc

デフォルトの新千歳(RJCC)に滑走路が4本存在するため、新千歳(RJCC)と千歳(RJCJ)に分割しました。
新千歳(RJCC)側をメインで使うことを想定しているので、千歳(RJCJ)側には管制が存在しません。
千歳(RJCJ)側メインで使いたい人は、各自修正してください。

Airport2Projectを使用してデフォルトのデータをコピーしてから編集しています。

基本的には「素材の味」を使用しているので、凝った修正はしていません。
**そもそも空港を2つに分割することが目的なので、特に詳細なアップデートをする予定はありません。**
もし何かしらのアップデートをしたい場合は、ここのファイル群をダウンロードしてお使いください。

__右上の緑の「Code」ボタンから「Download ZIP」することでまとめてダウンロードできます。__

フェアユース(公正利用、分からなかったら単語で調べてね)の範囲であれば、ダウンロードして自由にお使いいただいて構いません。

README.md以外のファイルをひとつのフォルダに入れた上で、SDKでRJCC.xmlを読み込むことで編集とビルドが可能になります。
ビルド後はフォルダ内に「Packages」というフォルダができるので、その中のフォルダ(rjcc-rjcj)をCommunityフォルダに突っ込んでください。
編集してビルドする際は、Creatorを自分の名前に書き換えておいてください。(元ファイルではberryになっていると思います)

**加工後のデータを各自でFlightsim.toで配布してもらっても結構です、その場合は特に連絡不要です。**
もしくは、修正内容をここにプルリクとして送ってもらえれば、こちらで確認・反映して修正版をアップロードすることも可能です。
ただ、十年単位でのメンテナンスは個人として保証しませんのでご了承ください。

よそで公開する場合は、GitHub上のアカウント宛でいいので一報もらえると助かります。(個人的にもぜひ使わせてもらいたいので)

**商用として有償頒布したり、寄付を募ったり、YouTube等の登録者数稼ぎに使うのはダメです。(たぶん色んな条項に違反しますし、見つけ次第容赦なく通報します)**

「編集したいけど何から手をつければいいか分からない！どこで聞けばいいかも分からない！」という場合は、
GitHubアカウント作ってGitHub上で連絡してもらえれば、可能な範囲で相談に乗ります。
(メールやTwitterやpixivからメッセージ送られても答えられないかもしれません)

# 使用ツール
* Airport2Project v1.0.0.3
* MSFS SDK v0.9.0

# 修正点
Airport2Projectで出力したデータからの変更点。
* ILS無効化して手動で設定 (Airport2Projectの仕様的に必要っぽい)
* * 設定がイケてなかったのでv1.1で再修正
* エプロン照明追加
* G誘導路の有効化
* 国際線ターミナル増設
* スポット追加 (69～71)
* スポット番号誤り修正 (42→64)
* スポット削除 (28など)
* 線の小規模な修正
* 誘導路の光り方の修正
* 進入灯の修正 (Airport2Projectで出力するとCALVERT2とかになって眩しい)
* 空港の平坦化
* 滑走路の長さがきっちり揃ってなかったので綺麗な数値に修正

# 分割
* 基本的には元データを両側にコピーして、それぞれの側で個別に編集
* エプロン等は4000m滑走路を境にして分割
* 政府専用機ハンガーのあるエプロンのスポットは両側のデータで保持 (特に問題なさそう)
* RJCJ側は36RにILSあったので一応設定
* RJCJ側の周波数は特に何も作成せず (被ったら面倒なので)

# 修正漏れ
* C-6, W-6誘導路が使用停止状態(×マーク)じゃない (特に何も触ってないのでデフォルト状態のまま)
* * ちなみに誘導路自体は設定がない状態(＝そのへんの地面と同じ扱い)
* ~~RJCJのPAPIが2.7度じゃないかもしれない (特に何も触ってないのでデフォルト状態のまま、GSは2.7度)~~
* * 2.7度になってなかったのでv1.1のタイミングで修正

# 既知の問題点
* Jetway(ボーディングブリッジ、飛行機に乗る直前に通るアレ)が、駐機中の他の機体に対して変な方向(右側とか)に付いている場合がある
* * ソフト側のバグだと思っているので、とりあえずJetwayの方向をまっすぐにすることで防止 (有効かどうかは不明)
* * * というか他の空港でも普通に起こってるっぽいので放置
* 滑走路がオレンジ色じゃない
* * SDK側でいい感じに設定変更できるるようにしてほしい
* * ちなみにRJCJ側の滑走路2本はオレンジではなく白が正しい
* RJCJ側の管制塔がどうやっても消せない
* * 両方のデータでPolygon(建物除外)とExclusionRectangle(全除外)をかけても倒せない、もぅﾏﾁﾞ無理
* RJCJ側の管制が存在しない
* * そもそもfrequenciesをどうやって設定していいか分からない
* * 現実は基地側が管制しているので、下手に設定したら競合しそう
* RJCJ側のアプローチ情報が何もない
* * そもそもどうやって設定していいか分からない
* Little NavmapでILS設定が二重に表示される
* * 向こう側の仕様だと思うけれど、向こうのデフォルト設定の消し方が分からない

---

暇とやる気とチョコレートがあったら追記します。
