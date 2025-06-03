# Ex04 Simple Calculator - React Project
## Date:

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
APP.JS
```
import React, { useState } from 'react';
import './App.css';

const App = () => {
  const [input, setInput] = useState('');
  const [result, setResult] = useState('');

  const handleClick = (value) => {
    if (value === '=') {
      try {
        setResult(eval(input).toString());
      } catch (error) {
        setResult('Error');
      }
    } else if (value === 'C') {
      setInput('');
      setResult('');
    } else if (value === '⌫') {
      setInput(input.slice(0, -1));
    } else {
      setInput(input + value);
    }
  };

  const buttons = [
    '7', '8', '9', '/',
    '4', '5', '6', '*',
    '1', '2', '3', '-',
    '0', '.', '=', '+',
    'C', '⌫'
  ];

  return (
    <div className="calculator-container">
      <div className="calculator">
        <div className="display">
          <div className="input">{input}</div>
          <div className="result">{result}</div>
        </div>
        <div className="buttons">
          {buttons.map((btn) => (
            <button
              key={btn}
              onClick={() => handleClick(btn)}
              className={`button ${btn === '=' ? 'equals' : ''} ${btn === 'C' ? 'clear' : ''}`}
            >
              {btn}
            </button>
          ))}
        </div>
        <div className="footer">
          <p>© {new Date().getFullYear()} Vanisha-212222040174</p>
        </div>
      </div>
    </div>
  );
};

export default App;
```
APP.CSS
```
.calculator-container {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background-color: #f0f0f0;
  padding: 20px;
}

.calculator {
  width: 100%;
  max-width: 400px; /* Increased from 320px */
  border: 4px solid #000;
  border-radius: 0;
  box-shadow: 8px 8px 0 #000;
  background-color: #fff;
  padding: 25px;
  box-sizing: border-box;
}

.display {
  border: 3px solid #000;
  margin-bottom: 25px;
  padding: 15px;
  background-color: #f8f8f8;
  text-align: right;
  min-height: 80px;
}

.input {
  font-size: 1.5rem; /* Increased from 1.2rem */
  min-height: 30px; /* Increased from 24px */
  color: #555;
}

.result {
  font-size: 2.2rem; /* Increased from 1.8rem */
  font-weight: bold;
  min-height: 40px; /* Increased from 32px */
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 15px; /* Increased from 10px */
}

.button {
  border: 3px solid #000;
  background-color: #fff;
  color: #000;
  font-size: 1.5rem; /* Increased from 1.2rem */
  font-weight: bold;
  padding: 20px 0; /* Increased from 15px */
  cursor: pointer;
  transition: all 0.2s;
  border-radius: 0;
}

.button:hover {
  background-color: #000;
  color: #fff;
  transform: translate(-2px, -2px);
  box-shadow: 4px 4px 0 #000;
}

.button:active {
  transform: translate(0, 0);
  box-shadow: none;
}

.equals {
  background-color: #ff6b6b;
  grid-column: span 1;
}

.clear {
  background-color: #4ecdc4;
  grid-column: span 2;
}

.footer {
  margin-top: 20px;
  text-align: center;
  font-size: 1.5rem;
  color: #666;
  border-top: 2px solid #000;
  padding-top: 10px;
}

@media (max-width: 500px) {
  .calculator {
    max-width: 350px;
    padding: 20px;
  }
  
  .button {
    padding: 18px 0;
    font-size: 1.3rem;
  }
}
```

## OUTPUT
![image](https://github.com/user-attachments/assets/dc299eaa-a068-42bd-bc41-37e173b737f7)
![image](https://github.com/user-attachments/assets/7958a5b8-2320-4632-b4b0-ee30b64a3196)
![image](https://github.com/user-attachments/assets/56eaddee-f5a0-49e8-9576-b10cd11c31cf)




## RESULT
The program for developing a simple calculator in React.js is executed successfully.
