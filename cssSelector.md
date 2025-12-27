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
