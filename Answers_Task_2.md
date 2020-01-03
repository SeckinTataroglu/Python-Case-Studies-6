```python



# The order of the questions of "a","b" and "c" reordered to prevent potential errors and writing more code than it should be.

import datetime as dt
import string as st
import calendar

def anyLetter(input):
    result = False
    for i in input:
        if not i.isdigit():
            result =True
    return result

monthNames = {1:"January",
              2:"February",
              3:"March",
              4:"April",
              5:"May",
              6:"June",
              7:"July",
              8:"August",
              9:"September",
              10:"October",
              11:"November",
              12:"December"}


# The execution of the code stops when the date is entered in the correct format.
while True:
    
    dateEntered = input("Please enter your birthday in format of DD/MM/YYYY: ")
   
    try:                                                           # try-catch mechanism was used to prevent any unexceptional error
        if dateEntered == "exit":
            print("The program has been terminated.\n")
            break
                
        
        # (c) If the input from the user is not 10 characters, an error message should be issued with an explanation of the error, and instructing the user to enter the date again.
        if len(dateEntered) != 10:
            print("(c) Please enter the date as DD/MM/YYYY and in total 10 characters including two '/' mark...\n")
            continue        
        
        
        
        # (b) If the '/' are not in correct place or absent, an error message should be issued with an explanation of the error, and instructing the user to enter the date again.
        if dateEntered[2] != "/" or dateEntered[5] != "/":
            print("(b) Please use '/' as separator of day, month and year...\n")
            continue         
        
        
        
        # (a) If the input contains letters from the alphabet then the code should instruct the user to enter only digits.
        if anyLetter(dateEntered[:2]) is True or anyLetter(dateEntered[3:5]) is True or anyLetter(dateEntered[6:]) is True:
            print("(a) Please enter numerical values...\n")
            continue
        
            
        
        # (d) If the month number exceeds 12 or is less than 1, an error is issued and the user is asked to correct the error he/she made.
        handleDate = dateEntered.split("/")                                      # Date was splitted to handle easier
        day = int(handleDate[0])
        month = int(handleDate[1])
        year = int(handleDate[2])
        
        if month < 1 or month > 12:
            print("(d) Please enter a month value between 1 and 12\n")
            continue
        
        
        
        # (e) If the day number is invalid for a given month (e.g., February 30th does not exist!), an error message is printed and the user is asked for another date entry.
        monthErrorMessage = ("(e) The day entered is invalid. Please enter an appropriate day for {}...\n".format(monthNames[month]))
        
        if (month == 2):                                              # Handling of leap years 
            if calendar.isleap(year) is True and (day > 29):
                print(monthErrorMessage)
                continue
            elif calendar.isleap(year) is False and (day > 28):
                print(monthErrorMessage)
                continue
        if(month == 4,6,9,11) and (day > 30):
            print(monthErrorMessage)
            continue
        if (month == 1,3,5,7,8,10,12) and (day > 31):
            print(monthErrorMessage)
            continue    
        
                
        # (f) If the day entered is in the future, or if the person's age is greater than 150 years old, an error is issued and the user is asked to correct the error he/she made.
        dateValue = dt.date(int(handleDate[2]),int(handleDate[1]),int(handleDate[0]))
        if dateValue >= dt.date.today():
            print("(f) Please enter an earlier date before today...\n")
            continue
        
        if int(dt.date.today().year - dateValue.year) > 150:
            print("(f) Are you" ,int(dt.date.today().year - dateValue.year), "years old?")
            print("(f) A mistake may have been made.\n")
            continue
        
        
        
    except ValueError:
        print("Unexpected error occured. Please enter a valid date...\n")
        continue
    

    
    
    
    print("The day is {}, the month is {}, and the Year is {}\n".format(day,monthNames[month],year))
    break
