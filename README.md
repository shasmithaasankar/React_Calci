# Ex04 Simple Calculator - React Project
## Date:05-06-2026
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
# SimpleCalculator.jsx
```
import React, { useState } from "react";
import "./Calculator.css";

export default function SimpleCalculator() {
  const [input, setInput] = useState("");

  const handleClick = (value) => {
    setInput(input + value);
  };

  const handleClear = () => {
    setInput("");
  };

  const handleBackspace = () => {
    setInput(input.slice(0, -1));
  };

  const handleCalculate = () => {
    try {
      const expression = input.replace(/×/g, "*").replace(/÷/g, "/");
      const result = eval(expression);
      setInput(result.toString());
    } catch {
      setInput("Error");
    }
  };

  return (
    <div className="calculator-container">
      <h2 className="title">Simple Calculator</h2>
      <input
        type="text"
        value={input}
        readOnly
        className="display"
      />

      <div className="button-grid">
        {[7, 8, 9, "÷", 4, 5, 6, "×", 1, 2, 3, "-", 0, ".", "=", "+"].map(
          (btn) => (
            <button
              key={btn}
              onClick={() => {
                if (btn === "=") handleCalculate();
                else handleClick(btn.toString());
              }}
              className={btn === "=" ? "button equal" : "button"}
            >
              {btn}
            </button>
          )
        )}

        <button onClick={handleBackspace} className="button span-two">
          ⌫
        </button>
        <button onClick={handleClear} className="button span-two clear">
          C
        </button>
      </div>
    </div>
  );
}
````
# Calculator.css
```
body{
  background-color: rgb(73, 118, 208);
}
.calculator-container {
  max-width: 320px;
  margin: 50px auto;
  padding: 20px;
  background: #85b5e5;
  border-radius: 12px;
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
  text-align: center;
}

.title {
  margin-bottom: 15px;
  font-family: Arial, sans-serif;
  color: #333;
}

.display {
  width: 100%;
  height: 50px;
  margin-bottom: 15px;
  font-size: 20px;
  text-align: right;
  padding: 8px;
  border-radius: 6px;
  border: 1px solid #ccc;
  background: #fff;
}

.button-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}

.button {
  padding: 15px;
  font-size: 18px;
  border: none;
  border-radius: 8px;
  background: #e9ecef;
  cursor: pointer;
  transition: 0.2s;
}

.button:hover {
  background: #dee2e6;
}

.equal {
  background: #4cafef;
  color: white;
  grid-column: span 1;
}

.equal:hover {
  background: #3a9fd6;
}

.clear {
  background: #ff6b6b;
  color: white;
}

.clear:hover {
  background: #e55a5a;
}

.span-two {
  grid-column: span 2;
}
```
# App.jsx
```
import SimpleCalculator from "./SimpleCalculator.jsx"
function App(){
  
  return(
    <>
  <SimpleCalculator/>
    </>
  )
}
export default App;

```
## OUTPUT
<img width="1915" height="904" alt="image" src="https://github.com/user-attachments/assets/4eb1784c-8366-4261-92fe-6b6c375185bb" />

<img width="1919" height="890" alt="image" src="https://github.com/user-attachments/assets/82746ed9-db62-4f9e-970b-f350b5784acd" />

<img width="1914" height="901" alt="image" src="https://github.com/user-attachments/assets/9cc60216-be2d-41ed-9cc0-6ec1367df098" />

## RESULT
The program for developing a simple calculator in React.js is executed successfully.
