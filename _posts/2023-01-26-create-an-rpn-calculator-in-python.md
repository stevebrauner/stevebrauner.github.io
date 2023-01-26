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

{% highlight plaintext %}
a mathematical notation in which
operators follow their operands
{% endhighlight %}

For example, to calculate "3 + 4" you would type

{% highlight plaintext %}
3
<enter>
4
+
{% endhighlight %}

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

{% highlight python %}

class Model:
    """
    Model class for the Calculator App -- A simple RPN style calculator.

    The model includes methods for addition, subtraction, division,
    and multiplication, along with methods to manipulate the stack and check
    for division by zero.
    """

    def __init__(self):
        self._stack = []
        self.ERROR_TEXT = "ERROR (ready for entry)"

    def get_stack(self):
        return self._stack

    def clear_stack(self):
        self._stack = []

    def push_on_to_stack(self, number):
        self._stack.append(number)

    def pop_from_stack(self):
        try:
            result = self._stack.pop()
        except IndexError:
            result = None
        finally:
            return result

    def add(self, number):
        number_from_stack = self.pop_from_stack()
        if number_from_stack:
            result = number_from_stack + number
            return self.push_and_return(result)
        else:
            return self.ERROR_TEXT

    def subtract(self, number):
        number_from_stack = self.pop_from_stack()
        if number_from_stack:
            result = number_from_stack - number
            return self.push_and_return(result)
        else:
            return self.ERROR_TEXT

    def multiply(self, number):
        number_from_stack = self.pop_from_stack()
        if number_from_stack:
            result = number_from_stack * number
            return self.push_and_return(result)
        else:
            return self.ERROR_TEXT

    def divide(self, denominator):
        nominator = self.pop_from_stack()
        if denominator != 0.0 and nominator:
            result = nominator / denominator
            return self.push_and_return(result)
        elif nominator:
            self.push_on_to_stack(nominator)
            return self.ERROR_TEXT
        else:
            return self.ERROR_TEXT

    def push_and_return(self, result):
        self.push_on_to_stack(result)
        return result

{% endhighlight %}

### The View

The view uses the PySide6 package for the GUI of the calculator.

The View class creates the widgets used to make the calculator's interface. It uses a grid layout so that the elements may be laid out properly.

It uses methods for the elements of the layout:
- layout_keys creates the buttons for the numbers (0-9), the period (.), the functions pop (POP), drop (DRP), clear (C), all clear (AC), swap (SWP), the sign changer (+/-), the operations divide (/), multiply (*), subtract (-), and add (+), and the enter key (RET).
- layout_entry creates the label for the entry display.
- layout_stack creates the label for the multiline stack display.

{% highlight python %}

from PySide6 import QtCore, QtWidgets


class View(QtWidgets.QWidget):
    """
    View for Calculator App -- a simple RPN style calculator.

    View uses PySide6 GUI framework.
    """

    def __init__(self):
        super().__init__()
        self.button = dict()

    def create_view(self):
        self.grid_layout = QtWidgets.QGridLayout(self)
        self.layout_keys()
        self.layout_entry()
        self.layout_stack()

    def layout_keys(self):
        self.layout_button("0", 5, 1)
        self.layout_button("1", 4, 1)
        self.layout_button("2", 4, 2)
        self.layout_button("3", 4, 3)
        self.layout_button("4", 3, 1)
        self.layout_button("5", 3, 2)
        self.layout_button("6", 3, 3)
        self.layout_button("7", 2, 1)
        self.layout_button("8", 2, 2)
        self.layout_button("9", 2, 3)

        self.layout_button(".", 5, 3)

        self.layout_button("POP", 4, 0)
        self.layout_button("DRP", 3, 0)
        self.layout_button("C", 2, 0)
        self.layout_button("AC", 1, 0)
        self.layout_button("SWP", 1, 1)
        self.layout_button("+/-", 1, 2)
        self.layout_button("/", 1, 3)
        self.layout_button("*", 1, 4)
        self.layout_button("-", 2, 4)
        self.layout_button("+", 3, 4)

        self.enter = QtWidgets.QPushButton("RET")
        self.set_size_policy(self.enter)
        self.enter.setMinimumSize(50, 50)
        self.grid_layout.addWidget(self.enter, 4, 4, 2, 1)

    def layout_button(self, text, row, column):
        self.button[text] = QtWidgets.QPushButton(text)
        self.set_size_policy(self.button[text])
        self.button[text].setMinimumSize(50, 50)
        self.grid_layout.addWidget(self.button[text], row, column)

    def layout_entry(self):
        self.entry = QtWidgets.QLabel()
        self.set_size_policy(self.entry)
        self.entry.setAlignment(QtCore.Qt.AlignRight)
        self.grid_layout.addWidget(self.entry, 0, 0, 1, 5)

    def layout_stack(self):
        self.stack = QtWidgets.QLabel()
        self.set_size_policy(self.stack)
        self.stack.setAlignment(QtCore.Qt.AlignBottom)
        self.grid_layout.addWidget(self.stack, 1, 5, 5, 3)

    def set_size_policy(self, widget):
        widget.setSizePolicy(
            QtWidgets.QSizePolicy.Expanding,
            QtWidgets.QSizePolicy.Expanding,
        )

{% endhighlight %}

### The Controller

The controller connects a model and view together to allow button presses to inform the model to update the stack, to do calculations, and return values needed to update the view.

The controller uses an entry string (_entry) to hold the number being entered (via the buttons "9-0", ".", and "+/-") or displayed (after "POP", "SWP", or a calculation via "/", "*", "-", "+").

Each button in the view ("9-0", ".", "POP", "DRP", "C", "AC", "SWP", "+/-", "/", "*", "-", "+", "RET") is connected with a method that updates the view and/or the model with the action requested. The entry and stack areas are updated as needed after each button press.

{% highlight python %}

from PySide6 import QtCore


class Controller:
    """
    Controller class for the Calculator App -- a simple RPN style calculator.

    The controller connects the Model and View classes.
    """

    def __init__(self, model, view):
        self.model = model
        self.view = view
        self.ERROR_TEXT = "ERROR (ready for entry)"
        self._entry = ""

    def connect_view_controller(self):
        self.view.button["9"].clicked.connect(self.nine)
        self.view.button["8"].clicked.connect(self.eight)
        self.view.button["7"].clicked.connect(self.seven)
        self.view.button["6"].clicked.connect(self.six)
        self.view.button["5"].clicked.connect(self.five)
        self.view.button["4"].clicked.connect(self.four)
        self.view.button["3"].clicked.connect(self.three)
        self.view.button["2"].clicked.connect(self.two)
        self.view.button["1"].clicked.connect(self.one)
        self.view.button["0"].clicked.connect(self.zero)
        self.view.button["."].clicked.connect(self.period)

        self.view.button["POP"].clicked.connect(self.entry_from_stack)
        self.view.button["DRP"].clicked.connect(self.drop_from_stack)
        self.view.button["C"].clicked.connect(self.clear_entry)
        self.view.button["AC"].clicked.connect(self.clear_all)
        self.view.button["SWP"].clicked.connect(self.swap_entry_stack_top)
        self.view.button["+/-"].clicked.connect(self.plus_minus)
        self.view.button["/"].clicked.connect(self.divide)
        self.view.button["*"].clicked.connect(self.multiply)
        self.view.button["-"].clicked.connect(self.subtract)
        self.view.button["+"].clicked.connect(self.add)
        self.view.enter.clicked.connect(self.enter)

    @QtCore.Slot()
    def nine(self):
        self._entry += "9"
        self.update_view_entry()

    @QtCore.Slot()
    def eight(self):
        self._entry += "8"
        self.update_view_entry()

    @QtCore.Slot()
    def seven(self):
        self._entry += "7"
        self.update_view_entry()

    @QtCore.Slot()
    def six(self):
        self._entry += "6"
        self.update_view_entry()

    @QtCore.Slot()
    def five(self):
        self._entry += "5"
        self.update_view_entry()

    @QtCore.Slot()
    def four(self):
        self._entry += "4"
        self.update_view_entry()

    @QtCore.Slot()
    def three(self):
        self._entry += "3"
        self.update_view_entry()

    @QtCore.Slot()
    def two(self):
        self._entry += "2"
        self.update_view_entry()

    @QtCore.Slot()
    def one(self):
        self._entry += "1"
        self.update_view_entry()

    @QtCore.Slot()
    def zero(self):
        self._entry += "0"
        self.update_view_entry()

    @QtCore.Slot()
    def period(self):
        if "." not in self._entry:
            self._entry += "."
            self.update_view_entry()

    @QtCore.Slot()
    def entry_from_stack(self):
        top_of_stack = self.model.pop_from_stack()
        if top_of_stack:
            self._entry = str(top_of_stack)
            self.update_view_entry()
            self.update_view_stack()
        else:
            self._entry = ""
            self.view.entry.setText(self.ERROR_TEXT)

    @QtCore.Slot()
    def drop_from_stack(self):
        result = self.model.pop_from_stack()
        if result:
            self.update_view_stack()
        else:
            self.entry_error()

    @QtCore.Slot()
    def clear_entry(self):
        self._entry = ""
        self.update_view_entry()

    @QtCore.Slot()
    def clear_all(self):
        self.clear_entry()
        self.model.clear_stack()
        self.update_view_entry()
        self.update_view_stack()

    @QtCore.Slot()
    def swap_entry_stack_top(self):
        entry_as_float = self.convert_entry_to_float()
        number_from_stack = self.model.pop_from_stack()
        if entry_as_float and number_from_stack:
            self._entry = str(number_from_stack)
            self.model.push_on_to_stack(entry_as_float)
            self.update_view_entry()
            self.update_view_stack()
        elif number_from_stack:
            self.entry_error()
            self.model.push_on_to_stack(number_from_stack)
            self.update_view_stack()
        else:
            self.entry_error()

    @QtCore.Slot()
    def plus_minus(self):
        if "-" not in self._entry:
            self._entry = "-" + self._entry
            self.update_view_entry()
        else:
            self._entry = self._entry[1:]
            self.update_view_entry()

    @QtCore.Slot()
    def enter(self):
        entry_as_float = self.convert_entry_to_float()
        if entry_as_float is not None:
            self.model.push_on_to_stack(entry_as_float)
            self._entry = ""
            self.update_view_entry()
            self.update_view_stack()
        else:
            self.entry_error()

    @QtCore.Slot()
    def divide(self):
        denominator = self.convert_entry_to_float()
        if denominator == 0.0:
            self.entry_error()
        elif denominator:
            answer = str(self.model.divide(denominator))
            self.display_entry_then_clear(answer)
            self.update_view_stack()
        else:
            self.entry_error()

    @QtCore.Slot()
    def multiply(self):
        number = self.convert_entry_to_float()
        if number is not None:
            answer = str(self.model.multiply(number))
            self.display_entry_then_clear(answer)
            self.update_view_stack()
        else:
            self.entry_error()

    @QtCore.Slot()
    def add(self):
        number = self.convert_entry_to_float()
        if number is not None:
            answer = str(self.model.add(number))
            self.display_entry_then_clear(answer)
            self.update_view_stack()
        else:
            self.entry_error()

    @QtCore.Slot()
    def subtract(self):
        number = self.convert_entry_to_float()
        if number is not None:
            answer = str(self.model.subtract(number))
            self.display_entry_then_clear(answer)
            self.update_view_stack()
        else:
            self.entry_error()

    def convert_entry_to_float(self):
        result = None
        try:
            result = float(self._entry)
        except ValueError:
            result = None
        finally:
            return result

    def entry_error(self):
        self._entry = ""
        self.view.entry.setText(self.ERROR_TEXT)

    def display_entry_then_clear(self, value):
        self.view.entry.setText(value)
        self._entry = ""

    def update_view_entry(self):
        self.view.entry.setText(self._entry)

    def update_view_stack(self):
        stack_for_view = "\n".join(map(str, self.model._stack[::-1]))
        self.view.stack.setText(stack_for_view)

{% endhighlight %}

### The App

The app file (app.py) connects the model, view, and controller, and runs the program.

The App class initializes a GUI, instantiates a model, view, and controller (using the model and view). It has a run method that creates the view elements, connects the view with the model in the controller, displays the finished GUI, and allows for it to be cleanly closed.

When the app.py file is run directly (with python app.py) it instantiates the App class and executes its run method.

{% highlight python %}

"""
Main file for running the Calculator App -- a simple RPN style calculator.

The App class instantiates the Model, View, and Controller classes, and
provides a run method.
This file also provides a main class to instantiate the App class and to
provide the if __name__ == "__main__" statement for running with
"python app.py".
"""
import sys

from controller import Controller
from model import Model
from PySide6 import QtWidgets
from view import View


class App:
    def __init__(self):
        self.app = QtWidgets.QApplication([])
        self.model = Model()
        self.view = View()
        self.controller = Controller(self.model, self.view)

    def run(self):
        self.view.create_view()
        self.controller.connect_view_controller()
        self.view.show()
        sys.exit(self.app.exec())


def main():
    app = App()
    app.run()


if __name__ == "__main__":
    main()

{% endhighlight %}

## Conclusion

Well that's the simple RPN calculator project. You can find the repository for this project on <a href="https://github.com/stevebrauner/calculator">GitHub</a>.

If you want to expand this project you can add additional operations such as square root, square, reciprocal, trigonometry functions, etc.

I hope you enjoyed this project and that you will give it a try.
