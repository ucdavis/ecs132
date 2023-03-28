
# ECS 132, Spring 2023, Quiz 0

This is Quiz 0.  It will be different from the other quizzes,
which will be in-class (weekly in the disucssion section, and also in
lecture on the last day of class).

**Make SURE to read the instructions carefully.**

## Instructions

* You must use the [OMSI tool](https://github.com/matloff/omsi) to
  submit your quiz.  Make SURE to do a test run first, playing the role
of both the student and instructor, as explained in the OMSI docs. 

* This will be due 11:59 pm, April 11.  The TAs will start the OMSI
  server on April 3 (machine and port to be announced).  You may submit
at any time between April 3 and 11.  Don't leave it for the last minute;
keep in mind my slogan, "Computers never work." :-)

* You should be able to get an A+ grade on this quiz!  You are welcome
  to seek help from me or our TAs (you may ask more than once if
needed):

    Norm Matloff, nsmatloff@ucdavis.edu <br>
    Dylan Alberto Chima-Sanchez, dchimasanchez@ucdavis.edu <br>
    Lan Jiang, lanjiang@ucdavis.edu

    You are not allowed to discuss this quiz with anyone else besides
    the three names listed above.  Failure to adhere to this requirement
    will be considered **a violation of the code of academic conduct.**

* Prepare for this quiz by learning the rudiments of R, in my
  [fasteR tutorial](https://github.com/matloff/fasteR), and by reviewing
linear algebra, using my [linear algebra review](https://github.com/matloff/fastLinearAlgebra).  Both topics will also be covered in discussion section, Week 1, but of course in less depth.

* Quiz questions, both here and in future quizzes, will be labeled
  either "R code answer" or "Text answer."  In the former case: 

   - The OMSI grading tool will execute exactly what you 
   submit.  Accordingly, there should be NO non-R in your submission.

   - If the question asks for you to just write a function, that is all
   you must have in your submission.  If you would like to include test
   code, do so and run to check but comment it out before submitting.

   - Use R comment lines to show your work and explain your answer.

   - A question may ask you to "print" something.  This means, "print to
     the screen," i.e. use the **print()** function or equivalent.

   - When a question asks you to write code, it means it.  Don't compute
     something by hand and then merely submit the number.

   - You are not required to include error-checking unless specifically
     asked to do so.

## Regarding RStudio

Some of you may have been exposed to RStudio, an IDE for R.  It's
designed for noncoders, and in my opinion, VS Code is probably more
appropriate for CS people.  Personally, I find that IDEs in general just
get in my way, and I just use the Vim text editor with my own homegrown
macros.  It's up to you.

In any event, in terms of OMSI, it doesn't matter how you generate your
R code; OMSI doesn't know and doesn't care.

## The quiz questions

**Question 1:**  Consider the **mtcars** dataset, built-in to R.  Write
code that finds and prints the **hp** value in the third row of the
dataset.

**Question 2:**  Again with the **mtcars** dataset, write code that
finds and prints the mean **mpg** among cars having 6 or 8 cyclinders.

**Question 3:**  Again with the **mtcars** dataset, write code that
adds a new column, the horsepower/weight ratio, and prints the entire
new dataset, now 12 columns rather than 11.

**Question 4:**  I live 60 miles from campus, and 1.5 miles from my
nearest freeway exit.  As I exited the freeway, the dashboard said I had
averaged 34.2 miles per gallon on that trip (campus to freeway exit).
When I got home, the figure was 33.8 miles per gallon for the entire
trip (campus to my driveway).  How many miles per gallon did I get from
the freeway exit to home?  Print this figure.

**Question 5:**  Write code that finds the product of A and B below,
using the %\*% operator.

``` r
A <- rbind(1:2,5:6)
B <- rbind(1:3,5:7)
  # compute and print product here
```

**Question 6:**  Write a function that creates and returns an n x n
matrix whose row i, column j element is |i-j|.

``` r
ijMatrix <- function(n) 
{
   
  # add code here

}
```

**Question 7:**  Write a function that creates and returns the value of
a *quadratic form*, u<sup>t</sup> M u, for a vector u and matrix M.  The
result is a number.

``` r
quadForm <- function(u,M) 
{

  # add code here

}
```

**Question 8:** (Text answer.) What is the name of the matrix operation
that exchanges rows with columns?

