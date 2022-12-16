from tkinter import *
# create window
root = Tk()
root.title("Calculator")
# create display 
display = Entry(root, font=("Arial", 20), width=30, bd=5, justify=RIGHT)
display.grid(row=0, column=0, columnspan=4, padx=5, pady=5)

# create buttons
buttons = [
    ["7", "8", "9", "/"],
    ["4", "5", "6", "*"],
    ["1", "2", "3", "-"],
    ["0", "C", "=", "+"]
]

#current operation
current_operation = ""

# button click function
def button_click(number):
    # it's global variable because every time a button is clicked variable must ch
    global current_operation
    current_operation = current_operation + str(number)
    display.delete(0, END)
    display.insert(0, current_operation)

# equal button function
def equal_button():
    global current_operation
    #eval func takes the string as an expression and determines its value. For instance, the string "3 + 5" would return 8.
    result = eval(current_operation)
    display.delete(0, END)
    display.insert(0, result)
    current_operation = ""

# clear button function
def clear_button():
    global current_operation
    current_operation = ""
    display.delete(0, END)

# create buttons using loop
row = 1
for button_row in buttons:
    column = 0
    for button in button_row:
        if button == "=":
            Button(root, text=button, width=15, command=equal_button).grid(row=row, column=column, padx=5, pady=5)
        elif button == "C":
            Button(root, text=button, width=15, command=clear_button).grid(row=row, column=column, padx=5, pady=5)
        else:
            Button(root, text=button, width=15, command=lambda number=button: button_click(number)).grid(row=row, column=column, padx=5, pady=5)
        column += 1
    row += 1

root.mainloop()
