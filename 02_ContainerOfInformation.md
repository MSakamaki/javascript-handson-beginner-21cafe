# 情報の入れ物を作る。

##  変数(variable)

### 変数の書き方

```javascript
var [変数名] = [情報];
```

 + 変数は「情報を格納する箱」です。
 + 変数名は「箱を一意に特定する為の名前」です。

### javascript変数の種類

 + 数値
 + 文字列
 + 日付
 + 真偽値
 + 配列
 + オブジェクト
 + null / undefined

<small>その他にも正規表現、Error、JSONなどありますが今回は割愛します。</small>

### 書き方


| 型 | 変数iに値を格納する場合 | 何のために使う？ |
|:---|:---|:---|
| 数値(Integer) | ``var i = 100;`` | 数値を扱う、計算などが目的 |
| 文字列(String) | ``var i = "hello";`` もしくは ``var i = 'hello';`` | 文字を扱う |
| 日付(Date) | ``var i = new Date(2014,3,25);`` | 日付を扱う |
| 真偽値(Boolean) | ``var i = true;`` | 判定をしたいときに |
| 配列(Array) | ``var i = [];`` | 連続した情報の塊を持ちたいとき |
| オブジェクト(Object) | ``var i = {};`` | キーにデータを関連付けて保存したいとき |
| null | ``var i = null;`` | 値が無いオブジェクトを示す |
| undefined | ``var i = undefined;`` | まだ値が代入されていないことを示す |


### 変数の中身を見る

変数の中身を表示してみましょう。  
以下のケースは``console.log()``、``alert()``、``document.body.innerText``を使いって変数の中身をそれぞれ表示しています。

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

### 変数同士の組み合わせ

#### 数値 + 数値

```javascript


console.log( 100 + 200 );

```

#### 文字列 + 文字列

```javascript


console.log( "hello" + "world" );

```

#### 文字列 + 数値

```javascript


console.log( "hello" + 100);

```

### 変数の必要性

変数に格納しておく事で、繰り返し出現する要素を一元管理できる。

```javascript


var height = 100;
var width = 50;
var length = 80;

document.body.innerText
 = "立方体の面積は高さ×幅×奥行きで求めます。"
 + " 高さは" + height
 + " 幅は" + width
 + " 奥行きは" + length
 + " 計算式は" + height + "×" + width + "*" + length + "で、結果は"
 + (height * width *  length)
 + "です。";


```

### 配列とObject

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

配列に格納されている特定の値だけを見たい場合は次のように書きます。

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















