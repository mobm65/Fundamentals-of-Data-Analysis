# Fundamentals-of-Data-Analysis
Assessment Tasks
I started research on this topic by defining the terms; function, list, dictionary and key-value pairs. The assignment reminded me of a frequency table from Leaving Certificate Maths so I thought I might approach it from this angle.
I found the following, which was a result of a search how to find mode without importing a function, from the site 
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
  
 This function had the desired effect, you put in a list and it returns a dictionary of key-value pairs but I didn't understand it and I could not get it to work.
 
 

