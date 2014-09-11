#js4kintro

javascript と WebGL、そして GLSL を用いて行う 4k イントロのためのひな形ファイルです。

現状ではベースファイルの容量が約 1.6 キロバイトになっています。工夫次第で約 2.5 キロバイトほどフラグメントシェーダのコードが書けるはずです。

基本的な仕様は以下参照。

* ブラウザのクライアント領域全面に canvas を配置
* canvas サイズだけでなく viewport もクライアント領域に合わせて動的に書き換え
* window.onload で動作開始、ESC キーによって動作を停止
* アニメーションは setTimeout を利用しており更新頻度は 16ms を指定
* シェーダのコンパイルとリンクをチェックしておりエラーがある場合には動作しない
* 極力ブラウザの違いによって動作に差がでないように WebGL 本体部分を設計
* ソース全体として、頑張れば人が読める程度の可読性を残す(黒魔術的記載はしない)


##ルール(仮)

* ファイルサイズは 4096 バイト以下でなくてはならない
* HTML には最終的にタイトル(titleタグ)を含めるがこれはファイルサイズにカウントしない
* HTML、javascript、または css を現状よりも minify する場合には pull request
* サウンド処理を追加するなどの特別な事情があり js 等に **追記するのは** OK
* ただし、js や css に手を入れた場合は理由と共に明文化すること
* 最低でも 512px 以上の矩形領域で動作することを保証


##今後の見通し

本企画はいずれちゃんとした形で投稿型イベントとして開催したい。

現状、GLSL オンリーでの描画は特別なことをやろうとすると特に、実行環境を選ぶケースがあり、あらゆる環境で安定して動作するシェーダを書くのは難しい場合がある。

企画にする場合には、ハードウェアの構成をしっかりと決めて事前に公開しておくこと、また、あらかじめ運営側で動作確認をしておきそれが作者の意図したものと同じ動作をしているのかどうか確認する手段が必要。


##動作環境の問題

ひとつの基準として、MacBookAir(1.4GHzデュアルコアIntel Core i5+Intel HD Graphics 5000+メモリ8MB+13.3インチ)で普通に動くかどうか。

Windows マシンは基準がさらに難しい。3DMark FireStrike でスコア 1000 位のマシンで平常運転できるかどうかくらいが目安になりそうな気がする。

ちなみに、MacBookAir 2014 モデルの上記構成とほぼ同じものが FireStrike のスコアとして 700～800 前後だと思われる。
