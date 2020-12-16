---
layout: page
title: Data_Science
subtitle: Foundations of Data Science by Avrim Blum, John Hopcroft and Ravindra Kannan
---
I have taken up a SLP Project for the next semester under my Prof. Niranjan Balachandran who has motivated me to read this book(name in the subtitle :P). </br>
So I want to upload regularly on this page whatever experiments I carry out on this and have a good learning experience.

The first thing was the Law of Large Numbers, the proof is easy but what I think can make a general audience interested are illustrations. So I wrote down two python codes illustrating the Law of Large Numbers.

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
![Plot](https://github.com/piyushag0611/piyushag0611.github.io/blob/master/assets/img/largenolog.png)

You can see how as no. of tosses increase the experimental probability of heads goes to 0.5
