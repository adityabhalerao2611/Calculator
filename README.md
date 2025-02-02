<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Basic Calculator</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <div class="calculator">
    <div class="display">
      <input type="text" id="result" disabled />
    </div>
    <div class="buttons">
      <button class="btn" onclick="appendToDisplay('1')">1</button>
      <button class="btn" onclick="appendToDisplay('2')">2</button>
      <button class="btn" onclick="appendToDisplay('3')">3</button>
      <button class="btn" onclick="appendToDisplay('+')">+</button>

      <button class="btn" onclick="appendToDisplay('4')">4</button>
      <button class="btn" onclick="appendToDisplay('5')">5</button>
      <button class="btn" onclick="appendToDisplay('6')">6</button>
      <button class="btn" onclick="appendToDisplay('-')">-</button>

      <button class="btn" onclick="appendToDisplay('7')">7</button>
      <button class="btn" onclick="appendToDisplay('8')">8</button>
      <button class="btn" onclick="appendToDisplay('9')">9</button>
      <button class="btn" onclick="appendToDisplay('*')">*</button>

      <button class="btn" onclick="appendToDisplay('0')">0</button>
      <button class="btn" onclick="clearDisplay()">C</button>
      <button class="btn" onclick="calculate()">=</button>
      <button class="btn" onclick="appendToDisplay('/')">/</button>
    </div>
  </div>

  <script src="script.js"></script>
</body>
</html>

<!--css code-->
/* CSS for the Calculator */
body {
    font-family: Arial, sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background-color: #f4f4f4;
    margin: 0;
  }
  
  .calculator {
    background-color: white;
    border-radius: 10px;
    box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
    overflow: hidden;
  }
  
  .display {
    background-color: #222;
    color: white;
    padding: 20px;
  }
  
  #result {
    width: 100%;
    height: 50px;
    font-size: 2em;
    text-align: right;
    border: none;
    background: transparent;
    color: white;
  }
  
  .buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
    padding: 20px;
  }
  
  .btn {
    background-color: #f0f0f0;
    padding: 20px;
    font-size: 1.5em;
    border: none;
    cursor: pointer;
    transition: background-color 0.3s;
  }
  
  .btn:hover {
    background-color: #ddd;
  }

  <!--Javascript code-->
  // JavaScript for the Calculator functionality
let display = document.getElementById("result");

// Append the clicked value to the display screen
function appendToDisplay(value) {
  display.value += value;
}

// Clear the display screen
function clearDisplay() {
  display.value = "";
}

// Calculate the expression entered
function calculate() {
  try {
    display.value = eval(display.value); // Evaluates the expression entered
  } catch (e) {
    display.value = "Error"; // If there's an error in the calculation, show "Error"
  }
}

