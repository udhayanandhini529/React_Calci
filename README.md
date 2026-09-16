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
app.jsx:
```
import React, { useState } from "react";
import "./App.css";

function App() {
  const [input, setInput] = useState("");

  const handleClick = (value) => {
    setInput((prev) => prev + value);
  };

  const clearDisplay = () => {
    setInput("");
  };

  const deleteLast = () => {
    setInput((prev) => prev.slice(0, -1));
  };

  const calculate = () => {
    try {
      setInput(eval(input).toString());
    } catch {
      setInput("Error");
    }
  };

  const buttons = [
    "7", "8", "9", "/",
    "4", "5", "6", "*",
    "1", "2", "3", "-",
    "0", ".", "=", "+"
  ];

  return (
    <div className="container">
      <div className="calculator">
        <h1>Calculator</h1>

        <div className="display">
          {input || "0"}
        </div>

        <div className="top-buttons">
          <button className="special" onClick={clearDisplay}>
            AC
          </button>

          <button className="special" onClick={deleteLast}>
            DEL
          </button>
        </div>

        <div className="buttons">
          {buttons.map((btn) => (
            <button
              key={btn}
              className={btn === "=" ? "equal" : ""}
              onClick={() =>
                btn === "=" ? calculate() : handleClick(btn)
              }
            >
              {btn}
            </button>
          ))}
        </div>
      </div>
    </div>
  );
}

export default App;
```
app.css:
```
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Poppins", sans-serif;
}

body {
  min-height: 100vh;
  background: linear-gradient(
    135deg,
    #0f172a,
    #1e293b,
    #334155
  );
}

.container {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  padding: 20px;
}

.calculator {
  width: 380px;
  padding: 25px;
  border-radius: 25px;

  background: rgba(255, 255, 255, 0.08);
  backdrop-filter: blur(18px);

  box-shadow:
    0 8px 32px rgba(0, 0, 0, 0.4),
    inset 0 0 10px rgba(255,255,255,0.05);

  border: 1px solid rgba(255,255,255,0.1);
}

.calculator h1 {
  text-align: center;
  color: white;
  margin-bottom: 20px;
  font-weight: 600;
}

.display {
  height: 90px;
  background: rgba(255,255,255,0.08);
  color: white;
  border-radius: 15px;
  margin-bottom: 20px;

  display: flex;
  align-items: center;
  justify-content: flex-end;

  padding: 20px;
  font-size: 2rem;
  overflow-x: auto;
}

.top-buttons {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;
  margin-bottom: 12px;
}

.special {
  background: #ef4444;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 12px;
}

button {
  height: 65px;
  border: none;
  border-radius: 15px;
  font-size: 1.2rem;
  color: white;

  background: rgba(255,255,255,0.1);
  backdrop-filter: blur(5px);

  cursor: pointer;
  transition: all 0.2s ease;
}

button:hover {
  transform: translateY(-3px);
  background: rgba(255,255,255,0.18);
}

button:active {
  transform: scale(0.95);
}

.equal {
  background: #22c55e;
  font-weight: bold;
}

.equal:hover {
  background: #16a34a;
}

@media (max-width: 450px) {
  .calculator {
    width: 100%;
  }

  button {
    height: 55px;
  }

  .display {
    font-size: 1.6rem;
  }
}
```
main.jsx:
```
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App";
import "./App.css";

ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
```
## OUTPUT
<img width="1002" height="628" alt="image" src="https://github.com/user-attachments/assets/e799cedf-7229-48ce-b480-3d59c255823f" />
## RESULT
The program for developing a simple calculator in React.js is executed successfully.
