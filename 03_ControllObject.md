# 処理の流れを作る。

この章からプログラムらしくなります。

## 演算子

[MDNリファレンス＠演算子](https://developer.mozilla.org/ja/docs/Web/JavaScript/Guide/Expressions_and_Operators)

プログラムは、前の章で話した変数と、今回紹介する演算子、分岐、繰り返しを使い様々な結果を作り出します。

計算を行う演算子には以下のようなものがあります。

### 算術演算子

 + ``+`` 加算を行います。
 + ``-`` 減算を行います。
 + ``*`` 乗算を行います。
 + ``/`` 除算を行います。
 + ``%`` 除算のあまりを算出します。

以下は算術演算子を用いた、四則演算の例です。

```javascript

var i = 10;
var j = 5;

console.log("加算", i + j );
console.log("減算", i - j );
console.log("乗算", i * j );
console.log("除算", i / j );
console.log("除算あまり", i % j );

```

#### サンプル問題

 + 直径30センチの球体の体積を求めてみましょう。

 + 計算式は、４ × π × 半径 × 半径 × 半径 ÷ ３

 + 円周率(π)は[Mathオブジェクト](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Math)の「Math.PI」より取得しています。

```javascript


// 直径
var diam = 30;
// 円周率（π）
var pi = Math.PI;


// 答えは約「14137.166...」になります。
console.log( 計算式 );

```

### その他いろいろな演算子

計算以外にもいろいろな演算子があります、すべてを紹介するとそれだけで時間が過ぎてしまうので

ここでは、よく使うものをピンポイントで紹介します。

#### 単項演算子

 + ``++``を数値に付けると、インクリメント（値を１つ加算します）
 + ``--``を数値に付けると、デクリメント（値を１つ減らします）
 + ``-``を数値に付けると、符号反転（プラスとマイナスを逆転）させる。

```javascript

var x = 1;

console.log("１回目表示", x);
console.log("２回目表示", ++x);
console.log("３回目表示", x++);
console.log("４回目表示", x);
console.log("４回目表示", -x);

```

#### 代入演算子

代入演算子は、すでに値が入っている変数の値に対して変化を与える場合に使います。

代入演算子にはいろいろなものがあります。

 + ``+=`` 代入対象の変数に、値を加算します。
 + ``-=`` 代入対象の変数から、値を減らします。
 + ``*=`` 代入対象の変数に、値を掛け算します。
 + ``/=`` 代入対象の変数に、値を割り算します。
 + ``%=`` 代入対象の変数に、値を割り算の余りを出します。


```javascript


var x = 100;

console.log("xの値は",x);

// 代入演算子を使う
x += 30;

console.log("代入演算の結果は",x);

```

## 判定

変数、オブジェクトそのものを判定するか、２つのオブジェクトを比較した結果で、論理値を導き出します。

判定の結果（論理値）の値は以下の２種類です。

|値|意味|
|:---|:---|
|``true``| 正しい |
|``false``| 正しくない |


### 判定演算子

２つのデータを比較する場合、判定演算子を使って値を比べます。

 + ``==`` 等しい
 + ``!=`` 等しくない
 + ``===`` 型も含めて等しい
 + ``!==`` 型も含めて等しくない
 + ``>`` 左側が、右側より大きい
 + ``<`` 左側が、右側より小さい
 + ``>=`` 左側が、右側以上
 + ``<=`` 左側が、右側以下

たとえば、変数iとxを判定する場合は以下のように書きます。

```javascript


var i = 10;
var x = 15;

console.log("iとxは同じ？", i == x);
console.log("iとxは違う？", i != x);
console.log("iとxはiの方が大きい？", i >= x);
console.log("iとxはiの方が小さい？", i <= x);

```

### 判定の使い方(if/switch)

この判定を使い、**処理の分岐**を作ってみましょう。

条件によって処理を切り分けるには``if``を使います。

```javascript

// 変数を色々と入力してみる。
var i = window.prompt("文字を入力してください");

// 変数iの値がhelloか？
if (i == "hello") {
	// もし、iがhelloだった場合
	console.log("iはhelloだった");
} else if (i == "world") {
	// ではなく、iがworldだった場合
	console.log("iはworldだった");
} else {
	// どれでもない場合
	console.log("iはhelloでもworldでもなかった");
}

```

１行程度のif分なら、中かっこ {}を省略することもできるが、見辛くなるので一般的に非推奨です。

```javascript


if (i == "hello") 
	console.log("条件が正しい");
else 
	console.log("条件が間違っている");

```

条件を切り分ける方法として、``if``以外にもswitchと言う物があります。

```javascript

var i = window.prompt("数値を入れてください。");
switch(i){
  case "1":
    console.log("入力値が１の場合");
    break;
  case "2":
    console.log("入力値が２の場合");
    break;
  case "3":
    console.log("入力値が３の場合");
    break;
  default:
    console.log("入力値が１、２、３どれでもない場合");
    break;
}

```

#### [おまけ]falseになるデータ

値にはそれだけでtrue/falseの判定として使えるものもあります。

```javascript


// これは true/false ?
if (0) {
	console.log("True?");
} else {
	console.log("False?");
}

```

以下の値は単一で扱った場合falseと判定される物です。

| 型 | 値 |
|:--|:--|
| String | ``""``(空文字) |
| Number | ``0`` |
| null | ``null`` |
| undefined | ``undefined`` |


## 繰り返し

処理を条件に基づき、繰り返します。

javascriptの繰り返し処理で使えるキーワードには様々な物がありますが、今回は基本の以下4つを覚えて貰います。

#### 繰り返し処理で使う代表的なもの

| 文言 | 簡単な説明 |
|:--|:--|
| ``while`` | ループの基本 |
| ``for`` | カウンタを持つことができるループ文 |
| ``break`` | ループから抜けたいとき |
| ``continue`` | 次のループへいきたいとき |


### while

``while``は、条件が正しい間、処理の内容を繰り返し続けます。

``while( 条件式 ) { 処理 }``

以下の例は、変数iが１０より小さい間、処理を繰り返す処理です。

```javascript


var i = 1;
while( i < 10 ) {
	console.log(i, "回目のループ");
	i++;
}

```

``while``の中では、条件を変化させる処理を入れ忘れないようにしましょう、間違えると**永久ループ**に陥ります。

### for

``for``は宣言、反復条件、評価式のセットを持ちます。

``for( 初期化式 ; 条件式 ; 後処理式 ) { 処理 }``

| 名前 | 説明 |
|:--|:--|
| 初期化式 | ループ内だけで有効な変数を宣言します |
| 条件式 | 条件がtrueの間だけ処理を続けます |
| 後処理式 | 処理の実行後、条件式の前に実行される式です |


```javascript


for ( var i = 0 ; i < 10 ; i++ ){
	console.log(i, "回目のループ");
}

```

### break

ある特定条件に達した場合、無条件にループを抜けたい場合に使います。

```javascript


for ( var i = 0 ; i < 10 ; i++ ){
	console.log(i, "回目のループ");
	
	// iが５の時
	if ( i == 5 ) {
		console.log("iが5になりました。breakします。");
		break;
	}
}
console.log("ループ終了しました");

```


### continue

こちらは、ある特定条件下でループの次の処理へ移りたい場合に使います。

```javascript


for ( var i = 0 ; i < 10 ; i++ ){
	// iを３で割ったあまりがゼロの時
	if ( (i % 3) == 0 ) {
		console.log("iが3の倍のときは、処理をスキップします。");
		continue;
	}
	console.log(i, "回目のループ");
}
console.log("ループ終了しました");

```

#### サンプル問題

 + 変数``cup``に1000ｍｌの水が入っています。
 + プロンプトに入れた水の量だけ、変数``cup``の数値を減らしてください。
 + ``cup``が空になったらループを抜けましょう。

```javascript

var cup = 1000;

console.log("[開始]カップに入っている水の量は", cup, "です。");

while( 条件 ){
	// 汲み出した水の量
	var scoop = window.prompt("汲み出す水の量を指定してください。");

	水をくみ出す処理を書く

	console.log("今カップに入っている水の量は", cup, "です。");
}

console.log("[終了]カップに入っている水の量は", cup, "です。");

```
##### おまけで機能追加してみよう

 + プロンプトから数字以外が来たときは？おかしな動きにならないようにしてみよう。
 + 水をくみ過ぎて``cup``がマイナスになったときに、汲めないようにするには？

## まとめ

 + プログラムは変数と変数を演算子で組み合わせ、様々な結果を作り出す。
 + 処理を分岐させるにはif文やswitch文を使って、分ける。
 + ループ処理で、ゆるやかに変化をつけつつ処理を繰り返す。永久ループには注意！
