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

この関数を使う場合、以下のように呼び出します。

```javascript


console.log("plus()の結果は", plus(10, 20));

```

#### サンプル問題

+ 



### サンプル問題

```html


<!doctype html>
<html>
<head>
	<meta charset="UTF-8">
</head>
<body>
    <div><input type="text" id="operand"/></div>
	<div>
	<button onclick="ope('+');"> + </button>
	<button onclick="ope('-');"> - </button>
	<button onclick="ope('×');"> × </button>
	<button onclick="ope('÷');"> ÷ </button>
	<button onclick="ope('=');"> = </button>
    </div>
    <div>
    	<label id="calculation"></label>
    </div>
</body>
<script>

var operandVal = document.getElementById("operand").value;
var calculation = document.getElementById("calculation");

var ope = function(operator){
	console.log(operandVal);
}

</script>
</html>

```
