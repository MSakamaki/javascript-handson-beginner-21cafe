# 情報の入れ物を作る。

##  変数(variable)

### 変数の書き方

```javascript


var [変数名] = [情報];

```

 + 変数は「情報を格納する箱」です。
 + 変数名は「箱を一意に特定する為の名前」です。

変数は「宣言」と「代入」を行うことにより、情報を持つことができます。

```javascript


// 変数iを宣言
var i;

// 変数iに100を代入する。
i = 100;

// 次のように宣言と代入を一度に行うこともできます。
var x = 200;

```

### 変数を使う。

変数の中身を表示してみましょう。

以下のケースは``console.log()``、``alert()``、``document.body.innerText``を使って変数の中身を表示しています。

#### 例

```javascript


// メッセージ「hello world !」が入っている変数「message」を作る。
var message = "hello world !";

// ブラウザ上に表示する。
document.body.innerText = message;

// アラートに表示する。
alert(message);

// コンソール上に表示する。
console.log(message);

```

## リテラル

javascriptには様々なデータの種類があります。

### javascript型

 + 数値
 + 文字列
 + 論理型
 + オブジェクト
 + null / undefined

### 書き方

javascriptは、様々な値の型を、自動的に判定しています。

| 型 | 変数iに値を格納する場合 | 何のために使う？ |
|:---|:---|:---|
| 数値(Integer) | ``var i = 100;`` | 数値を扱う、計算などが目的 |
| 文字列(String) | ``var i = "hello";`` | 文字を扱う |
| 論理型(Boolean) | ``var i = true;`` | デジタルな考えをしたいときに |
| オブジェクト(Object) | ``var i = {};`` | キーにデータを関連付けて保存したいとき |
| 配列(Array) | ``var i = [];`` | 連続した情報の塊を持ちたいとき |
| null | ``var i = null;`` | 値が無いオブジェクトを示す |
| undefined | ``var i = undefined;`` | まだ値が代入されていないことを示す |

### 変数の型を検知する。

変数の値がどんな型かをみるには、``typeof``や``instanceof``を使います

しかし、この機能は複雑なので今回は飛ばします。

```javascript 


// プリミティブ型の判定
var tmp = "hello javascript";

console.log(typeof tmp);
console.log( tmp instanceof String );

// オブジェクト型の判定
var ntmp = new String("hello new JavaScript");

console.log(typeof ntmp);
console.log( ntmp instanceof String );

```

### 変数同士の組み合わせ

``+``を使うと、変数と変数を組み合わせ、新たな結果を作ることができます。

その時、どのような型同士を使ったかにより、様々な結果が帰ります。

#### 数値 + 数値

```javascript


console.log( 100 + 200 );

```

#### 文字列 + 文字列

```javascript


console.log( "100" + "200" );

```

#### 文字列 + 数値

```javascript

// 文字列 ＋ 数値
console.log( "100" + 200 );

// 数値 ＋ 文字列
console.log( 100 + "200" )

```

### 変数を使ってみる。

変数に格納しておく事で、繰り返し出現する要素を一元管理できます。

```javascript

var height = 100;
var width = 50;
var length = 80;

// 計算を行います。
var answer = height * width * length;

document.body.innerText
 = "立方体の面積は高さ×幅×奥行きで求めます。"
 + "高さは" + height
 + "、幅は" + width
 + "、奥行きは" + length
 + "、計算式は" + height + "×" + width + "*" + length + "で、結果は"
 + answer + "です。";

```

## 配列とObject

オブジェクトや配列はいろいろな情報（変数）を、一つの変数として管理できるものです。

変数が箱だとすると、配列やObjectはタンスのようなものです。

#### 配列

配列は、連続した変数の塊です。

宣言は次のように行います。

```javascript


var ary = ["A","B","C"];

```

この配列は、文字列AとBとCを順番に格納しています。

中身を見る場合、以下のように書いてみましょう。

配列の中身がすべて見えるはずです。

```javascript


console.log(ary);

```

配列に格納されている特定の値だけを見たい場合は、次のように``変数名[見たい位置]``のように書きます。

```javascript


console.log(ary[1]);

```

配列の操作を行う場合はそれぞれ以下のように書きます。

```javascript 


// 配列の宣言
var ary = ['A','B','C'];

// 配列に値Dを追加
ary.push('D');

// 配列の2番目の値(B)をKに書き換える。
ary[1] = 'K';

// 配列3番目の値から、1個削除する。
ary.splice(2,1);

// 表示すると・・・？
console.log(ary);

```


#### Object

Objectはキーと値を対に持つ変数の塊です。

宣言は次のように書きます。

```javascript


var obj = { A: "エー", B:"ビー", C:"シー" };

```

このオブジェクトにはAと言うキーに"エー"と言う値、Bと言うキーに"ビー"と言う値、Cと言うキーに"シー"と言う値で、文字列をそれぞれ格納しています。

中身をすべて見る場合は配列と同じく以下のように書きます。

```javascript


console.log(obj);

```

オブジェクトに格納されている、特定の値を見たい場合には以下のように書くことが出来ます。


```javascript


console.log(obj.A);

console.log(obj['B']);


```

Objectの操作を行う様々な方法を以下に記します。

```javascript


var obj = { A: "エー", B:"ビー", C:"シー" };

// Objectに値を追加
obj.D = "ディー";
obj['E'] = "イー";

// Object.Bの値を書き換える
obj.B = "ベー";

// Object.Cの値を削除する。
delete obj.C;

// 表示すると・・・？
console.log(obj);

```


