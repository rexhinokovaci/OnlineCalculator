# Online Calculator

A clean, responsive calculator for the browser, written in vanilla JavaScript with a CSS Grid keypad.

**Live demo:** https://rexhinokovaci.github.io/OnlineCalculator/

## Features

- Addition, subtraction, multiplication and division
- **Chained operations**: picking a new operator evaluates the pending one first (`2 + 3 *` shows `5 *`)
- Two-line display: the previous operand plus operator on top, the current input below
- **AC** (all clear) and **DEL** (delete last digit)
- Rejects a second decimal point and ignores operators when there's no number to work on
- Thousands separators in the display (`1,234,567.89`)

## How it works

All state lives in a small `Calculator` class in `script.js`:

| Method | Role |
| --- | --- |
| `appendNumber()` | Builds the current operand, rejecting duplicate decimal points |
| `chooseOperation()` | Stores the operator, computing first if an operation is already pending |
| `compute()` | Applies `+`, `-`, `*` or `÷` with `parseFloat` |
| `getDisplayNumber()` | Formats the integer part with `toLocaleString` and keeps the decimals as typed |
| `updateDisplay()` | Renders both display lines |

Buttons are wired up with `data-*` attributes (`data-number`, `data-operation`, `data-equals`, `data-delete`, `data-all-clear`) and the JavaScript looks them up with `querySelectorAll`.

## Tech stack

HTML5, CSS3 (Grid layout) and vanilla JavaScript (ES6 classes). No dependencies, no build step. Hosted on GitHub Pages.

## Running locally

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

Or just open `index.html` in a browser.

---

Built by [Rexhino Kovaci](https://github.com/rexhinokovaci) — DevOps & AI engineer in Tirana, Albania. Need an app built? [Get in touch](mailto:kovacirexhino@gmail.com).
