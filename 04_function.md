# 処理の塊を作る

今までの章ではプログラムの流れを学習してきました。

これからその流れを一つの塊にして、目的を達成する為の命令セットを作っていきます。

## 関数

関数の定義方法は次のように書きます。

```javascript


function 関数名( 引数 ) { 
  処理
  return 戻り値
};

```

| 名前 | 説明 |
|:--|:--|
| 関数名 | この関数の名前です |
| 引数  | この関数に渡される引数です、カンマ区切りで渡せます |
| 処理  | この関数のメイン処理を書きます。|
| 戻り値 | 処理が完了した時点で戻す値を書きます。 |


#### 関数の作り方

次の例は、2つの数値を加算して、その結果を返す関数を定義しています。

```javascript


// 関数を定義します。
function plus(x, y) {
	console.log( x, "と", y, "を加算します。" );
	return x + y;
}

```

#### 関数の使い方

この関数を使う場合、次のように呼び出します。

```javascript


console.log("plus()の結果は", plus(10, 20));

```

１度関数を定義しておくと、様々な場面や用途で繰り返し使うことができるようになります。


```javascript


console.log("  5 + 10 = ", plus(5,  10));
console.log("  8 +  3 = ", plus(8,   3));
console.log(" 12 + 12 = ", plus(12, 12));
console.log("  5 +  5 = ", plus(5,   5));

```

### スコープ

関数を使う重要な要素として、スコープがあります。

#### グローバル変数とローカル変数

今回説明するのはグローバル変数とローカル変数です。

|名前|説明|
|:--|:--|
|グローバル変数|プログラム全体から参照できる|
|ローカル変数|宣言した関数の中でのみ参照できる|

特定の関数の中で変数を宣言した場合、それはローカル変数になります。

グローバル変数はどこからでも見ることができますが、ローカル変数は関数の外で参照できません。

```javascript 


// グローバル変数を宣言する。
var grbl = "Grobal";

function fnc(){
	// ローカル変数を宣言する。
	var scope = "local";

	console.log("グローバル変数を関数内で参照", grbl);
	console.log("ローカル変数を関数内で参照",scope);
}

// 関数fnc実行
fnc();

console.log("グローバル変数を関数の外で参照", grbl);
console.log("ローカル変数を関数の外で参照", scope);

```

#### ``var``の役割

変数は``var``をつけなくても宣言ができます。

では、今まで何故``var``を付けて変数宣言をしていたかというと、``var``を付けない場合、すべてグローバル変数で作成されてしまうためです。

以下の例では、関数内で``var``を付けずに変数を宣言にしています。

この変数は関数の外でも参考可能なグローバル変数で作られています。

```javascript


function fnc(){
	// グローバル変数を宣言
	scope = "local?";
	console.log("変数を関数内で参照",scope);
}
// 関数fnc実行
func();

console.log("変数を関数の外で参照",scope);


```


#### **注意**

前の章の注意点にも書きましたが、宣言した変数は上書きができてしまいます。

以下の例ように``hoge``関数を作り、その後hogeに新たな値を代入すると、文字列に変化してしまいます。

変数/関数の上書きには注意しましょう。

```javascript


function hoge (){
	console.log("hoge call");
}
console.log(hoge());

hoge = "foo";

console.log(hoge());

```

### サンプル問題

 + Ｃａｎｖａｓで ■ が自動的に動くプログラムです。
 + それぞれ用意した関数と変数を書き換えながら、■を動かしてみましょう。
 + 

```html

<!doctype html>
<html>
<head>
	<meta charset="UTF-8">
</head>
<body>
	<canvas id="cnvs" width="140" height="140"></canvas>
</body>
<script>

var canvas = document.getElementById("cnvs");
var ctx = canvas.getContext('2d');

var x = 10,
    y = 10,
    w = 10,
    h = 10,
    speed = 100;

function fn_x(){
	return x++;
}
function fn_y(){
	return y;
}
function fn_w(){
	return w;
}
function fn_h(){
	return h;
}

function viewCanvas(){
	ctx.fillStyle = '#000';
	ctx.fillRect(0, 0, canvas.width, canvas.height);
	ctx.fillStyle = '#fff';
	ctx.fillRect(fn_x(), fn_y(), fn_w(), fn_h());
	window.setTimeout("viewCanvas()", speed);
};

viewCanvas();

</script>
</html>

```

#### へんてこ動作のサンプル

##### 計算、Math関数を用いたＹ座標

```javascript
function linear(x) {
    return x / 2;
}

function sin(x) {
    return Math.sin(x) * 300; // 0.0 - 1.0が返ってくるので倍率ドン
}

function tan(x) {
    return Math.tan(x) * 300; // 0.0 - 1.0が返ってくるので倍率ドン
}
```

このように書き換える。

```javascript
function fn_y(){
	return linear(x);
}
```

##### Ｕターンをしてみる。

```javascript
function fn_x(){
	if (y >= 120 ) {
		return x--;
	}else if ( x >= 120 ) {
		return x;
	}
	return x++;
}
function fn_y(){
	if ( y >= 120 ) {
		return y;
	} else if ( x >= 120 ) {
		return y++;
	}
	return y;
}
```
##### マウスの追跡

traceX()と、traceY()をfn_x(), fn_y(), x, yそれぞれと置き換えてみる。

```javascript
var mouseX = 0,
    mouseY = 0;
function traceX() {
    return mouseX;
}
function traceY() {
    return mouseY;
}
document.addEventListener("mousemove" , function(e) { mouseX = e.clientX; });
document.addEventListener("mousemove" , function(e) { mouseY = e.clientY; });
```

### サンプル問題

 + 計算機を作ってみましょう
 + +,-,×,÷と、数値を入力して、最後に＝を押すと計算結果を出すプログラムを作りましょう。
 + CEを入力すると計算中の結果も画面のクリアされます。
 + やってみよう
	+ 途中の計算式
	+ 加減算と乗除算の優先順位をつけて計算するには・・・？

```html


<!doctype html>
<html>
<head>
	<meta charset="UTF-8">
</head>
<body>
	<div>
    	<label id="calculation">&nbsp;</label>
    </div>
    <div>
		<button onclick="ope('7');"> 7 </button>
		<button onclick="ope('8');"> 8 </button>
		<button onclick="ope('9');"> 9 </button>
		<button onclick="ope('÷');"> ÷ </button>
	</div>
	<div>
		<button onclick="ope('4');"> 4 </button>
		<button onclick="ope('5');"> 5 </button>
		<button onclick="ope('6');"> 6 </button>
		<button onclick="ope('×');"> × </button>
	</div>
	<div>
		<button onclick="ope('1');"> 1 </button>
		<button onclick="ope('2');"> 2 </button>
		<button onclick="ope('3');"> 3 </button>
		<button onclick="ope('-');"> － </button>
	</div>
	<div>
		<button onclick="ope('0');"> 0 </button>
		<button onclick="ope('.');"> ．</button>
		<button onclick="ope('=');"> = </button>
		<button onclick="ope('+');"> ＋ </button>
		<button onclick="ope('CE');"> CE </button>
    </div>
</body>
<script>

var calculation = document.getElementById("calculation");

var ope = function(operator){
	console.log("演算子", operator);
	console.log("計算式", calculation.textContent);

	// ここに処理を書いて計算機プログラムを完成させよう

	// 結果を表示する。
	calculation.textContent += operator;
}

</script>
</html>


```
