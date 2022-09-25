---
layout: single
title: "Calculator"
excerpt: "A simple rpn style calculator"
classes: wide
header:
  teaser: /assets/images/calculator.png
feature_row:
  - image_path: /assets/images/calculator.png
    alt: "calculator app"
    excerpt: "app in use -- [view](/assets/images/calculator.png)"
---

# Calculator: A simple rpn style calculator app

{% include feature_row %}

- Uses a Model View Controller design pattern.
- View is a PySide6 GUI.
- The calculator buttons operate via mouse clicks.

As an RPN style calculator you 
1. enter a number (use +/- button to change sign).
2. add it to the stack with the RET button (Return).
3. enter second number.
4. press the operator key (+, -, /, or *).
5. result is placed on the stack and displayed.

<p>See source code at the repo on <a href="https://github.com/stevebrauner/calculator">GitHub</a>.</p>
