---
layout: single
title: "Calculator App"
excerpt: "A simple rpn style calculator"
classes: wide
feature_row:
  - image_path: /assets/images/calculator.png
    alt: "calculator app"
    excerpt: "app in use -- [view](/assets/images/calculator.png)"
---

# Calculator: A simple rpn style calculator app

{% include feature_row %}

- Created as RPN calculator because it is used more in math/science fields and is more complex to execute.
- Uses a Model View Controller design pattern.
- View is a PySide6 GUI.
- The calculator buttons operate via mouse clicks.

## Coding reflections

- The layout of the GUI required some tweaking to get it to align properly.
- Implementing a MVC design required splitting the logic functions into a model and considering edge cases like divide by zero, operating on an empty stack, etc.
- The controller needed to convert inputs into an updated view and passing the actions to the model for updates.

## Source Code

See source code at the repo on <a href="https://github.com/stevebrauner/calculator">GitHub</a>.
