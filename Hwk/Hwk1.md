
# ECS 132, Homework 1

## Instructions

**Note carefully:**  Your submissiom must follow instructions exactly,
as your (at least preliminary) grade will be determined by the (R
language) auto-grading script.  Lack of adherence to instructions may
reduce your grade.

Submit a **.tar** file containing files **Problem1.R**,
**Problem2.R** and so on, and NO SUBDIRECTORIESz; the grading script
will run the command **tar xf** on your **.tar** file, and will NOT then
run **setwd()**; it will expect to see your files in the directory in
which the **.tar** file resided.

Each of your **.R** files must contain the specified function(s), with
no freestanding code.

## Problem 2

Say there is a bus line, with the first bus leaving the main station at
time X<sub>0</sub> = 0.  Subsequent bus departures are at X<sub>1</sub>,
X<sub>2</sub> and so on.  Let L<sub>d</sub> = X<sub>d</sub> -
X<sub>d-1</sub>, d = 1,2,...  Assume the L<sub>i</sub> are independent,
and P(L<sub>d</sub> = r) = p<sub>r</sub> (indexing starts at 1).  Denote
the buses by B<sub>1</sub>, B<sub>2</sub> etc.

A certain passenger comes to a certaion bus stop every day at time m.
(So, this time is not a random quantity.)  It takes v time for a bus to
reach this stop from the main station.  We are interested in the time W
the passenger must wait for a bus (which is 0 if a bus happens to arrive
at time m), and other related quantities:

* Bus 2 leaves the main station at time r.

* P(W = k)

* P(W = k | L<sub>1</sub> = q)

* P(U = 3), where B<sub>U</sub> is the bus boarded by our passenger of
  interest

* E(number of buses leaving the main station by time k)

* Var(number of buses leaving the main station by time k)

* E(number of buses leaving the main station by time m | W = k)

Note that each of these quantities are separate questions.  For
instance, though the first one talks abot W = k, that doesn't mean W = k
for the rest.

Write a function **ExactAnalysis()** (no arguments) that returns the
above quantities as a 6-element vector, for the following setting:

* i = 5

* p = (0.5,0.5)

* v = 3

* k = 1

* r = 3

* q = 1

Show your work in the function, in the form of a combination of code
comments and display of intermediate computations.

Write a function **busSim()** with the following call form

``` r
busSim(i,p,v,k,r,q,nDays
```

Here **nDays** is the number of days to simulate, i.e. the number of
rows in a "notebook" view of the problem.  It will again return a
6-element vector.
