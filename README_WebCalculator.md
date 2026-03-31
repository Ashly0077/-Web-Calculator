# Calculator

> A clean, keyboard-driven web calculator with memory, history, and copy support.

![HTML](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)

---

## Overview

A fully client-side calculator built without any frameworks or dependencies. The focus was on writing clean, modular JavaScript with a state-driven architecture — treating it less like a "calculator widget" and more like a small interactive application with proper separation between state, logic, and rendering.

---

## Features

- **Full arithmetic** — addition, subtraction, multiplication, division
- **Operator chaining** — chain calculations without pressing `=` first
- **Memory system** — `M+`, `MR`, `MC` with on-screen indicator
- **Copy to clipboard** — one-click copy with visual confirmation
- **Calculation history** — last 30 results, click any to reuse
- **Keyboard support** — full numpad + operators, with visual key feedback
- **Error handling** — divide-by-zero, edge cases handled gracefully
- **Zero dependencies** — pure HTML, CSS, JavaScript

---

## Tech Stack

| Layer      | Technology               |
|------------|--------------------------|
| Markup     | HTML5 (semantic)         |
| Styling    | CSS3 (custom properties, grid, transitions) |
| Logic      | Vanilla JavaScript (ES6+)|

---

## Getting Started

No build step. No install.

```bash
git clone https://github.com/yourusername/calculator
cd calculator
open calculator.html
```

Or just open `calculator.html` in any modern browser.

---

## Keyboard Shortcuts

| Key          | Action              |
|--------------|---------------------|
| `0–9`        | Input digit         |
| `+ - * /`    | Set operator        |
| `Enter` / `=`| Calculate           |
| `Backspace`  | Delete last digit   |
| `Escape`     | Clear all           |
| `Ctrl + C`   | Copy result         |

---

## Engineering Highlights

**State-driven architecture**
All calculator state (`num1`, `num2`, `operator`, `memory`, `history`) lives in a single `state` object. No scattered globals. Every function reads from and writes to this object, making the data flow predictable and easy to debug.

**Operator chaining**
When a user inputs `5 + 3 *`, the previous expression is evaluated automatically before the new operator is applied — matching the behavior of standard calculators without requiring expression parsing or an AST.

**Keyboard visual feedback**
A `KB_MAP` object maps keyboard keys to button element IDs. On keydown, the corresponding button receives a `kb-active` CSS class that pulses for 120ms — giving the user the same tactile signal as clicking.

**Clipboard with fallback**
The copy feature uses the modern `navigator.clipboard.writeText()` API with a `try/catch` fallback to `execCommand('copy')` for older browser compatibility.

**Precision handling**
Results are rounded using `toPrecision(12)` then re-parsed as float to strip trailing zeros — preventing floating-point noise like `0.30000000000000004` from appearing in the display.

---

## Screenshots

> _Add screenshots here_

---

## Roadmap

- [ ] Scientific mode (sin, cos, √, x²)
- [ ] Theme switcher (light / dark / high-contrast)
- [ ] LocalStorage persistence for history
- [ ] PWA support (installable, offline)
- [ ] Swipe gestures for mobile
