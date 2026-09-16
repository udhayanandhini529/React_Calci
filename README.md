# Ex04 Simple Calculator - React Project
## Date:14-03-2026
## Name : UDHAYA NANDHINI M
## Reg No : 212225240177

## AIM
To  develop a Simple Calculator using React.js with clean and responsive design, ensuring a smooth user experience across different screen sizes.

## ALGORITHM
### STEP 1
Create a React App.

### STEP 2
Open a terminal and run:
  <ul><li>npx create-react-app simple-calculator</li>
  <li>cd simple-calculator</li>
  <li>npm start</li></ul>

### STEP 3
Inside the src/ folder, create a new file Calculator.js and define the basic structure.

### STEP 4
Plan the UI: Display screen, number buttons (0-9), operators (+, -, *, /), clear (C), and equal (=).

### STEP 5
Create a new file Calculator.css in src/ and add the styling.

### STEP 6
Open src/App.js and modify it.

### STEP 7
Start the development server.
  npm start

### STEP 8
Open http://localhost:3000/ in the browser.

### STEP 9
Test the calculator by entering numbers and operations.

### STEP 10
Fix styling issues and refine content placement.

### STEP 11
Deploy the website.

### STEP 12
Upload to GitHub Pages for free hosting.

## PROGRAM
app.css:
```
.calculator-container {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 80vh;
  background-color: #f4f4f9;
}

.calculator {
  background: #222;
  padding: 20px;
  border-radius: 12px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
  width: 280px;
}

.display {
  background: #111;
  color: #fff;
  font-size: 2rem;
  padding: 15px;
  text-align: right;
  border-radius: 6px;
  margin-bottom: 15px;
  min-height: 40px;
  word-wrap: break-word;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}

button {
  padding: 15px;
  font-size: 1.2rem;
  font-weight: bold;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  background: #444;
  color: white;
}

button:hover {
  background: #555;
}

.btn-op { background: #f39c12; }
.btn-op:hover { background: #e67e22; }

.btn-action { background: #e74c3c; }
.btn-action:hover { background: #c0392b; }

.btn-equal {
  background: #2ecc71;
  grid-row: span 2;
  height: 100%;
}
.btn-equal:hover { background: #27ae60; }

.btn-zero {
  grid-column: span 2;
}

```


app.js:
```
import React from 'react';
import Calculator from './Calculator';

function App() {
  return (
    <div className="App">
      <Calculator />
    </div>
  );
}

export default App;

```


calculator.js:
```

import React, { useState } from 'react';
import './Calculator.css';

function Calculator() {
  const [input, setInput] = useState('');

  const handleClick = (value) => {
    setInput((prev) => prev + value);
  };

  const handleClear = () => {
    setInput('');
  };

  const handleCalculate = () => {
    try {
      setInput(Function(`'use strict'; return (${input})`)().toString());
    } catch {
      setInput('Error');
    }
  };

  return (
    <div className="calculator-container">
      <div className="calculator">
        <div className="display">{input || '0'}</div>
        <div className="buttons">
          <button onClick={handleClear} className="btn-action">C</button>
          <button onClick={() => handleClick('/')} className="btn-op">÷</button>
          <button onClick={() => handleClick('*')} className="btn-op">×</button>
          <button onClick={() => handleClick('-')} className="btn-op">-</button>

          <button onClick={() => handleClick('7')}>7</button>
          <button onClick={() => handleClick('8')}>8</button>
          <button onClick={() => handleClick('9')}>9</button>
          <button onClick={() => handleClick('+')} className="btn-op">+</button>

          <button onClick={() => handleClick('4')}>4</button>
          <button onClick={() => handleClick('5')}>5</button>
          <button onClick={() => handleClick('6')}>6</button>
          <button onClick={handleCalculate} className="btn-equal">=</button>

          <button onClick={() => handleClick('1')}>1</button>
          <button onClick={() => handleClick('2')}>2</button>
          <button onClick={() => handleClick('3')}>3</button>
          <button onClick={() => handleClick('0')} className="btn-zero">0</button>
          <button onClick={() => handleClick('.')}>.</button>
        </div>
      </div>
    </div>
  );
}

export default Calculator;
```

## OUTPUT
![alt text](<Screenshot 2026-09-16 120019.png>)
## RESULT
The program for developing a simple calculator in React.js is executed successfully.
