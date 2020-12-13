# Fundamentals-of-Data-Analysis

## Assessment Tasks

COUNTS
I started research on this topic by defining the terms; function, list, dictionary and key-value pairs. The assignment reminded me of a frequency table from Leaving Certificate Maths so I thought I might approach it from this angle.

I found the following, which was a result of a search how to find mode without importing a function, from the site:
https://medium.com/analytics-vidhya/python-mean-median-mode-functions-without-importing-anything-b2be91870280

def mode(1st):
    frequency = {}
    for number in 1st:
            frequency.setdefault(number,0)
            frequency.[number]+=1
    print(frequency)
 
 input
 mode([list of numbers])
 
 output
 {key-value pairs i.e. the number and its frequency}
  
 This function should have had the desired effect, you put in a list and it returns a dictionary of key-value pairs but I didn't understand it and I could not get it to work.
 
 
I continued research in this line and found the following useful in solving the assigned problem.  
https://stackoverflow.com/questions/2161752/how-to-count-the-frequency-of-the-elements-in-an-unordered-list

>>> a = [1,1,1,1,2,2,2,2,3,3,4,5,5]
>>> d = {x:a.count(x) for x in a}
>>> d
{1: 4, 2: 4, 3: 2, 4: 1, 5: 2}
>>> a, b = d.keys(), d.values()
>>> a
[1, 2, 3, 4, 5]
>>> b
[4, 4, 2, 1, 2]

This function will build the dictionary from the list and get the count as well as get rid of duplicates.

I modified the code to suit my requirements, basically I just need to rework the first two lines. In my code d becomes the function counts and it 
will give me a dictionary of key-value pairs from a list of ints or strings.

This function I created cannot be replicated so I consulted this website for help. https://www.w3schools.com/python/python_functions.asp
To make the code a proper function I needed to add a return statement.  At this point I have succeeded in getting my function to return itself but
not the answer.

Return Values
To let a function return a value, use the return statement:
Example
def my_function(x):
  return 5 * x
print(my_function(3))
print(my_function(5))
print(my_function(9))

I needed to disassociate my function from the list a so that it would work independently.  So I defined the function using b in the syntax, my function now
iterated over b to make the dictionary.  I used the return statement to end the execution of function call and give the results I wanted.  When I ran the properly
defined counts function on the list a, it returned every element, x, and the number of times x appeared, f(x).

DICEROLLS
For the 2nd Task, DICEROLLS, I googled some ideas about random sampling on numpy to decide what functions to use.  The following site was informative.
https://medium.com/stephen-godfreys-blog/using-python-to-visualize-probability-questions-64a6f73b9568

These four sites were useful to revise some of the lessons we had done and to help create effective syntax.
https://realpython.com/lessons/randomness-modeling-and-simulation/ Revision of creating random integer lists in Python
https://realpython.com/lessons/while-loops-conclusion-lessons-learned/ Revision of while loops.
https://www.w3schools.com/python/python_while_loops.asp A useful site to help find what loop I need to create to iterate through the number of dice (k) by the number of times it/they are thrown(n).
https://www.w3schools.com/python/python_for_loops.asp Revision of for loops

https://www.w3schools.com/python/ref_func_zip.asp  Helped with zipping the two face values, first two, then second two and so on.

https://stackoverflow.com/questions/65071627/python-function-that-simulates-rolling-dice-based-on-input-parameters-1-number Trying to see how others have dealt with this problem and model some of their ideas.

https://stackoverflow.com/questions/8528178/list-of-zeros-in-python Helped me find a way to start the loop. I learned it is a common practice to begin with zero values which allowed me to create a list of tuples I could iterate over.

I first tried to generate the data, the numpy function random.randint allows me to select numbers randomly.  I use the parameters 1 and 7 because this function is not inclusive of the higher number.  The final parameter tells the function how many times to iterate.  I found the zip function in stackoverflow and used it to zip the two facevalues and print the results.
The next task was to develop the function by incorporating the n parameter. The previous function I created, counts, will be useful in creating a dictionary of values
with the number of times they appear.  I again use the zip function which creates tuples and incorporates the parameter n, the number of throws.  I call the result summed_rolls and pass it through counts.  
In the 3rd code cell of this task I combined all the elements, the function dicerolls with the parameters n (number of throws) and k (number of dice).  Stackoverflow replies suggested I started from a set with all zero values and add my next and subsequent throws, totals is my list of dice multiplied by n, the number of times dice are thrown. n_dice_rolls is the random selection chosen by the random.randint function. k is the number of dice thrown. The zip function zips the totals of dice thrown by number of times AND the random dice rolls.  I can now call return which passes totals through the function counts.  This completes the function dicerolls with the paramenters k and n.

