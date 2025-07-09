<h1>CALCULATER</h1>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Simple Calculator</title>
  <style>
    body {
      background: #f1f1f1;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      font-family: Arial, sans-serif;
    }
    .calculator {
      background: #fff;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 15px rgba(0, 0, 0, 0.2);
    }
    input[type="text"] {
      width: 100%;
      padding: 15px;
      font-size: 1.5em;
      margin-bottom: 10px;
      text-align: right;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 60px);
      gap: 10px;
      justify-content: center;
    }
    button {
      padding: 15px;
      font-size: 1.2em;
      cursor: pointer;
      border: none;
      border-radius: 5px;
      background-color: #eee;
      transition: background-color 0.2s;
    }
    button:hover {
      background-color: #ddd;
    }
    .equal {
      grid-column: span 2;
      background-color: #4CAF50;
      color: white;
    }
    .clear {
      background-color: #f44336;
      color: white;
    }
  </style>
</head>
<body>
  <div class="calculator">
    <input type="text" id="display" readonly />
    <div class="buttons">
      <button onclick="clearDisplay()" class="clear">C</button>
      <button onclick="appendValue('/')">÷</button>
      <button onclick="appendValue('*')">×</button>
      <button onclick="appendValue('-')">−</button>

      <button onclick="appendValue('7')">7</button>
      <button onclick="appendValue('8')">8</button>
      <button onclick="appendValue('9')">9</button>
      <button onclick="appendValue('+')">+</button>

      <button onclick="appendValue('4')">4</button>
      <button onclick="appendValue('5')">5</button>
      <button onclick="appendValue('6')">6</button>

      <button onclick="appendValue('1')">1</button>
      <button onclick="appendValue('2')">2</button>
      <button onclick="appendValue('3')">3</button>
      <button onclick="calculate()" class="equal">=</button>

      <button onclick="appendValue('0')">0</button>
      <button onclick="appendValue('.')">.</button>
    </div>
  </div>

  <script>
    const display = document.getElementById('display');

    function appendValue(value) {
      display.value += value;
    }

    function clearDisplay() {
      display.value = '';
    }

    function calculate() {
      try {
        display.value = eval(display.value);
      } catch (e) {
        display.value = 'Error';
      }
    }
  </script>
</body>
</html>
