# Calculator

from replit import clear
from art import logo
def addition(n1,n2):
  return n1+n2
def sub(n1,n2):
  return n1-n2
def multi(n1,n2):
  return n1*n2
def div(n1,n2):
  return n1/n2
# creating a dictionary named operations
operations={'+':addition,
'-':sub,
'*':multi,
'/':div}

def calculator():
  print(logo)
  num1=float(input("What's the first number?\n"))


  for key in operations:
    print(key)
  should_continue=True
  while should_continue:
    operation=input("Pick an operation: \n")
    num2=float(input("What's the next number?\n"))
    calculation_function=operations[operation]
    answer=calculation_function(num1,num2)

    print(f"{num1} {operation} {num2}={answer}")
    if input(f"Type 'y' to continue calculating with{answer},or type'n' to exit\n")=='y':
      num1=answer
    else:
      should_continue=False
      print(f"Final answer is {answer}")
      clear()
      calculator()
calculator()      
      
