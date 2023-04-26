

# ECS 132, Homework 2

Due Friday, May 5, 11:59 pm.

## Problem 1

This problem involves the Preferential Attachment Model (PAM).

<UL>

<li>  Write a function with call form

``` r
    PAMsim(nGen)
```

It will simulate PAM, through time **nGen**, i.e. through the attachment
action of v<sub>nGen+2</sub>.  It will return an R list, with these
components:

- The final adjacency matrix, **adjMat**, of size m X m, where m = nGen + 2.

- An **attachHistory** vector, of length **nGen**.  Component i of that
  vector will be the index of the existing node that v<sub>i+2</sub>
  attaches to.  E.g. if v<sub>12</sub> attaches to 
  v<sub>5</sub>, then attachHistory[10] = 5.

<li>  Write a function with call form

``` r
    PAMemaxd(nGen,nReps)
```

that uses simulation to find the approximate expected value of the
maximum degree in the graph at time **nGen**.  It should call
**PAMsim()**. 

</UL>

## Problem 2

This problem concerns the Monty Hall example.  

Say the contestant always chooses Door 1 (always, meaning in many plays
of the game).  Thus C is not a random variable, while A and H still *are*
random variables.

Also, say the contestant's strategy is to never budge; she will always
stick to her original guess when the host offers her a chance to chage
her mind.

So A is randomly chosen (by the host or the producer of the game show)
among 1, 2 and 3, and H is as in the book.  

Say the car is worth $20,000 and the goats have $100 value.  You will Find
EW, the contestant's expected winnings.  Note:  This is a not a
*conditional* expected value.  You will write two functions, with call
forms

``` r
    exactEW()
```

and

``` r
    simEW(nreps)
```

that find the exact value of EW and its approximate, simulated value.
The two will serve as checks on each other.
## Problem 3

We have tags numbered 1,2,...,m.  We keep choosing tags at random, with
replacement, until we accumulate a sum of at least k.  We wish to find the
probability that it takes us s tag draws to achieve this.

Write a function with call form

``` r
tags(m,k,s) 
```

that uses recursive calls to find this probability exactly.  Note that
your function must be fully general, for any nonnegative integers m, k
and s.  (The probability will be considered 0 for nonpositive m, k and
s.)




