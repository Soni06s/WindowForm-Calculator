# 🧮 Windows Forms Calculator

A modern, fully-featured **Windows Forms Calculator** built with **C# (.NET Framework 4.8)**, inspired by the clean design of the Windows 11 built-in calculator.

![Calculator Screenshot](screenshot.png)

---

## ✨ Features

| Category | Features |
|---|---|
| **Basic Operations** | Addition `+`, Subtraction `−`, Multiplication `×`, Division `÷` |
| **Advanced Functions** | Square root `√x`, Square `x²`, Reciprocal `1/x`, Percentage `%` |
| **Input Controls** | Clear `C`, Clear Entry `CE`, Backspace `⌫`, Toggle Sign `+/-` |
| **Chaining** | Chain multiple operations without pressing `=` |
| **Expression Bar** | Shows the current expression above the main display |
| **Keyboard Support** | Full keyboard input (numbers, operators, Enter, Escape, Delete, Backspace) |
| **Responsive Font** | Display font shrinks automatically for long numbers |
| **Dark Theme** | Sleek dark UI with colour-coded button categories |

---

## 🚀 Getting Started

### Prerequisites

- **Windows** OS (Windows 7 or later)
- **Visual Studio 2019 / 2022** (Community edition is free)
- **.NET Framework 4.8** (pre-installed on Windows 10/11)

### Clone & Run

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/WindowsFormCalculator.git

# 2. Open the solution
cd WindowsFormCalculator
start WindowsFormCalculator.sln
```

Then press **F5** in Visual Studio to build and run.

### Build from CLI (MSBuild)

```bash
# Restore & build in Release mode
msbuild WindowsFormCalculator.sln /p:Configuration=Release
```

The compiled executable will be at:
```
WindowsFormCalculator\bin\Release\WindowsFormCalculator.exe
```

---

## ⌨️ Keyboard Shortcuts

| Key | Action |
|---|---|
| `0`–`9` | Digit input |
| `.` | Decimal point |
| `+` `-` `*` `/` | Operators |
| `Enter` / `=` | Calculate result |
| `Backspace` | Delete last digit |
| `Escape` | Clear all (C) |
| `Delete` | Clear entry (CE) |

---

## 🗂️ Project Structure

```
WindowsFormCalculator/
├── WindowsFormCalculator.sln          # Visual Studio solution
└── WindowsFormCalculator/
    ├── Program.cs                     # Application entry point
    ├── Form1.cs                       # Calculator logic & event handlers
    ├── Form1.Designer.cs              # Auto-generated UI layout code
    ├── WindowsFormCalculator.csproj   # Project file (.NET Framework 4.8)
    └── Properties/
        └── AssemblyInfo.cs            # Assembly metadata
```

---

## 🏗️ Architecture

The project follows a clean **Designer + Code-Behind** pattern:

- **`Form1.Designer.cs`** — UI layout: all controls, colours, sizes, and positions are defined programmatically via a reusable `ConfigureButton()` helper.
- **`Form1.cs`** — Business logic: calculator state machine, chaining, error handling, keyboard routing.

### Calculator State Machine

```
[Idle / New Entry]
     │  digit pressed
     ▼
[Entering Number]
     │  operator pressed         ← stores firstOperand
     ▼
[Waiting for Second Number]
     │  digit pressed
     ▼
[Entering Second Number]
     │  = pressed                ← stores secondOperand, shows result
     ▼
[Result Displayed]  ──► operator pressed ──► chain next calculation
```

---

## 🎨 UI Design

Button colours follow a consistent palette:

| Button Type | Background | Foreground |
|---|---|---|
| Number (`0`–`9`, `.`, `+/-`) | `#323232` | White |
| Operator (`+` `−` `×` `÷`) | `#2D2D32` | Light Blue `#78B4FF` |
| Equals (`=`) | `#0067C0` | White |
| Special (`C` `CE` `⌫` `%` `√x` `x²` `1/x`) | `#282828` | `#C8C8C8` |

---

## 📋 Requirements

- Windows OS
- .NET Framework 4.8 Runtime
- Visual Studio 2019+ (for development)

---

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/my-feature`
3. Commit your changes: `git commit -m "Add my feature"`
4. Push to the branch: `git push origin feature/my-feature`
5. Open a Pull Request

---

## 📄 License

This project is licensed under the **MIT License** — see [LICENSE](LICENSE) for details.

---

## 🙏 Acknowledgements

- Inspired by the **Windows 11 Calculator** UI/UX
- Built with **C# Windows Forms** (.NET Framework 4.8)
