<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Scientific Calculator</title>
    <link rel="stylesheet" href="styles.css">
</head>
  <body>
    <style>
      body {
    font-family: Arial, sans-serif;
    background-color: rgb(31, 13, 13);
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
   
}

.calculator {
    background-color: white;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    width: 300px;
    
    
    
}

#display {
    width: 100%;
    height: 40px;
    font-size: 24px;
    text-align: right;
    margin-bottom: 10px;
    padding: 5px;
    border: 1px solid #ccc;
    border-radius: 5px;
}

.buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
}

button {
    padding: 15px;
    font-size: 18px;
    border: none;
    border-radius: 5px;
    background-color: #007bff;
    color: white;
    cursor: pointer;
    transition: background-color 0.3s;
}

button:hover {
    background-color: #0056b3;
}
    </style>
  </body>
<body>

    <div class="calculator">
        <input type="text" id="display" disabled>
        <div class="buttons">
            <button onclick="clearDisplay()">C</button>
            <button onclick="appendToDisplay('7')">7</button>
            <button onclick="appendToDisplay('8')">8</button>
            <button onclick="appendToDisplay('9')">9</button>
            <button onclick="appendToDisplay('/')">/</button>
            <button onclick="appendToDisplay('4')">4</button>
            <button onclick="appendToDisplay('5')">5</button>
            <button onclick="appendToDisplay('6')">6</button>
            <button onclick="appendToDisplay('*')">*</button>
            <button onclick="appendToDisplay('1')">1</button>
            <button onclick="appendToDisplay('2')">2</button>
            <button onclick="appendToDisplay('3')">3</button>
            <button onclick="appendToDisplay('-')">-</button>
            <button onclick="appendToDisplay('0')">0</button>
            <button onclick="appendToDisplay('.')">.</button>
            <button onclick="calculateResult()">=</button>
            <button onclick="appendToDisplay('+')">+</button>
            <button onclick="appendToDisplay('Math.sin(')">sin</button>
            <button onclick="appendToDisplay('Math.cos(')">cos</button>
            <button onclick="appendToDisplay('Math.tan(')">tan</button>
            <button onclick="appendToDisplay('Math.sqrt(')">√</button>
            <button onclick="appendToDisplay('Math.pow(')">x²</button>
            <button onclick="appendToDisplay('(')">(</button>
            <button onclick="appendToDisplay(')')">)</button>
        </div>
    </div>
    <script src="script.js"></script>
</body>
  <script>
    function appendToDisplay(value) {
    document.getElementById('display').value += value;
}

function clearDisplay() {
    document.getElementById('display').value = '';
}

function calculateResult() {
    const display = document.getElementById('display');
    try {
        // Evaluate the expression
        display.value = eval(display.value);
    } catch (error) {
        display.value = 'Error';
    }
}
  </script>
