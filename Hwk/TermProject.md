
# ECS 132 Term Project

## General requirements

* Due June 11, 11:59 pm.  

* You will be finding instances in real world data in which our families
  of continuous distribution families represent the data well.
    
* There are many choices in the dataset collection in the [GitHub repo
  of my other
  course](https://github.com/ucdavis/FairMLCourse/blob/main/Data).
  Please restrict your analysis to those datasets.

* A professional-quality written report, prepared in [LaTeX](http://heather.cs.ucdavis.edu/~matloff/latex.html ), will be required.  This means clear writing, correct grammar, informative graphics (again, R only, please),attractive presentation and so on.

* Though you'll write some supporting code, *this is not a coding
  project*.  It is *analysis*, with an emphasis on interpretation.

## Background

You will need to pick up some R skills from my [fasteR
tutorial](https://github.com/matloff/fasteR), e.g. in Lesson 3.  Lesson
ESTDISTRS of my [fastStat tutorial](https://github.com/matloff/fastStat)
will also be relevant.

## Use of the datasets

Most of the datasets in the repo are compressed data resulting from
calling **save()** in R.  These have '.rda', '.RData' etc. suffices in
their file names.  The paired function is **load()**.

As an example, try running

``` r
load('bank.rda',verbose=T) 
head(bank) 
hist(age) 
hist(bank$age) 
```

from the subdirectory **fairml**.

You will need to pick up some R skills from my [fasteR
tutorial](https://github.com/matloff/fasteR), e.g. in Lesson 3.  Lesson
ESTDISTRS of my [fastStat tutorial](https://github.com/matloff/fastStat)
will also be relevant.

## Details regarding your report and its submission

* Make sure the human grader (me) is in good mood when he grades.
  Follow directions!  Don't make the grading script crash!

* **DOUBLE-CHECK THAT YOU ARE MEETING ALL SPECS!**  Whoever does the
  actual turning in of your submission, impress upon him/her that this
  is a huge responsiblity that can affect everyone's grade. 

* Absolutely NO late reports will be accepted.  **As you near the
  deadline, keep submitting what you have** (each one will overwrite the
  last), so that at least you will get a lot of credit even if you don't
  finish. *Each team member has the responsibility of checking that this
  is being done.*

* Include a section listing each team member's contribution to the
  project -- who did what.  If a member did not participate, do not
  include him/her in this section, nor in the <b>.tar</b> file name.
  **Don't forget this section!**

* Don't skimp on time devoted to the writing.  **The phrasing matters!**
  This is true both in terms of having good, professional writing
  quality, but also in terms of *proper interpretation*, which will be
  vital in your report.

* Package your files, i.e. **.tex**, **.pdf**, **.R**, image files,
  etc., in a file whose name is of the form **email1.email2....tar**,
  where each <b>emaili</b> is the UCD e-mail address of group
  member i, e.g. <b> bclinton.gwbush.bobama.dtrump.tar</b>.  Note the
  periods separating fields.  Don't get the address wrong!  Otherwise
  the grading script may not give someone credit.

* The **.tar** file must have no subdirectories.  (See our Hwk 1 specs
  on this.)

* You must include both the **.tex** file and the **.pdf** file that it
  generates.  Your LaTeX file must be named **ProjectReport.tex**, and
  the corresponding PDF **ProjectReport.pdf**.

* Submit your report to my **handin** site on CSIF (NOT the TA's
  site), username **matloff**, directory **132gproject**.

* Groups that put in a reasonable amount of time -- and thought! --
   almost always receive an A or A+ grade on the project.  Groups that
   do not complete the project usually get a D grade.  **PLEASE START
   EARLY!**
