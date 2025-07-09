# LinuxCalculator

Images 

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Modern Calculator</title>
  <style>
    * {
      box-sizing: border-box;
      font-family: 'Segoe UI', sans-serif;
    }

    body {
      margin: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(135deg, #2c3e50, #4ca1af);
    }

    .calculator {
      background-color: #fff;
      padding: 20px;
      border-radius: 20px;
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
      width: 320px;
    }

    .display {
      height: 60px;
      background: #222;
      color: #fff;
      font-size: 2rem;
      padding: 10px;
      text-align: right;
      border-radius: 10px;
      overflow: hidden;
      margin-bottom: 15px;
    }

    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
    }

    button {
      padding: 20px;
      font-size: 1.2rem;
      border: none;
      border-radius: 10px;
      background-color: #ecf0f1;
      cursor: pointer;
      transition: 0.2s;
    }

    button:hover {
      background-color: #d0d7dc;
    }

    .operator {
      background-color: #f39c12;
      color: white;
    }

    .operator:hover {
      background-color: #e67e22;
    }

    .equals {
      background-color: #2ecc71;
      color: white;
      grid-column: span 2;
    }

    .equals:hover {
      background-color: #27ae60;
    }

    .clear {
      background-color: #e74c3c;
      color: white;
    }

    .clear:hover {
      background-color: #c0392b;
    }
  </style>
</head>
<body>

<div class="calculator">
  <div class="display" id="display">0</div>
  <div class="buttons">
    <button class="clear" onclick="clearDisplay()">C</button>
    <button onclick="deleteChar()">⌫</button>
    <button onclick="append('%')">%</button>
    <button class="operator" onclick="append('/')">÷</button>

    <button onclick="append('7')">7</button>
    <button onclick="append('8')">8</button>
    <button onclick="append('9')">9</button>
    <button class="operator" onclick="append('*')">×</button>

    <button onclick="append('4')">4</button>
    <button onclick="append('5')">5</button>
    <button onclick="append('6')">6</button>
    <button class="operator" onclick="append('-')">−</button>

    <button onclick="append('1')">1</button>
    <button onclick="append('2')">2</button>
    <button onclick="append('3')">3</button>
    <button class="operator" onclick="append('+')">+</button>

    <button onclick="append('0')">0</button>
    <button onclick="append('.')">.</button>
    <button class="equals" onclick="calculate()">=</button>
  </div>
</div>

<script>
  const display = document.getElementById('display');

  function append(char) {
    if (display.innerText === '0' || display.innerText === 'Error') {
      display.innerText = char;
    } else {
      display.innerText += char;
    }
  }

  function clearDisplay() {
    display.innerText = '0';
  }

  function deleteChar() {
    if (display.innerText.length === 1 || display.innerText === 'Error') {
      display.innerText = '0';
    } else {
      display.innerText = display.innerText.slice(0, -1);
    }
  }

  function calculate() {
    try {
      display.innerText = eval(display.innerText.replace(/×/g, '*').replace(/÷/g, '/'));
    } catch (e) {
      display.innerText = 'Error';
    }
  }
</script>

</body>
</html>



https://github.com/atharvasangale7/LinuxCalculator/blob/5b2b7f51f3375de377c64767e398bbe5dc5e5fc2/Screenshot%202025-07-09%20213831.png
