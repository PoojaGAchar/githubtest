# githubtest
from tkinter import *
  
# globally declare the expression variable 
expression = ""

  
# Function to update expressiom 
# in the text entry box 
def press(num): 
    # point out the global expression variable 
    global expression 
  
    # concatenation of string 
    expression = expression + str(num) 
  
    # update the expression by using set method 
    equation.set(expression) 
  
  
# Function to evaluate the final expression 
def equalpress(): 
    # Try and except statement is used 
    # for handling the errors like zero 
    # division error etc. 
  
    # Put that code inside the try block 
    # which may generate the error 
    try: 
  
        global expression 
  
        # eval function evaluate the expression 
        # and str function convert the result 
        # into string 
        total = str(eval(expression)) 
  
        equation.set(total) 
  
        # initialze the expression variable 
        # by empty string 
        expression = "" 
  
    # if error is generate then handle 
    # by the except block 
    except: 
  
        equation.set(" error ") 
        expression = "" 
  
  
# Function to clear the contents 
# of text entry box 
def clear(): 
    global expression 
    expression = "" 
    equation.set("")

  
# Driver code 
if __name__ == "__main__": 
    # create a GUI window 
    gui = Tk() 
  
    # set the background colour of GUI window 
    gui.configure(background="black") 
  
    # set the title of GUI window 
    gui.title("Calculator") 
  
    # set the configuration of GUI window 
    gui.geometry("500x250") 
  
    # StringVar() is the variable class 
    # we create an instance of this class 
    equation = StringVar() 
  
    # create the text entry box for 
    # showing the expression . 
    expression_field = Entry(gui, textvariable=equation) 
  
    # grid method is used for placing 
    # the widgets at respective positions 
    # in table like structure . 
    expression_field.grid(columnspan=50, ipadx=200) 
  
    equation.set('') 
  
    # create a Buttons and place at a particular 
    # location inside the root window . 
    # when user press the button, the command or 
    # function affiliated to that button is executed . 
    button1 = Button(gui, text=' 1 ', fg='black', bg='white', 
                     command=lambda: press(1), height=2, width=9, highlightthickness=0).grid(row=5, column=0, sticky="nsew")  ##sticky-No Space
  
    button2 = Button(gui, text=' 2 ', fg='black', bg='white', 
                     command=lambda: press(2), height=2, width=9,highlightthickness=0).grid(row=5, column=1, sticky="nsew") 
  
    button3 = Button(gui, text=' 3 ', fg='black', bg='white', 
                     command=lambda: press(3), height=2, width=9,highlightthickness=0).grid(row=5, column=2,sticky="nsew") 
  
    button4 = Button(gui, text=' 4 ', fg='black', bg='white', 
                     command=lambda: press(4), height=2, width=9,highlightthickness=0).grid(row=4, column=0,sticky="nsew") 
  
    button5 = Button(gui, text=' 5 ', fg='black', bg='white', 
                     command=lambda: press(5), height=2, width=9,highlightthickness=0).grid(row=4, column=1,sticky="nsew") 
  
    button6 = Button(gui, text=' 6 ', fg='black', bg='white', 
                     command=lambda: press(6), height=2, width=9,highlightthickness=0).grid(row=4, column=2,sticky="nsew") 
  
    button7 = Button(gui, text=' 7 ', fg='black', bg='white', 
                     command=lambda: press(7), height=2, width=9,highlightthickness=0).grid(row=3, column=0,sticky="nsew") 
  
    button8 = Button(gui, text=' 8 ', fg='black', bg='white', 
                     command=lambda: press(8), height=2, width=9,highlightthickness=0).grid(row=3, column=1,sticky="nsew") 
  
    button9 = Button(gui, text=' 9 ', fg='black', bg='white', 
                     command=lambda: press(9), height=2, width=9,highlightthickness=0).grid(row=3, column=2,sticky="nsew") 
  
    button0 = Button(gui, text=' 0 ', fg='black', bg='white', 
                     command=lambda: press(0), height=2, width=9,highlightthickness=0).grid(row=6, column=1,sticky="nsew") 
  
    plus = Button(gui, text=' + ', fg='black', bg='white', 
                  command=lambda: press("+"), height=2, width=9,highlightthickness=0).grid(row=5, column=3,sticky="nsew") 
  
    minus = Button(gui, text=' - ', fg='black', bg='white', 
                   command=lambda: press("-"), height=2, width=9,highlightthickness=0).grid(row=4, column=3,sticky="nsew") 
  
    multiply = Button(gui, text=' * ', fg='black', bg='white', 
                      command=lambda: press("*"), height=2, width=9,highlightthickness=0).grid(row=3, column=3,sticky="nsew") 
  
    divide = Button(gui, text=' / ', fg='black', bg='white', 
                    command=lambda: press("/"), height=2, width=9,highlightthickness=0).grid(row=2, column=3,sticky="nsew") 
  
    equal = Button(gui, text=' = ', fg='black', bg='white', 
                   command=equalpress, height=2, width=9,highlightthickness=0).grid(row=6, column=3,sticky="nsew") 
  
    clear = Button(gui, text='Clear', fg='black', bg='white', 
                   command=clear, height=2, width=9,highlightthickness=0).grid(row=6, column=0,sticky="nsew") 
  
    Decimal = Button(gui, text='.', fg='black', bg='white', 
                    command=lambda: press("."), height=2, width=9,highlightthickness=0).grid(row=6, column=2,sticky="nsew")

    SquareRoot = Button(gui, text='√', fg='black', bg='white',                                                        
                    command=lambda: press("**0.5"), height=2, width=9,highlightthickness=0).grid(row=2, column=0,sticky="nsew")

    Square = Button(gui, text='x²', fg='black', bg='white',             ## square sign = Alt+253
                   command=lambda: press('**2'), height=2, width=9,highlightthickness=0).grid(row=2,column=1,sticky="nsew")

    Cube = Button(gui, text='x³', fg='black', bg='white',               ## cube sign = Alt+0179
                  command=lambda: press('**3'), height=2, width=9,highlightthickness=0).grid(row=2,column=2,sticky="nsew")
    # start the GUI 
    gui.mainloop() 
