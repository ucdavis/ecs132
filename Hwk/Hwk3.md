
# Homework 3

# Due Tuesday, May 23, 11:59 pm

# Problem 1

Consider the parking space example, Sec. 4.2.2, but generalized:  The
probability of an open space is now p, and the destination location is
now d.  (We no longer will think in terms of blocks.  The spaces are
numbered 1, 2, 3, ..., and we start at location 0.)  Write the "d,p,q,r"
functions, with call forms

* dpark(p,d,i):  probability of parking i distance from destination

* ppark(p,d,i):  probability of parking at most i distance from destination

* qpark(p,d,q):  inverse of ppark (but see below)

* rpark(n,p,d):  simulate n parkings, generating n distances

As always with discrete random variables, the 'q' function is a little
tricky.  Note the following:

```,r
> dbinom(1,2,0.5)
[1] 0.5
> pbinom(1,2,0.5)
[1] 0.75
> pbinom(1.1,2,0.5)
[1] 0.75
> qbinom(0.75,2,0.5)
[1] 1
> qbinom(0.76,2,0.5)
[1] 2
```

# Problem 2

Consider the board game example, Sec. 2.10. To make things easier for Markov analysis, relabel the squares from 1 to 8 instead of 0 to 7. We now get the bonus by landing on square 4, not 3.

Suppose we win $1 every time we pass square 8.  Write a function with call form boardGame() that
uses Markov analysis to find the long-run proportions of time we are on
squares 1,2,...,8 (it will be 0 for square 4), and the long-run mean and
variance of our winnings per die roll.  The output will be a vector 
of length 10.

# Problem 3

Here you will develop a Markov model of a call center.

* Calls arrive, last for a random amount of time, and exit.

* Time is discrete, similar to the epochs in the ALOHA model.

* At the beginning of an epoch, each call currently in service either terminates
with probability p, or continues with probability 1-p.  The calls act
independently of each other, and through time.  Concerning the latter,
for instance, the probability of a specific call continuing through its
first epoch but ending in the second is (1-p)p.

* Near the end of an epoch, a new call arrives, with probability q, or
  does not, with probability 1-q.  Again, this is independent across
time, and independent of what happens to existing calls.

* There are r operators, and a waiting area for w calls on hold.  When a
  call ends, the operator will start one of the calls that had been on
hold.  A call that arrives to a full system is declined.

* The state space, {0,1,2,...,r+w}, represents the number of calls in the
  system.

* X<sub>n</sub> is the number of calls in the center at the end of epoch
  n.

Write a function with call form callCtr(p,q,r,w) that returns a vector
consisting of:

* The long-run proportion of declined calls.

* The long-run average number of calls on hold.

* The long-run average number of busy operators.
