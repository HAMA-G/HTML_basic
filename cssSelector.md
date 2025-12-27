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