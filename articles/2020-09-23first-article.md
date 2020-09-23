---
title: "ふわっとスクロールの軽量ライブラリ•ScrollReveal.js"
emoji: "🎈"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["javascript"]
published: true
---

ページのスクロールをした際に、要素をふわっと表示させるあのアニメーション。
実装の方法を調べると結構な確率でjQueryでの方法がでてきます。
jQueryを使わない方法で探したところ、ScrollReveal.jsを見つけたのでここに備忘録。
軽量で実装&すごく簡単！

![scrollreveal](https://storage.googleapis.com/zenn-user-upload/7dx31023euqx48fv1ak94308zn5t)

## CDNで読み込みorパッケージインストール
### CDN
公式サイト[ScrollReveal](https://scrollrevealjs.org/)から読み込みます。
読み込むためにはindex.htmlの中のbodyタグの閉じタグ</body>の直前[^1]にscriptタグをおきます。
[^1]:[</body>直前におく理由](https://wp-p.info/tpl_rep.php?cat=js-biginner&fl=r2)
```text
<script src="https://unpkg.com/scrollreveal"></script>
```
### npm
npmでインストールするには下記コマンドを実行。
```text
npm install scrollreveal --save
```
セットアップは完了。

### 動かしたい要素にクラスをつける
```html
<div class="animate">動かしたい要素</div>
```
ここでは動かしたい箇所にanimateというclassをつけました。

###  アニメーション実装
jsの方で読み込んである関数を実行するだけ！
```js
ScrollReveal().reveal('.animate');
```
これで最低限の動きは実装できました。
@[codepen](https://codepen.io/Butter67/pen/LYNWgZQ)


さらにオプションで、細かい設定が可能。

| オプション | 値 (default) | 説明 |
| ---- | ---- | ---- |
| origin  | string (‘bottom’)   | 動きの起点。オプション: ‘top’, ‘bottom’, ‘left’, ‘right’ |
| delay | number (0) | アニメーションが始まるまでの時間（1min = 1000） |
| duration | number (500) | アニメーション完了までの長さ（1min = 1000） |
| distance | string('0px') | 要素が移動する距離。（px/em/%） |
| opacity | number (0) | アニメーションの透明度（0~1） |
| rotate | object ( { x: 0, y: 0, z: 0 } ) | 要素の回転の方向 |
| scale | number (1) | 始まる時の要素のサイズ |

もっと詳しいオプションのソースなどは[こちら](https://scrollrevealjs.org/api/delay.html)！



要素に各classをつけて、delayを時差設定にして順番に要素が浮きあがるように。

@[codepen](https://codepen.io/Butter67/pen/eYZWQXL)

いろいろ細かく設定すると、いろんな動きで遊べそうです！
軽量＆簡単がとにかくいいですね。

サクッと実装の際にはぜひ使ってみてください〜

