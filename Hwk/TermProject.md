
# ECS 132 Term Project

## General requirements

* Due June 13, 11:59 pm.  

* You will seek instances in real world data in which our families
  of continuous distribution families represent the data well.  Please
restrict your analysis to those datasets.

* A professional-quality written report, prepared in [LaTeX](http://heather.cs.ucdavis.edu/~matloff/latex.html ), will be required.  This means clear writing, correct grammar, informative graphics (R only, please),attractive presentation and so on.

## Background

* You will need to pick up some R skills from my [fasteR
tutorial](https://github.com/matloff/fasteR), e.g. in Lesson 3.  

* You will also need my [fastStat
  tutorial](https://github.com/matloff/fastStat), say through Lesson
ESTDISTRS.  We will cover most of this in class, but **you should read
ahead, so as to not delay work on the project.** For this project,
mainly you need lessons MLEMM and ESTDISTRS.  Read the latter first to
get started.



## Use of the datasets

I would prefer that you use a dataset from [the repo for my other
class](https://github.com/ucdavis/FairMLCourse/tree/main/Data).
Most of the datasets in the repo are compressed data resulting from
calling **save()** in R.  These have '.rda', '.RData' etc. suffices in
their file names.  The paired function is **load()**.

As an example, try running the following from the subdirectory
**fairml**.

``` r
load('bank.rda',verbose=T) 
head(bank) 
hist(bank$age) 
```

Most of the datasets are fairly self-explanatory via their column
names.  In some cases, you'll need to dig a little; let me know if you
have trouble tracking down a particular dataset.

Another possible  source would be the 
[UCI ML Repository](https://archive.ics.uci.edu/ml/index.php).

## Your analysis

You will investigate each of the families normal, exponential, gamma and
beta.  For each one:

* Find some variable in some dataset that seems to be well approximated
  by the given family. Remember, this data is considered just a sample
from some (possibly conceptual) population, so it will not look exactly
like the given family (sampling variation).  Even more important, the
true density will not be exactly the same as one in the given family
(model bias).  We are merely looking for a good approximation.

*  Note:  The beta family has support (0,1).  In the case of a variable
with well-defined bounds, you can achieve this by scaling.  E.g. if
variable is always in the interval (1,5), you subtract 1 and divide by 4
to get a (0,1) variable.  But do this only if the variable has natural
bounds; do not simply use the min and max values in the data as bounds.

* Plot density estimates from this data, first a histogram using
  **hist()** (with **probability = TRUE**, to scale so that total area
is 1) and then with **density()** (apply **plot()** to the return
value).  The latter uses an advanced density technique that produces a
smooth curve, unlike choppy histograms.

* Next, find the MLE of the parameters of this family, then plot the
  resulting density, superimposing it on your plot from **density()**.

* Finally, do the same for the MM estimator (plot the MM-estimated
  density superimposed on the plot from **density()**).

* Based on the above, comment on the suitability of the given parametric
  family for approximating the population density for this dataset.

Note:  To save a plot image to a file, you may wish to use
the code in [my ECS 189G blog, May 19 0955](https://github.com/ucdavis/FairMLCourse/blob/main/Blog.md).

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
  vital.

* Package your files, i.e. **.tex**, **.pdf**, **.R**, image files,
  etc., in a file whose name is of the form **email1.email2....tar**,
  where each <b>emaili</b> is the UCD e-mail address of group
  member i, e.g. <b> bclinton.gwbush.bobama.dtrump.tar</b>.  Note the
  periods separating fields.  Don't get the address wrong!  Otherwise
  the grading script may not give someone credit.

* The **.tar** file must have no subdirectories.  (See the [Hwk 1
  specs](https://github.com/ucdavis/FairMLCourse/blob/main/Hwk/Hwk1.md)
on this.)

* You must include both the **.tex** file and the **.pdf** file that it
  generates.  Your LaTeX file must be named **ProjectReport.tex**, and
  the corresponding PDF **ProjectReport.pdf**.

* Submit your report to my **handin** site on CSIF (NOT the TA's
  site), username **matloff**, directory **132project**.

* Groups that put in a reasonable amount of time -- and thought! --
   almost always receive an A or A+ grade on the project.  Groups that
   do not complete the project usually get a D grade.  **PLEASE START
   EARLY!**
