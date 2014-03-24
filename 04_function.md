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


これは2つの数値を加算し、その結果を関数です。

```javascript


// 関数を定義
function plus(x, y) {
	return x + y;
}

```



## Objectと配列と関数と


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
