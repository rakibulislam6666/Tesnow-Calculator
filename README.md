# 🧮 Calculator

A modern, lightweight and reliable Android Calculator application designed for fast, accurate and user-friendly calculations.

The project focuses on a clean interface, safe mathematical expression handling, accurate decimal calculations, and a smooth Android experience.

---

## ✨ Features

### 🔢 Core Calculations

- Addition "+"
- Subtraction "−"
- Multiplication "×"
- Division "÷"
- Decimal calculations
- Negative numbers
- Percentage calculations
- Operator precedence
- Parentheses support
- Long mathematical expressions
- Accurate decimal calculation using "BigDecimal"

### 📐 Smart Expression Handling

The calculator is designed to process complete mathematical expressions rather than simply calculating two numbers at a time.

**Example:**
```
10 + 5 × 2
```

**Result:**
```
20
```

The expression engine follows mathematical operator precedence to produce the correct result.

### 🔍 Expression Display

The calculator can display the mathematical expression while calculating, making it easier to understand what has been entered.

**Example:**
```
1250 ÷ 5 + 20
```

**Result:**
```
270
```

### 💰 Thousands Separator

Large numbers can be displayed with thousands separators for better readability.

**Example:**
```
1000000
```

becomes:
```
1,000,000
```

This makes large calculations easier to read.

### 🎯 Accurate Decimal Mathematics

The calculation engine uses Java's `BigDecimal` instead of relying only on floating-point arithmetic.

This helps avoid common floating-point precision problems. For example, calculations involving decimal values can be handled more reliably.

---

## 🏗️ Project Architecture

The application is separated into different responsibilities so that the calculation logic can remain independent from the user interface.

```
Calculator App
│
├── User Interface
│   ├── Number Buttons
│   ├── Operator Buttons
│   ├── Display
│   └── Result Display
│
├── Expression Handling
│   ├── Tokenization
│   ├── Operator Detection
│   ├── Parentheses
│   └── Expression Validation
│
├── Calculation Engine
│   ├── Addition
│   ├── Subtraction
│   ├── Multiplication
│   ├── Division
│   └── Percentage
│
└── Number Formatting
    ├── Decimal Formatting
    └── Thousands Separation
```

---

## ⚙️ Calculation Engine

The calculator uses a safe recursive-descent style expression parser to process mathematical expressions.

The parser handles different levels of mathematical operations.

Conceptually:

```
Expression
   ↓
Term
   ↓
Factor
   ↓
Number / Parentheses
```

This allows expressions such as `2 + 3 × 4` to be evaluated according to mathematical precedence.

Instead of simply evaluating the expression as raw code, the application processes the expression through its own calculation logic.

---

## 🛡️ Safe Calculation

The calculator does not need to execute arbitrary JavaScript or external code to perform calculations.

Expressions are interpreted by the application's own calculation engine.

This provides better control over:

- Invalid input
- Mathematical errors
- Division by zero
- Decimal precision
- Operator handling
- Expression validation

---

## 📱 User Interface

The UI is designed around simplicity and quick access.

Typical layout:

```
┌───────────��──────────────┐
│      Expression          │
│                          │
│          1250            │
├──────────────────────────┤
│  AC    ( )    %     ÷    │
│   7     8     9     ×    │
│   4     5     6     −    │
│   1     2     3     +    │
│   0     .     =          │
└──────────────────────────┘
```

The interface is designed to keep the most frequently used operations easily accessible.

---

## 🧠 Error Handling

The calculator is designed to prevent invalid calculations from crashing the application.

Examples of situations that can be handled:

- Division by zero
- Empty expression
- Invalid operator sequence
- Invalid decimal input
- Incomplete expression
- Invalid parentheses
- Calculation overflow/error conditions

Instead of crashing, the application can show an appropriate error state.

---

## 🧮 Example Calculations

### Basic
```
25 + 15 = 40
```

### Multiplication
```
12 × 8 = 96
```

### Operator Precedence
```
10 + 5 × 2 = 20
```

### Parentheses
```
(10 + 5) × 2 = 30
```

### Decimal
```
10.5 × 2 = 21.0
```

### Large Number
```
1000000 + 250000 = 1,250,000
```

---

## 🛠️ Technologies

The project is built for Android using:

- Java
- Android SDK
- Gradle
- Android Build Tools
- BigDecimal
- Custom mathematical expression parser

The project is designed to remain lightweight and does not require an internet connection for normal calculator operations.

---

## 📦 Requirements

To build the application, you need:

- Android development environment
- Java/JDK compatible with the project
- Android SDK
- Android Build Tools
- Gradle/Gradle Wrapper
- Android device or emulator

---

## 🚀 Build

Clone the project:

```bash
git clone https://github.com/rakibulislam6666/Tesnow-Calculator.git
```

Enter the project directory:

```bash
cd Tesnow-Calculator
```

Build the debug APK:

```bash
./gradlew assembleDebug
```

The generated APK can normally be found under:

```
app/build/outputs/apk/debug/
```

---

## 📲 Installation

After building the APK, install it on an Android device.

For example:

```bash
adb install app-debug.apk
```

Or transfer the APK to an Android phone and install it manually.

---

## 🔐 Release Signing

For publishing the application, a release keystore should be used.

Example configuration:

```
Keystore
   ↓
Signing Key
   ↓
Release Build
   ↓
Signed APK / App Bundle
   ↓
Google Play
```

The keystore and passwords should never be committed to GitHub.

Add sensitive files to `.gitignore`:

```
*.keystore
*.jks
keystore.properties
```

---

## 📁 Suggested Project Structure

```
Tesnow-Calculator/
│
├── app/
│   ├── src/
│   │   └── main/
│   │       ├── java/
│   │       │   └── com/
│   │       │       └── tesnow/
│   │       │           └── calculator/
│   │       │               ├── MainActivity.java
│   │       │               ├── CalculatorEngine.java
│   │       │               ├── ExpressionParser.java
│   │       │               └── ...
│   │       │
│   │       └── res/
│   │           ├── drawable/
│   │           ├── layout/
│   │           ├── mipmap/
│   │           └── values/
│   │
│   ├── build.gradle
│   └── proguard-rules.pro
│
├── build.gradle
├── settings.gradle
├── gradle.properties
└── README.md
```

---

## 🎨 Design Philosophy

The application follows a simple design philosophy:

> **Fast. Accurate. Simple. Reliable.**

The goal is not to overload the calculator with unnecessary features.

Instead, the focus is on:

- Easy input
- Clear results
- Accurate calculations
- Fast response
- Clean interface
- Reliable error handling

---

## 🔮 Future Development

The project can be expanded with many professional features.

### 📜 Calculation History

Store previous calculations:

```
25 × 5 = 125
100 ÷ 4 = 25
125 + 50 = 175
```

Users could view, reuse or delete previous calculations.

### 🌓 Dark Mode

Add:
- Light Mode
- Dark Mode
- System Default

### 📐 Scientific Calculator

Future versions could support:
- sin(), cos(), tan()
- log(), ln()
- √, x², xʸ
- π, e

### 🔢 Advanced Operations

Possible additions:
- Square root
- Power
- Factorial
- Modulo
- Reciprocal
- Absolute value

### 📋 Copy Result

Allow users to copy the result directly to the clipboard.

### ↩️ Undo / Redo

Users could undo accidental input and restore previous expressions.

### 📳 Haptic Feedback

Optional vibration feedback when pressing calculator buttons.

### 🎨 Custom Themes

Future versions could provide customizable:
- Button styles
- Accent colors
- Backgrounds
- Display styles

### 🌍 Localization

Support multiple languages, including:
- English
- বাংলা (Bengali)
- Hindi
- Arabic
- Other languages

### 📊 Calculation History Export

Future versions could allow users to export calculation history as:
- TXT
- CSV
- PDF

---

## 🔒 Privacy

The calculator is designed to perform calculations locally on the device.

- No account is required for basic calculator functionality
- No internet connection is required for normal calculations
- All calculations are processed on-device
- No personal data is collected or stored

If future versions introduce analytics, cloud synchronization or online services, the privacy policy should be updated accordingly.

---

## 🤝 Contributing

Contributions are welcome!

If you want to improve the project:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test the application thoroughly
5. Submit a Pull Request with a clear description

Example:

```bash
git checkout -b feature/scientific-calculator
```

---

## 🐛 Bug Reports

If you find a problem, please report:

- Device model
- Android version
- App version
- Input expression
- Expected result
- Actual result
- Screenshot, if possible

This makes debugging much easier.

---

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

## ⭐ Project Goal

This project aims to become a lightweight but powerful Android calculator that combines:

```
Simple UI
    +
Accurate Mathematics
    +
Safe Expression Parsing
    +
Reliable Error Handling
    +
Professional Android Design
```

---

## 📌 Roadmap

- [x] Basic arithmetic operations
- [x] Decimal calculations
- [x] Expression evaluation
- [x] Operator precedence
- [x] BigDecimal-based calculation
- [x] Thousands separator
- [x] Expression display
- [x] Error handling
- [ ] Calculation history
- [ ] Dark mode
- [ ] Scientific calculator
- [ ] Custom themes
- [ ] Haptic feedback
- [ ] Multiple languages
- [ ] Advanced mathematical functions
- [ ] Google Play Store release

---

## 👨‍💻 Developer

**Tesnow Calculator**

Built with Java and Android technologies by **MD. RAKIBUL ISLAM**

GitHub: [@rakibulislam6666](https://github.com/rakibulislam6666)

---

## ⭐ Support

If you find this project useful, consider giving the repository a ⭐ on GitHub.

Thank you for checking out the project!

---

**Made with ❤️ for better calculations**
