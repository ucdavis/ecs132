
# Homework 3

# Due

# Problem 1

Consider the parking space example, Sec. 4.2.2, but generalized:  The
probability of an open space is now p, and the destination location is
now d.  (We no longer will think in terms of blocks.  The spaces are
numbered 1, 2, 3, ..., and we start at location 0.)  Write the "d,p,q,r"
functions, with call forms

* dpark(p,d,i)  probability of parking i distance from destination

* ppark(p,d,i)  probability of parking at most i distance from destination

* qpark(p,d,q)  inverse of ppark (but see below)

* rpark(n,p,d)  simulate n parkings, generating n distances

As always with discrete random variables, the 'q' function is a little
tricky.  Note the following:

```,r
> dbinom(1,2,0.5)
[1] 0.5
> pbinom(1.1,2,0.5)
[1] 0.75
> qbinom(0.75,2,0.5)
[1] 1
> qbinom(0.76,2,0.5)
[1] 2
```

# Problem 2

Consider the board game example, Sec. 2.10.  Suppose we win $1 every
time we pass square 8.  Write a function with call form boardGame() that
uses Markov analysis to find the long-run proportion of time we are on
squares 1,2,...,8 (it will be 0 for square 3) and the long-run mean and
variance of our winnings per die roll.  The output will be a vector 
of length 10.

