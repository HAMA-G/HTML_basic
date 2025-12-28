## 要素セレクタ
要素（タグ名）を記載するセレクタ
```HTML
<style>
	h1 {
		color: red;
	}
</style>
<h1>Title</h1>
```

## クラスセレクタ
HTMLタグには、「class」というグローバル属性がある。
各要素をグルーピングすることができる。
クラスセレクタは、このclass属性を使って要素を指定するセレクタ
ドットで始める
```HTML
<style>
	.box {
		color: red;
	}
</style>
<div class="box">box</div>
```
要素名を先に付加すると、要素で絞り込むこともできる
あまり一般的ではない
```html
<style>
	div.box {
		color: red;
	}
</style>
<div class="box">box</div>
```
## IDセレクタ
グローバル属性である「id」属性を使って指定する
id属性の値はページ内で1つしか指定できない
特定の要素を確実に指定できるが、近年ではIDセレクタが使われrうことはあまりない
JavaScriptで使用されることが多い
```html
<style>
	#titile1 {
		color: red;
	}
</style>
<h1 id="title1">Title</h1>
```
## 全称セレクタ（ユニバーサルセレクタ）
「\*」という記号でページのすべての要素を洗わず
実際にはあまり利用されない
リセットCSSなどで使われているもの
```HTML
<style>
	* {
		margin: 0;
	  }
</sytle>
```
# 階層を使ったセレクタ
## 子孫セレクタ
ある要素の中にある要素を指定する
```HTML
<style>
	div p {
		color: red;
	  }
</sytle>
<div>
	<p>Paragraph</p>
</div>
```
## 子セレクタ
子孫セレクタとの違い

| セレクタ   | 説明            |
| ------ | ------------- |
| 子孫セレクタ | 親の中にあるもの全てが対象 |
| 子セレクタ  | 直下の子だけが対象となる  |
「>」という記号を使う
```HTML
<style>
	div > p {
		color: red;
	  }
</sytle>
<div>
	<p>これは対象です</p>
	<article>
		<p>Article</p>
	</article>
</div>
```
## 隣接兄弟セレクタ
要素同士が隣り合っている場合に、ある要素の直後にある要素の場合だけ対象とする
利用方法：見出し直後の本文にだけ特別な処理をしたい場合など
```HTML
<style>
	h2 + p {
		color: red;
	  }
</sytle>
<h2>Title</h2>
<p>これは対象です</p>
<p>これは非対象です</p>
```
## 後続兄弟セレクタ
ある要素の後にある指定した要素が対象となる

```HTML
<style>
	h2 ~ p {
		color: red;
	  }
</sytle>
<h2>Title</h2>
<p>これは対象です</p>
<p>これも対象です</p>
```
## 属性を使ったセレクタ
classやidなどの特定の属性だけでなく、さまざな属性の値を使ってようそを指定できる
## 属性の有無
「\[\]」で要素の名前を囲むことで、その属性が指定された要素を指定する

```HTML
<style>
	[required] {
		background-color: red;
	  }
</sytle>
<input type="text" name="name" required>
```
## 値の一致
属性の値が指定されたもののみを指定できる
「=」値が完全一致する場合のみ
```HTML
<style>
	[type="text"] {
		background-color: red;
	  }
</sytle>
<input type="text" name="name" required>
```
「~=」とすると、その値が含まれている複数指定されている場合でも指定可能
```HTML
<style>
	[class~="button"] {
		color: red;
	  }
</sytle>
<input class="button" name="name" required>
```
前方一致、後方一致、部分一致の指定
あまり使われていない印象
```HTML
<style>
	/*前方一致*/
	[lang^="-en"] {
		color: red;
	  }

	/*後方一致*/
	[lang$="-en"] {
		color: red;
	  }

	/*部分一致*/
	[lang*="en"] {
		color: red;
	  }
</sytle>
<input class="button" name="name" required>
```

## 擬似クラス
https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Selectors/Pseudo-classes
### マウスオーバー
マウスカーソルが重なった時のみ適用される
スマホの時には反応しないので注意！
マウスオーバーの時に色が変わるなどで使用する程度にとどめ、
コメントが表示されるといった細かな設定には使用しない
```CSS
a:hover {
	color: red;
}
```
### チェック状態
チェックボックスなどでチェックされた時に適用される
```CSS
input:checked {
	color: red;
}
```
### フォーカスが当たっている時
フォーカスが当たっているときに適用される
```CSS
input:focus {
	color: red;
}
```
### 空の場合
子要素に何もない時に適用される
```HTML
<style>
	p:hover {
		color: red;
	}
</style>

<p></p>
```
### 順番を指定する
セレクタの中で順番などを使って細かく指定することができる
```CSS
/* 最初の要素 */
li:first-child {
	color: red;
}

/* 最後の要素 */
li:last-child {
	color: red;
}

 /* 2番目の要素 */
li:nth-child(2) {
	color: red;
}

/* 奇数の要素 */
li:nth-child(odd) {
	color: red;
}
```
## 擬似要素
https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Selectors/Pseudo-elements
要素っぽく見せることができるもの
### 要素の前後
contentプロパティはCSSを使って文字などを追加することができる
```CSS
 /* 要素の前にコンテンツを追加 */
p::befire {
	content: "★";
}

 /* 要素の後にコンテンツを追加 */
p::after {
	content: "★";
}
```
### 最初の文字や行
```CSS
 /* 最初の1文字を装飾 */
p::first-letter {
	font-size:2em;
}

 /* 最初の1行を装飾 */
p::first-line {
	color: red;
}
```