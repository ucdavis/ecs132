
# ECS 132, Homework 1

Due Friday, April 21, 11:59 pm.

## Instructions

**Note carefully:**  Your submission must follow instructions exactly,
as your (at least preliminary) grade will be determined by the (R
language) auto-grading script.  Lack of adherence to instructions may
reduce your grade.

Submit a **.tar** file containing files **Problem1.R**,
**Problem2.R** and so on, and NO SUBDIRECTORIES; the grading script
will run the command **tar xf** on your **.tar** file, and will NOT then
run **setwd()**; it will expect to see your files in the directory in
which the **.tar** file resided.

You can create the **.tar** file on, say, CSIF, by running

> $ tar cf xxxx.tar names_of_your_files

where 'xxxx' consists of group members' official UCD e-mail addresses, without the '@ucdavis.edu', separated by periods. E.g. 'ajones.blee.tar'.

Use the **handin** app in CSIF to submit your file. Submit to Lan, **jiang012**. For instance,

> $ handin jiang012 ecs132Hwk1 ajones.blee.tar

says, "Add my file **ajones.blee.tar** to jiang012's **ecs132Hwk1** handin
directory." (You can check that it got there; see the **handin** man
page.)

Each of your **.R** files must contain the specified function(s), with
no freestanding code.

## Problem 1

The R distribution includes a famous dataset, **UCBAdmissions**.  As
with all functions and built-in datasets in R, you can read its "man
page" (manual) by typing a question mark,

``` r
> ?UCBAdmissions
```

and it is the subject of numerous examples on the Web.

The data involve a lawsuit against UC Berkeley that accused UCB of
discriminating against female applicants for grad school.  This seemed
odd, given UCB's reputation as politically liberal, but the
seeming contradiction was resolved upon closer inspection of the data.
It turned out that the women were applying to more selective
departments, hence their lower overall acceptance rate.

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

Say there is a bus line, and we have a passenger of interest who arrives
at a certain bus stop every day at time m.  (So, m is not a random
quantity.)  It takes v time for a bus to reach this stop from the main
station.  

The start of a day is considered time X<sub>0</sub> = 0. Bus i leaves the main station at time 
X<sub>i</sub>, i = 1,2,3,...  Set L<sub>d</sub> = X<sub>d</sub> - X<sub>d-1</sub>, d = 1,2,3,... 
The L<sub>i</sub> are independent, and P(L<sub>d</sub> = j) =
p<sub>j</sub> (indexing starts at 1).  Denote the buses by B<sub>1</sub>,
B<sub>2</sub>, B<sub>3</sub> etc.  

So, the parameters that control the probabilistic behavior
of the bus system are:

* p: a vector of probabilities of delay times between successive buses

* v: the length of time it takes for a bus to reach the stop of our
  passenger of interest from the main station (assumed < m)

We are interested in the time W our passenger of interest must wait for a
bus (that is 0 if a bus happens to arrive at time m), and other related
quantities (m, k, etc. will be the parameters of the quantities you
are asked to find):

* P(W = k)

* P(Bus 2 leaves the main station at time r)

* P(W = k | L<sub>1</sub> = q)

* P(U = 3), where B<sub>U</sub> is the bus boarded by our passenger of
  interest

* EW

* Var(W)

* E(B<sub>U</sub>)

* E(number of buses leaving the main station by time m)

* Var(number of buses leaving the main station by time m)

* E(number of buses leaving the main station by time m | W = k)

Note that these quantities are separate from each other.  For instance,
though the first one talks aboutt W = k, that doesn't mean W = k for all
the rest.

Write a function **ExactAnalysis()** (no arguments) that returns the second and third of the
above 10 quantities as a 2-element vector, for the following setting:

* m = 5

* p = (0.5,0.5)

* v = 2

* k = 1

* r = 3

* q = 1

Show your work in the function, in the form of a combination of code
comments and display of intermediate computations.

Write a function **busSim()** with the following call form

``` r
busSim(m,p,v,k,r,q,nDays)
```

to find the above-listed 10 quantities via simulation.  Of course, the
arguments m, p and so on here are general, not the specific values used
in **ExactAnalysis()** above.

Here **nDays** is the number of days to simulate, i.e. the number of
rows in a "notebook" view of the problem.  It will again return a
10-element vector.

# Example

Here is the solution of one of the questions above:

``` r
P(B_2 leaves the main station at time 3) =
P((B_1 leaves at time 1 and B_2 leaves at time 3) or
  (B_1 leaves at time 2 and B_2 leaves at time 3)) = 
P((L_1 = 1 and L_2 = 2) or (L_1 = 2 and L_2 = 1)) =
P(L_1 = 1 and L_2 = 2) + P(L_1 = 2 and L_2 = 1) =
P(L_1 = 1) P(L_2 = 2) + P(L_1 = 2) P(L_2 = 1) =
(0.5) (0.5) + (0.5) (0.5) =
0.5

```

And here is a (very) partial writeup of **busSim()**, calculating only
P(W = k):

``` r
# in our "notebook," 1 line = 1 day

busSim <- function(m,p,v,k,r,q,nDays)
{
   wVals <- vector(length=nDays)  # set up space for the Ws
   for (day in 1:nDays) {
      wVals[day] <- generateW(v,p,m)
   }
   # T and F treated as 1 and 0; mean of 1s and 0s
   # is proportion of 1s
   return(mean(wVals == k))  
}

generateW <- function(v,p,m) 
{
   tot <- v
   while (1) {
      tot <- tot + generateL(p)
      if (tot >= m) break
   }
   return(tot - m)
}

generateL <- function(p) 
{

   # e.g. if p = (0.2,0.2,0.6), choose 1 number at random from the set
   # 1,2,3, with probabilities 0.2, 0.2 and 0.6, respectively
   sample(1:length(p),1,prob=p)
}

```

# General Note

This is not a programming course.  It's a math course whose concepts are
illustrated via coding.

As such, please don't obsess over "edge cases" (also known as "corner
cases," and as "pathological cases" in math).  The test cases that the
graders use will not (deliberately) be chosen in order to "get you."

