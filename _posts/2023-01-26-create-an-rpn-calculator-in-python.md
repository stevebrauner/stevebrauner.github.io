---
layout: single
title: "Create a Simple RPN Calculator in Python"
date: 2023-01-26 
categories: python
---

# Create an RPN Calculator in Python

In this post I will walk you through the creation of a simple Reverse Polish Notation (RPN) calculator in Python

## What is an RPN Calculator?

An RPN calculator uses Reverse Polish Notation for entering calculations.

According to Wikipedia, <a href="https://en.wikipedia.org/wiki/Reverse_Polish_notation">Reverse Polish Notation (RPN)</a> is

<blockquote>a mathematical notation in which operators follow their operands</blockquote>

For example, to calculate "3 + 4" you would type

<blockquote>3 &lt;enter&gt; 4 +</blockquote>

The calculator employs a stack to store numbers and the results of calculations for use later. In the above example the user presses the number 3. When the <enter> button is pressed the 3 is pushed onto the stack. Next the 4 is pressed followed by the + button. The calculator adds the 4 with the number on the top of the stack (in this case the 3, which it popped off the stack) and displays the answer (7) and pushes that on the stack (so at the end only the 7 is on the stack).

## Our Simple RPN Calculator

The calculator we are creating will have an entry area for numbers being entered and for the displaying of the results of calculations. It will have a stack that stores numbers entered or calculated, and the stack will be displayed as well.

The calculator will have a number pad with the digits 0-9, a period (.), and an enter key. It will have buttons for addition (+), subtraction (-), multiplication (*), and division (/) operations. It will have a sign button (+/-) to toggle the sign of the number in the entry area.

The calculator will have a drop (DRP) button for removing a number from the top of the stack (deleting it), a swap (SWP) button for swapping the top number on the stack with the current number in the entry area, and a pop (POP) button to remove the number from the top of the stack and place it in the entry area.

It will have a clear button (C) to clear the entry area (leaving the stack intact), and an all clear button (AC) to clear the entry area and the stack.

We will use a Model, View, Controller (MVC) design pattern for this project.

## Let's Start Coding

We will set up the project directory with a virtual environment. Next, we will install the PySide6 package that will be our GUI.

We will then create the calculator's model with the logic needed to calculate and store the numbers.

The view will contain the button layout, and the entry and stack areas.

The controller will contain the connections between the view and the model.

Finally, the app will be the file that runs the calculator by instantiating the model, view, and controller.

### The virtual environment and installing of packages

Create a directory (or a more complex project directory) for the project (calculator) and create a virtual environment for python3 for the directory. Install the needed package for the project -- PySide6 (for the GUI).

### The Model

Create a model.py file for the Model class. This class initiates an internal stack (_stack) for the storage of numbers in a first in, last out storage system (implemented with a basic Python list).

The Model class has methods for manipulating the stack -- for returning the stack (get_stack), clearing the stack (clear_stack), pushing a number on the stack (push_on_to_stack), popping a number from the stack (pop_from_stack). The pop method has an error check in case the stack is empty.

It has methods for calculations -- for adding (add), for subtracting (subtract), for multiplying (multiply), and for dividing (divide). All of these checks for an empty stack. The divide method checks for divide by zero condition.

Finally, a method that pushes a number on to the stack and returns the number helps with the calculation methods.

{% gist 38180a642e7cdf0de97ba49803e9a58c model.py %}

### The View

The view uses the PySide6 package for the GUI of the calculator.

The View class creates the widgets used to make the calculator's interface. It uses a grid layout so that the elements may be laid out properly.

It uses methods for the elements of the layout:
- layout_keys creates the buttons for the numbers (0-9), the period (.), the functions pop (POP), drop (DRP), clear (C), all clear (AC), swap (SWP), the sign changer (+/-), the operations divide (/), multiply (*), subtract (-), and add (+), and the enter key (RET).
- layout_entry creates the label for the entry display.
- layout_stack creates the label for the multiline stack display.

{% gist b3ac3860abad61c04453cd493219a723 view.py %}

### The Controller

The controller connects a model and view together to allow button presses to inform the model to update the stack, to do calculations, and return values needed to update the view.

The controller uses an entry string (_entry) to hold the number being entered (via the buttons "9-0", ".", and "+/-") or displayed (after "POP", "SWP", or a calculation via "/", "*", "-", "+").

Each button in the view ("9-0", ".", "POP", "DRP", "C", "AC", "SWP", "+/-", "/", "*", "-", "+", "RET") is connected with a method that updates the view and/or the model with the action requested. The entry and stack areas are updated as needed after each button press.

{% gist c46a7488c2cde4b50bb70654f96ad497 controller.py %}

### The App

The app file (app.py) connects the model, view, and controller, and runs the program.

The App class initializes a GUI, instantiates a model, view, and controller (using the model and view). It has a run method that creates the view elements, connects the view with the model in the controller, displays the finished GUI, and allows for it to be cleanly closed.

When the app.py file is run directly (with python app.py) it instantiates the App class and executes its run method.

{% gist c0d667814203a330c66447dbf40ddeec app.py %}

## Conclusion

Well that's the simple RPN calculator project. You can find the repository for this project on <a href="https://github.com/stevebrauner/calculator">GitHub</a>.

If you want to expand this project you can add additional operations such as square root, square, reciprocal, trigonometry functions, etc.

I hope you enjoyed this project and that you will give it a try.
