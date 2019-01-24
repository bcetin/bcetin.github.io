---
layout: post
title: Ancient Fax Machine Editorial
---
Last semester I was a student assistant for the [CMPE 250 course](https://www.cmpe.boun.edu.tr/~cemgil/Courses/cmpe250/index.html) at Boğaziçi University. Subject of the course is data structres and algorithms.
As the student assistants our role in the course was preparing the projects that will be assigned to the students and grading the submissions made by the students.
For this post I want to talk about the solution of this project and how I expected a student, or you the reader, to solve it.<!--break--> Of course for you to be able to solve the problem, you should first read the problem. I made a repository that contains the problem, solutions and a simple grader for this post.
But for now I am trusting you to just read the pdf file that contains the problem. [Here is the repo.](https://github.com/bcetin/CMPE250-Fall-2018-Project5)
**Note: Repository only has the question pdf right now, it will be when I write second part of this post. Stay tuned.**

So, you should be reading the problem now, instead of scrolling.
Just in case you skipped reading it, I will talk about something else a bit in order to give you another chance. My website and blog is 1 year old now! Yay!
I am not happy with the post frequency at this point, but it is still something. I hope to write more this year since I am trying to create more free time for myself.
Which I can use for my personal life and hobbies. Like writing a blog. Ok, I hope you did read the problem. Let's go towards a solution together, step by step.

### Step 1: Finding a solution, any solution.

What the title says. Of course the problem itself has a time limitation which we must meet. But for now let's put that aside.
Our aim first is just finding a way to count all the possible ways to split the message.
This should be a step you are taking when you are faced with a programming problem like this. Finding any way to solve the problem, no matter how naive it is.
The best way to go about this is thinking about how you would count the number of solutions yourself. Imagine this simple input:

~~~
ababa
a
aba
ab
ba
baba
~~~

The first thing one can do is just finding a word that can fit to the beginning of this message, in other words a word in the dictionary that is a prefix of the message.
"a", "ab" and "aba" are prefixes. So we should count the number of ways to split the message in these three cases and add those up.
Let's say we picked "a" as our first word. Then we are faced with the same problem again. We must find the words that are prefixes of the remainder of the message, namely "baba".
There are two such prefixes, "ba" and "baba". Similarly we can go with "ba". Then we end up with "ba", which only has the prefix "ba". Then we end up with nothing.
The message is over. So we add 1 to the counter in our head. Then go back to the last decision we made and change it. Namely, picking "baba" instead of "ba". This also leaves us with nothing.
Add 1 more. In general, we go over all words in the dictionary that are prefixes of the remainder of the message, then repeat with the remainder of the message after removing that word.

You might feel like that example was too simple, but my intention was showing you how to algorithm-ify the way you would normally solve this problem.
Now we can actually talk about how to actually implement this idea in code. We saw that the algorithm is just repeatedly picking prefixes until the message is over.
In other words, solution of the problem can be calculated from *subproblems* of the same form. Counting the number of ways to split the remainding message is actually a subproblem of the inital problem of splitting the entire message.
These types of problems can be easily solved recursively. All we need to implement is a way to find which words are prefixes of the message. Let's go with the most naive way again.
Just iterating over the entire dictionary and comparing each word letter by letter. When we find a hit, we just call the recursive function at the end of the prefix we found.
And we sum up the return values of these function calls and return that value. The base case for the recursion is returning 1 when we end up with an empty message.
I am not going to provide specific codes for these steps since you can actually see these steps in the final code.

Now that we have a way to count all the messages, let's calculate the time complexity.
Since we are counting all possible ways one by one, upper bound for complexity is the answer of the problem.
As you can see from the third example in the pdf file, the answer can be 2^N where N is the length of the message. Then for each possible splitting we go over entire dictionary for each word in the splitting.
This is really output dependent and not easy to calculate but it is at least MxL, where M is dictionary size and L is maximum word length, since we are at least going over all the letters in the dictionary.
Therefore time complexity is at least O(2^NxMxL).

### Step 2: Getting rid of obvious repetitions.

Now, we are trying to speed things up. Our first aim should be getting rid of that 2^N part since it grows FAST.
Let's see what we can observe about the recursive function we just wrote. It takes a remainder of the message and returns an integer.
To make it more concrete, we can say it takes in an integer that represents the starting point of a suffix of the original message.
This function is a *pure function*, meaning whenever we call it with the same parameters it gives the exact same output. [(More on pure functions here if you are interested.)](https://www.sitepoint.com/functional-programming-pure-functions/)
So we can actually cache the value we calculated when calculation is over. Then on future calls to this functions, we can just return the cached value. This idea is called dynamic programming, and it was the topic of this project.
I am not going to attempt teaching dynamic programming in this post. It is a huge topic. But I gave the general idea. You save the value you calculated for your input in a lookup table and just return the value on the lookup table on future calls with the same input.
This effectively reduces the time complexity to O(NxMxL) since the function can perform calculation at most N times. Once for each possible input between 1 and N.

And this solution, when implemented, could get full 100 points if implemented clean enough. This was my not exact intention when I prepared the project. I wanted this solution to get around 70 points since there are further optimizations to be made.
But because of my generousity about the limits for N,M and L this did not happen. And I will talk about the possible further optimizations on my next post. Where I will explain my solution that reduces the complexity to O(NxM+MxL) and another solution that came from a friend who was also student of the course last semester.
But before reading the next post, try to come up with it yourself. You need a way to stop repeating the same computations when checking which words in the dictionary are actually prefixes of a remainder of the message.

See you on the following post!