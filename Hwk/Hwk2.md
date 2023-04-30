

# ECS 132, Homework 2

Due Wednesday, May 10, 11:59 pm.

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

Here we will have d doors and multiple prizes, with different values according to a vector v. The length of v is less than d. Note that d and v are merely parameters of the problem, NOT random variables.

Say that, unknown to the host, the contestant always chooses Door 1 (always, meaning in many plays
of the game).  Thus C is not a random variable, while A and H still *are*random variables. Note that 
now A is now a random vector, whose component i is the door behind which the prize of value v[i] waits. There is nothing behind the other doors.

Also, say the contestant's strategy is to either accept the host's invitation to change her mind, with probability p, or stick with Door 1.

So A is randomly chosen (by the host or the producer of the game show)
among 1, 2 and 3, and H is as in the book.  

You will write a function with call form

``` r
    simEVarW(d,v,nreps)
```

that uses simulation to find EW and Var(W), where W is what the contestant wins (one of the values in v or 0).

## Problem 3

We have tags numbered 1,2,...,m.  We keep choosing tags at random, with
replacement, until we accumulate a sum of at least k.  We wish to find the
probability that it takes us s tag draws to achieve this. (As always, unless a problem specifically asks for a simulation, all probabilities, expected values and so on must be derived exactly.)

Write a function with call form

``` r
tags(m,k,s) 
```

that uses recursive calls to find this probability exactly.  Note that
your function must be fully general, for any nonnegative integers m, k
and s.  (The probability will be considered 0 for nonpositive m, k and
s.)




