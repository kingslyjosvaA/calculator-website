# calculator-website
<!DOCTYPE html>
<html>
<head>
  <title>Simple Calculator</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="calculator">
    <input type="text" id="display" readonly>
    <div>
      <button onclick="clearDisplay()">C</button>
      <button onclick="append('7')">7</button>
      <button onclick="append('8')">8</button>
      <button onclick="append('9')">9</button>
    </div>
    <div>
      <button onclick="append('+')">+</button>
      <button onclick="append('4')">4</button>
      <button onclick="append('5')">5</button>
      <button onclick="append('6')">6</button>
    </div>
    <div>
      <button onclick="append('-')">-</button>
      <button onclick="append('1')">1</button>
      <button onclick="append('2')">2</button>
      <button onclick="append('3')">3</button>
    </div>
    <div>
      <button onclick="append('*')">*</button>
      <button onclick="append('0')">0</button>
      <button onclick="append('.')">.</button>
      <button onclick="append('/')">/</button>
    </div>
    <div>
      <button onclick="calculate()">=</button>
    </div>
  </div>

  <script src="script.js"></script>
</body>
</html>
body {
  font-family: Arial;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background: #f2f2f2;
}

.calculator {
  border: 2px solid #333;
  padding: 20px;
  background: white;
  border-radius: 10px;
}

input {
  width: 100%;
  height: 40px;
  margin-bottom: 10px;
  text-align: right;
  font-size: 20px;
}

button {
  width: 60px;
  height: 40px;
  margin: 5px;
  font-size: 18px;
  cursor: pointer;
}
function append(char) {
  document.getElementById("display").value += char;
}

function clearDisplay() {
  document.getElementById("display").value = "";
}

function calculate() {
  try {
    let result = eval(document.getElementById("display").value);
    document.getElementById("display").value = result;
  } catch (e) {
    alert("Invalid Input");
  }
}


