# 🧮 Calculator Program

A fully functional Calculator built with HTML, CSS, and JavaScript. Perform basic arithmetic operations with a clean, intuitive interface!

## 📸 Preview

![Calculator Demo](https://github.com/user-attachments/assets/8810db4e-1346-4834-bad3-41238836083f)
> 

## ✨ Features

- ➕ **Addition** - Add numbers together
- ➖ **Subtraction** - Subtract numbers
- ✖️ **Multiplication** - Multiply numbers
- ➗ **Division** - Divide numbers (with zero-division handling)
- 🔢 **Decimal Support** - Work with decimal numbers
- 🧹 **Clear (C)** - Clear all input and start fresh
- ⌫ **Delete (DEL)** - Remove last digit
- 📱 **Responsive Design** - Works on all devices

## 🛠️ Built With

- **HTML5** - Structure and layout
- **CSS3** - Styling and button design
- **JavaScript** - Calculator logic and operations

## 📂 Project Structure

```
calculator/
│
├── index.html          # Main HTML file
├── style.css           # Styling
├── script.js           # Calculator logic
└── README.md           # Project documentation
```

## 💻 How It Works

### Calculator Logic
```javascript
let currentInput = '';
let previousInput = '';
let operation = null;

function appendNumber(number) {
    if (number === '.' && currentInput.includes('.')) return;
    currentInput += number;
    updateDisplay();
}

function chooseOperation(op) {
    if (currentInput === '') return;
    if (previousInput !== '') {
        calculate();
    }
    operation = op;
    previousInput = currentInput;
    currentInput = '';
}

function calculate() {
    let result;
    const prev = parseFloat(previousInput);
    const current = parseFloat(currentInput);
    
    if (isNaN(prev) || isNaN(current)) return;
    
    switch (operation) {
        case '+':
            result = prev + current;
            break;
        case '-':
            result = prev - current;
            break;
        case '×':
            result = prev * current;
            break;
        case '÷':
            if (current === 0) {
                alert("Cannot divide by zero!");
                clearAll();
                return;
            }
            result = prev / current;
            break;
        default:
            return;
    }
    
    currentInput = result.toString();
    operation = null;
    previousInput = '';
    updateDisplay();
}

function clearAll() {
    currentInput = '';
    previousInput = '';
    operation = null;
    updateDisplay();
}

function deleteLast() {
    currentInput = currentInput.slice(0, -1);
    updateDisplay();
}

function updateDisplay() {
    display.value = currentInput || '0';
}
```

### Key JavaScript Concepts

- **Variables** - Store current input, previous input, and operation
- **parseFloat()** - Convert strings to numbers for calculations
- **Switch statement** - Handle different operations
- **String methods** - `.includes()`, `.slice()` for input manipulation
- **Error handling** - Prevent division by zero

## 🎯 Getting Started

### Prerequisites
- A web browser (Chrome, Firefox, Safari, etc.)
- A code editor (VS Code, Sublime Text, etc.)

### Installation

1. Clone the repository
```bash
git clone https://github.com/YOUR_USERNAME/calculator.git
```

2. Navigate to the project directory
```bash
cd calculator
```

3. Open `index.html` in your browser
```bash
# On Windows
start index.html

# On Mac
open index.html

# On Linux
xdg-open index.html
```

Or simply drag and drop the `index.html` file into your browser!

## 🎮 How to Use

### Basic Operations

1. **Addition**: Enter first number → Click `+` → Enter second number → Click `=`
2. **Subtraction**: Enter first number → Click `-` → Enter second number → Click `=`
3. **Multiplication**: Enter first number → Click `×` → Enter second number → Click `=`
4. **Division**: Enter first number → Click `÷` → Enter second number → Click `=`

### Special Functions

- **C (Clear)**: Clears everything and resets the calculator
- **DEL (Delete)**: Removes the last digit entered
- **. (Decimal)**: Adds decimal point (only one per number)
- **= (Equals)**: Performs the calculation and shows result

### Button Layout
```
┌─────────────────────┐
│     Display         │
├─────┬─────┬─────┬───┤
│  C  │ DEL │  ÷  │   │
├─────┼─────┼─────┼───┤
│  7  │  8  │  9  │ × │
├─────┼─────┼─────┼───┤
│  4  │  5  │  6  │ - │
├─────┼─────┼─────┼───┤
│  1  │  2  │  3  │ + │
├─────┼─────┼─────┼───┤
│  .  │  0  │  =  │   │
└─────┴─────┴─────┴───┘
```

## 🎨 Customization

Personalize your calculator:
- **Color schemes** - Change button and display colors
- **Button styles** - Rounded corners, shadows, hover effects
- **Fonts** - Try calculator-style fonts or modern sans-serif
- **Display** - Add right alignment, better formatting
- **Animations** - Button press animations
- **Layout** - Adjust button sizes and spacing

### CSS Styling Ideas
```css
/* Modern gradient buttons */
button {
    background: linear-gradient(145deg, #6e6e6e, #2d2d2d);
    box-shadow: 5px 5px 10px #1a1a1a, -5px -5px 10px #404040;
}

/* Digital display style */
.display {
    font-family: 'Orbitron', monospace;
    background: #1e1e1e;
    color: #00ff00;
    text-align: right;
}
```

## 📚 What I Learned

This project helped me understand:
- ✅ Event handling for multiple buttons
- ✅ State management (storing current and previous values)
- ✅ Switch statements for handling operations
- ✅ String and number conversion
- ✅ Error handling (division by zero)
- ✅ DOM manipulation and display updates
- ✅ Working with decimal numbers
- ✅ User input validation

## 🧮 Operation Examples

```javascript
// Addition
5 + 3 = 8

// Subtraction
10 - 4 = 6

// Multiplication
6 × 7 = 42

// Division
20 ÷ 4 = 5

// Decimals
3.14 + 2.86 = 6

// Chained operations
5 + 3 = 8, then × 2 = 16
```

## 🔮 Future Enhancements

Ideas to level up your calculator:
- ⌨️ **Keyboard Support** - Use number keys and operators
- 📊 **Scientific Mode** - Add sin, cos, tan, square root, power
- 🧮 **Memory Functions** - M+, M-, MR, MC
- 📜 **History** - Show calculation history
- 🎨 **Themes** - Dark mode, light mode, custom colors
- 🔢 **Different Number Systems** - Binary, hexadecimal, octal
- 📐 **Advanced Operations** - Percentage, square, cube
- ↩️ **Undo Function** - Undo last operation
- 📋 **Copy Result** - Copy answer to clipboard
- 🎤 **Voice Input** - Speak calculations
- 📱 **PWA** - Install as mobile app
- 💾 **Save Sessions** - Remember last calculation
- 🌐 **Unit Converter** - Built-in conversion tools

## 🔢 Advanced Features Ideas

### Percentage Calculation
```javascript
function calculatePercentage() {
    currentInput = (parseFloat(currentInput) / 100).toString();
    updateDisplay();
}
```

### Square/Power Functions
```javascript
function square() {
    currentInput = (parseFloat(currentInput) ** 2).toString();
    updateDisplay();
}
```

### Memory Functions
```javascript
let memory = 0;

function memoryAdd() {
    memory += parseFloat(currentInput);
}

function memoryRecall() {
    currentInput = memory.toString();
    updateDisplay();
}
```

## 🎯 Use Cases

Perfect for:
- 📚 Quick math calculations
- 🏪 Shopping and budgeting
- 💰 Financial calculations
- 📊 Data analysis
- 🎓 Learning JavaScript basics
- 🏗️ Foundation for advanced calculator apps

## 🐛 Error Handling

The calculator handles common errors:
- **Division by Zero**: Shows alert and resets
- **Multiple Decimals**: Prevents adding more than one decimal point
- **Invalid Operations**: Checks for valid inputs before calculating
- **Display Overflow**: Can be limited to prevent UI breaking

## 🤝 Contributing

Contributions are welcome! Feel free to:
1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 👨‍💻 Author

**Partha Biswas**

- GitHub: [@Parttha06](https://github.com/Parttha06)
- LinkedIn: [Partha Biswas](https://www.linkedin.com/in/partha-biswass)

## 🙏 Acknowledgments

- Inspired by classic calculator design
- Built as part of my JavaScript learning journey
- Perfect for practicing DOM manipulation and event handling

## ⭐ Show Your Support

Give a ⭐️ if this calculator helped you crunch some numbers!

---

<div align="center">
Made with ❤️ and mathematical precision by Partha Biswas

🧮 Calculate with confidence! 🧮
</div>
