# Python-Case-Studies-1



## Task 1. String alphabet analysis


In the cell below, write a piece of code that will do the following work:

* (1) Introduce an arbitrary string of English text (you may cut and paste any text from an article on the web, etc.) The string should be no less than 500 charachters long.
* (2) Remove all digits from the string (e.g., '2'), leaving only alphabet characters (that is, the letters)
* (3) Calculate the number of words in the string, and have your program print the result
* (4) Calculate the number of times the letter 'a' appears in the string, and print the result
* (5) Using the python 'for' loop, do the same for all of the 26 letters in the alphabet. Note that both upper and lower case letters should be counted. 
* (6) Create a dictionary in which the frequency of each letter in the text is the value, and the letter is the key. 
* (7) Using the dictionary, have your program print the text 'The most frequently appearing letter is X, and it appears in the text N times', where X and N are calculated in the step above. 
* (8) Using the 'while loop' and the 'if' statement, print out any letters that are missing in the string.


Hints:

The following lines load English alphabet as a string in python, which should make it easier to do the task.

```python
import string
alphabet = string.ascii_lowercase
print alphabet
```




## Task 2. Using input from the user

Write a code that 
* Directs the User to enter their birth date, and accepts it in the format DD/MM/YYYY, e.g., 08/12/2015.
* Using the data entered, prints the message "The day is X, the month is Y, and the Year is Z", where X is 08, Y is December and Z is 2015 in the example above.
* Your code should catch the following errors:

    (a) If the input contains letters from the alphabet then the code should instruct the user to enter only digits.
    
    (b) If the '/' are not in correct place or absent, an error message should be issued with an explanation of the error, and instructing the user to enter the date again.
    
    (c) If the input from the user is not 10 characters, an error message should be issued with an explanation of the error, and instructing the user to enter the date again.
    
    (d) If the month number exceeds 12 or is less than 1, an error is issued and the user is asked to correct the error he/she made. 
    
    (e) If the day number is invalid for a given month (e.g., February 30th does not exist!), an error message is printed and the user is asked for another date entry. 
    
    (f) If the day entered is in the future, or if the person's age is greater than 150 years old, an error is issued and the user is asked to correct the error he/she made. 

The execution of the code stops when the date is entered in the correct format.

Notes: 

* Use the `.format' function to print the date in the correct format 

* Input from the User should be obtained by using the statement `raw_input`:

```python
input = raw_input("An instruction here: ")
```



