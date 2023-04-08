
# ECS 132, Homework 1

Due Monday, April 18, 11:59 pm.

## Instructions

**Note carefully:**  Your submission must follow instructions exactly,
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

## Problem 1

The R distribution includes a famous dataset, **UCBAdmissions**.  As
with all functions and built-in datasets in R, you can read its "man
page" (manual) by typing a question mark:

``` r
> ?data(UCBAdmissions)
```

The data involve a lawsuit against UC Berkeley that accused UCB of
discriminating against female applicants for grad school.  This seemed
odd, given UCB's reputation as politically liberal, but the
seeming contradiction was resolved upon closer inspection of the data.
It turned out that the women were applying to more selective
departments, hence their lower overal acceptance rate.

The dataset is  an *array* of dimension 3, a "3-dimensional matrix,"
consisting of "layers" and rows/columns within layers.  (You may have
heard the term *tensor*.)

The **str()** ("structure") function is very useful in R:

``` r
> str(UCBAdmissions)
 'table' num [1:2, 1:2, 1:6] 512 313 89 19 353 207 17 8 120 205 ...
 - attr(*, "dimnames")=List of 3
  ..$ Admit : chr [1:2] "Admitted" "Rejected"
  ..$ Gender: chr [1:2] "Male" "Female"
  ..$ Dept  : chr [1:6] "A" "B" "C" "D" ...
```

So for instance the number of women who were admitted to Department D
was 131:

``` r
> UCBAdmissions[1,2,4]
[1] 131
```

Write a function **admissionsProbs()** that computes and returns a
vector containing the following probabilities:

* P(admit)

* P(admit | female)

* P(admit | female and Dept. B)

* P(admit | female and Dept. C)

* P(Dept. C | female)

* P(admit | female and (Dept. B or Dept. C))

* P(female | admit)

* P(female and admit)

* P(Dept. C or Dept. D)

Each line of the "notebook" represents the case of one applicant.  Of
course, we have only a finite number of "lines," so all the
probabilities you compute are estimates of the general situation at UCB
at the time.  Our data can be viewed as a sample from the conceptual
population of all potential applicants in that era.

**NOTE CAREFULLY:**  Express the probabilities as common fractions,
e.g. 5/18.  Of course, these will appear as decimal fractions when
printed out, but the numerator and denominator are important for
"showing your work," i.e. to show to the grader that you do understand
the issues here.

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
