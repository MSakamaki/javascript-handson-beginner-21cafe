


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