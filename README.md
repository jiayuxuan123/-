
          <!DOCTYPE html>
<html>
  <head>
	<meta charset="utf-8" name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no">
	<title>WebCat</title>
  </head>
  <body>	
  </body>
</html>
<!DOCTYPE html>
<html lang="zh-CN">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>带撤回键和清除键的计算器</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
            background-color: #f5f5f5;
            padding: 10px; 
        }
       .calculator {
            background-color: #ffffff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            width: 90%; 
            max-width: 360px; 
        }
       .display {
            width: 100%; 
            height: 60px;
            font-size: 2em;
            margin-bottom: 20px;
            border: none;
            border-radius: 5px;
            padding: 0 10px;
            text-align: right;
            background-color: #f0f0f0;
        }
       .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr); 
            grid-gap: 10px;
        }
       .button {
            font-size: 1.5em;
            border: none;
            border-radius: 5px;
            background-color: #e0e0e0;
            color: #333333;
            padding: 15px; 
            cursor: pointer;
            transition: background-color 0.3s ease;
        }
       .button:hover {
            background-color: #d0d0d0;
        }
       .operator {
            background-color: #007aff;
            color: #ffffff;
        }
       .operator:hover {
            background-color: #0062cc;
        }
       .equal {
            background-color: #00cc66;
            grid-column: span 2;
            color: #ffffff;
        }
       .equal:hover {
            background-color: #00a34d;
        }
       .clear {
            background-color: #ff4d4d;
            color: #ffffff;
            grid-row: 1;
            grid-column: 1;
        }
       .clear:hover {
            background-color: #e03e3e;
        }
       .delete {
            background-color: #ff9800;
            color: #ffffff;
            grid-row: 1;
            grid-column: 2;
        }
       .delete:hover {
            background-color: #e68a00;
        }
       .repo-link {
            margin-top: 20px;
            font-size: 0.8em;
            color: #333;
        }
       .repo-link a {
            color: #007aff;
            text-decoration: none;
        }
       .repo-link a:hover {
            text-decoration: underline;
        }
    </style>
</head>

<body>
    <div class="calculator">
        <input type="text" id="display" class="display" readonly>
        <div class="buttons">
            <button class="button clear" onclick="clearDisplay()">C</button>
            <button class="button delete" onclick="deleteValue()">←</button>
            <button class="button" onclick="appendValue('7')">7</button>
            <button class="button operator" onclick="appendValue('/')">÷</button>
            <button class="button" onclick="appendValue('4')">4</button>
            <button class="button" onclick="appendValue('5')">5</button>
            <button class="button" onclick="appendValue('6')">6</button>
            <button class="button operator" onclick="appendValue('*')">×</button>
            <button class="button" onclick="appendValue('1')">1</button>
            <button class="button" onclick="appendValue('2')">2</button>
            <button class="button" onclick="appendValue('3')">3</button>
            <button class="button operator" onclick="appendValue('-')">-</button>
            <button class="button" onclick="appendValue('0')">0</button>
            <button class="button" onclick="appendValue('.')">.</button>
            <button class="button equal" onclick="calculate()">=</button>
            <button class="button operator" onclick="appendValue('+')">+</button>
        </div>
    </div>
    <div class="repo-link">
        该计算器项目已开源，访问 <a href="https://github.com/jiayuxuan123/-" target="_blank">GitHub仓库</a> 查看更多。
    </div>
    <script>
        function appendValue(value) {
            document.getElementById('display').value += value;
        }
        function calculate() {
            try {
                let result = eval(document.getElementById('display').value);
                document.getElementById('display').value = result;
            } catch (error) {
                document.getElementById('display').value = '错误';
            }
        }
        function deleteValue() {
            let currentValue = document.getElementById('display').value;
            document.getElementById('display').value = currentValue.slic