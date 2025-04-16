<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Simple Calculator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f4;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
    .calculator {
      background: #222;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 15px rgba(0,0,0,0.3);
    }
    .calculator input {
      width: 100%;
      height: 60px;
      font-size: 24px;
      text-align: right;
      margin-bottom: 10px;
      padding: 10px;
      border: none;
      border-radius: 5px;
    }
    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 60px);
      gap: 10px;
    }
    .buttons button {
      font-size: 20px;
      padding: 15px;
      border: none;
      border-radius: 5px;
      background: #444;
      color: #fff;
      cursor: pointer;
    }
    .buttons button:hover {
      background: #666;
    }
    .buttons .equals {
      grid-column: span 2;
      background: #0a84ff;
    }
  </style>
</head>
<body>

  <div class="calculator">
    <input type="text" id="display" disabled />
    <div class="buttons">
      <button onclick="clearDisplay()">C</button>
      <button onclick="appendValue('(')">(</button>
      <button onclick="appendValue(')')">)</button>
      <button onclick="appendValue('/')">÷</button>
      
      <button onclick="appendValue('7')">7</button>
      <button onclick="appendValue('8')">8</button>
      <button onclick="appendValue('9')">9</button>
      <button onclick="appendValue('*')">×</button>
      
      <button onclick="appendValue('4')">4</button>
      <button onclick="appendValue('5')">5</button>
      <button onclick="appendValue('6')">6</button>
      <button onclick="appendValue('-')">−</button>
      
      <button onclick="appendValue('1')">1</button>
      <button onclick="appendValue('2')">2</button>
      <button onclick="appendValue('3')">3</button>
      <button onclick="appendValue('+')">+</button>
      
      <button onclick="appendValue('0')">0</button>
      <button onclick="appendValue('.')">.</button>
      <button class="equals" onclick="calculate()">=</button>
    </div>
  </div>

  <script>
    function appendValue(val) {
      document.getElementById('display').value += val;
    }

    function clearDisplay() {
      document.getElementById('display').value = '';
    }

    function calculate() {
      try {
        document.getElementById('display').value = eval(document.getElementById('display').value);
      } catch {
        document.getElementById('display').value = 'Error';
      }
    }
  </script>

</body>
</html>
