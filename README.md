# Fundamentals-of-Data-Analysis
Assessment Tasks
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





