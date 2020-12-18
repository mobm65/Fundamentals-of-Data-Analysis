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
 
https://stackoverflow.com/questions/2161752/how-to-count-the-frequency-of-the-elements-in-an-unordered-list
I continued research in this line and found this site useful in solving the assigned problem.

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

TASK 2 - DICEROLLS
For the 2nd Task, DICEROLLS, I googled some ideas about random sampling on numpy to decide what functions to use.  The following site was informative.
https://medium.com/stephen-godfreys-blog/using-python-to-visualize-probability-questions-64a6f73b9568

These four sites were useful to revise some of the lessons we had done and to help create effective syntax.
https://realpython.com/lessons/randomness-modeling-and-simulation/ 
Revision of creating random integer lists in Python
https://realpython.com/lessons/while-loops-conclusion-lessons-learned/ 
Revision of while loops.
https://www.w3schools.com/python/python_while_loops.asp 
A useful site to help find what loop I need to create to iterate through the number of dice (k) by the number of times it/they are thrown(n).
https://www.w3schools.com/python/python_for_loops.asp 
Revision of for loops

https://www.w3schools.com/python/ref_func_zip.asp  Helped with zipping the two face values, first two, then second two and so on.

https://stackoverflow.com/questions/65071627/python-function-that-simulates-rolling-dice-based-on-input-parameters-1-number Trying to see how others have dealt with this problem and model some of their ideas.

https://stackoverflow.com/questions/8528178/list-of-zeros-in-python Helped me find a way to start the loop. I learned it is a common practice to begin with zero values which allowed me to create a list of tuples I could iterate over.

I first tried to generate the data, the numpy function random.randint allows me to select numbers randomly.  I use the parameters 1 and 7 because this function is not inclusive of the higher number.  The final parameter tells the function how many times to iterate.  I found the zip function in stackoverflow and used it to zip the two facevalues and print the results.
The next task was to develop the function by incorporating the n parameter. The previous function I created, counts, will be useful in creating a dictionary of values
with the number of times they appear.  I again use the zip function which creates tuples and incorporates the parameter n, the number of throws.  I call the result summed_rolls and pass it through counts.  
In the 3rd code cell of this task I combined all the elements, the function dicerolls with the parameters n (number of throws) and k (number of dice).  Stackoverflow replies suggested I started from a set with all zero values and add my next and subsequent throws, totals is my list of dice multiplied by n, the number of times dice are thrown. n_dice_rolls is the random selection chosen by the random.randint function. k is the number of dice thrown. The zip function zips the totals of dice thrown by number of times AND the random dice rolls.  I can now call return which passes totals through the function counts.  This completes the function dicerolls with the paramenters k and n.


TASK 3 - NUMPY.RANDOM.BINOMIAL

SOURCES
https://www.journaldev.com/33182/python-add-to-list
    How to find a way to add elements unto a list.
    
https://www.w3schools.com/python/python_while_loops.asp
    Useful to write code with correct syntax.
    
https://numpy.org/doc/stable/reference/random/generated/numpy.random.binomial.html
    Researching the background to and uses of this function.

https://www.w3schools.com/python/numpy_random_binomial.asp
    Both useful sites to research the function random.binomial and its parameters.
    
Numpy.random is a PRNG, a pseudo random number generator, and it generates pseudo random arrays.
A binomial function can have only two possible outcomes; yes/no, true/false, heads/tails. It is, therefore, a discrete distribution. The function I am using is numpy.random.binomial which takes three parameters: n = the number of trials, p = the probability of the outcome occuring and size = the shape of the returned array.  I will
be using this to show the probability of throwing heads with a coin is 1 in every 2 tosses.  Therefore 68% of the data should fall within one standard deviation from the mean, 95% of the data will fall within 2 standard deviations of the mean and 99.7% of the data will fall within 3 standard deviations from the mean.  
The first task is to create a random number of throws.  I am calling this coinflip and I will enter the parameters 100 coin tosses with a probability of .5, 100 times into the function numpy.random.binomial.  I use this to develop a function heads which throws a dice 100 times and records the number of times it faces heads up(1) or tails up (0).  This takes the input coinflips and returns them summed up.  It uses a while loop to append instances up to 1000 and sum them.  I start with an empty list as a base on which I call results.  I start at the element i = 0 and iterate through all elements up to 1000. I then append these results to the return from the function heads.  Finally I use seaborn distplot to plot the normal distribution.  It is not perfectly distributed but when I increase the sample size in the random.binomial function to 1000 it looks a much better fit.

TASK 4 - SIMPSON'S PARADOX
Simpson's paradox is a trend which is evident in a number of groups but it reverses when the groups are combined. As Mark Twain said there are "lies, damned lies and statistics." The impact of all possible variables must be considered before concluding that one variable is linked to another. Bickel's US Berkley study from 1974 seemed to indicate gender bias in favour of men. When each department was assessed individually, there was actually a small but statistically relevant bias in favour of women. Simpson's paradox can arise when there is a confounding variable. This variable is not taken into account in the causal relationship between two variables, yet it can impact them.
For example it seems that Apple can charge whatever they want and people buy their phones. This might lead us to believe that high price correlates with high sales. A confounding variable here might be the social status attached to owning an iphone or customer loyalty to the brand.
In this assignment I plan to show that four datasets can have a similar linear regression when plotted separately, this may change when the datasets are concatenated before plotting.

SOURCES
https://en.wikipedia.org/wiki/Simpson%27s_paradox
This site was very information and gave me a great basis to plan my assignment. 

https://www.w3schools.com/python/numpy_creating_arrays.asp
Researching the correct function to create the datasets.

https://matplotlib.org/2.1.1/api/_as_gen/matplotlib.pyplot.plot.html
Helpful in choosing a suitable plot to display the data.

https://www.datacamp.com/community/tutorials/joining-dataframes-pandas
This was really helpful for me, there were useful code snippets I could
manipulate and use to concatenate the data.

https://pandas.pydata.org/pandas-docs/stable/user_guide/merging.html
This site provided information about ways to merge datasets.
    

DETAILS
I created four dataframes, dfa, dfb, dfc and dfd using python dictionary. The column x takes its data
from the x, x2, x3 or x4 data created by the function np.linspace. The column y takes its
data from the y, y2, y3 or y4 data created by the function np.linspace.
The new dataframes are dfa, dfb, dfc and dfd and has the data from a, b, c or d, and columns x & y.
I used pyplot to illustrate the data.

I then used matplotlib to illustrate the datasets together on the same plot.
The plot shows the four datasets shown on the same graph, they are still separate at this point.
The legend indicates which plot is which and each trendline has a different colour.

Finally I used the pandas concat function to join/concatenate the four dataframes to one dataset which I call df_row.

RESULT
This plot does not seem to indicate that the combination of the dataframes made any difference to the positive trend of the data.







