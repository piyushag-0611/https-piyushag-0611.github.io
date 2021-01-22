---
layout: page
title: Data_Science
subtitle: Foundations of Data Science by Avrim Blum, John Hopcroft and Ravindra Kannan
---
I have taken up a SLP Project for this semester under **Prof. Niranjan Balachandran** who has motivated me to read this book(name in the subtitle :p).
So I want to upload regularly on this page whatever experiments I carry out on this and have a good learning experience.

## Law of Large Numbers 
Consider the case of **heights** of people around the world. If the heights did follow a distribution, then the mean value of the heights of people all around the world would be very close to say the mean of heights of **10000 people**, given that you collected the heights randomly.

So How does the **Law of Large Numbers** help, it clearly helps you in getting good estimate of things in which you may have a commercial interest. Say for example Vehicles generally will have the internal dimensions same for the driver's seat and still it works for most people, male or female, short or tall. Consider the case of trousers, there are generally standard sizes, but it works well for most of us. How do we get the idea of what a good measurement is that will work for most people?

I think the Law of Large Number helps. 

**A Demonstration**
So I wrote down a python codes illustrating the Law of Large Numbers. Its a simple Head or Tail situation, and as we increase the number of tosses our calculated or experimental mean does go pretty close to 0.5.

~~~
#Demonstrating Law of Large Numbers
import matplotlib.pyplot as plt
import random
import numpy as np
toss =[0,1]
list = [10,20,30,40,50,100,200,400,800,1000,2000,4000,8000,20000,50000]
list_in_log = np.log10(list)
ratio_of_tails = []
for i in list:
    tails = 0
    for j in range(i):
        outcome = random.choice(toss)
        if outcome==1:
            tails = tails+1
    ratio_of_tails.append(tails/i)
plt.plot(list_in_log,ratio_of_tails)

~~~
![post](https://i.imgur.com/38JTygH.png)
You can see how as no. of tosses increase the experimental probability of heads goes to 0.5

## An interesting Problem
Given a random number generator which follows the uniform distribution, can you determine the value of **pi** ?

Let me put out the solution.

The idea is to generate points and find out the fraction of points lying inside the half square if our total set of points is the unit circle.<br>

~~~
#determing pi
#Generating 10000 points.
import random
import matplotlib.pyplot as plt
list =[]
for i in range(100):
    points_in_circle=0
    points_in_square=0
    for i in range(10000):
        x=random.random()
        y=random.random()
        if x*x+y*y<1:
            points_in_circle = points_in_circle+1
        if x<0.5 and y<0.5:
            points_in_square = points_in_square+1
    list.append(points_in_circle/points_in_square)
plt.plot(list)
~~~
![post](https://i.imgur.com/bUR8FFe.png)

This depicts the values of **pi** that I got using the above method. Ok, correct to two significant digits only but still. :p

## Volume of a d-dimensional Unit ball

Surprising




