

# ECS 132, Homework 2

Due Friday, May 5, 11:59 pm.

## Problem 1

This problem involves the Preferential Attachment Model (PAM).

* Write a function with call form

``` r
PAMsim(nGen)
```

It will simulate PAM, through time **nGen**, i.e. through the attachment
action of v<sub>nGen</sub>.  It will return an R list, with these
components:

- The final adjacency matrix, **adjMat**, of size m X m, where m = nGen + 2.

- A **attachHistory** vector, of length **nGen**.  Component i of that
  vector will be the index of the existing node that v<sub>i+2</sub>
  attaches to, say 5 if it attaches to v<sub>5</sub>.

* Write a function PAMemaxd(nGen), that uses simulation to find
the approximate expected value of the maximum degree in the graph at
time **nGen**.  It should call **PAMsim()**. 

## Problem 2

Monty Hall.  Say contestant always chooses Door 1.  (Thus C is not a
random variable.)  Also, contestant's strategy is to never budge; she
will always stick to her original guess.  But A is random among 1:3, and
H is as in the book.  Find EW, expected winnings.  Note:  This is NOT a
CONDITIONAL expected value.

## Problem 3

We have tags numbered 1,2,...,m.  We keep choosing tags at random, with
replacement, until we accumulate a sum of at least k.  We wish to find the
probability that it takes us s tag draws to achieve thi.s

Write a function with call form

``` r
tags(m,k,s) 
```

that uses recursive calls to find this probability exactly.  Note that
your function must be fully general, for any nonnegative integers m, k
and s.  (The probability will be considered 0 for nonpositive m, k and
s.)




