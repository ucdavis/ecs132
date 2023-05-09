
# ECS 132 Blog

**Spring 2023**

**May 8, 2010:**

Some tips regarding Problem 3.
* A recursive algorithm exploints a *mathematical* relation.  Your first
job must be to develop that relation. **DON'T WRITE ANY CODE YET!**

* So, you must develop a *mathematical* equation first.  Keep your
laptop closed!  Stick to pencil and paper.

* The equation will be something lib f(n) = f(n-1) + f(n-2) for
Fibonacci numbers.  Note the form!  The function is being evaluated on
both sides of the equation, but with different arguments.  Your job is
to find such a relation for **tags()**.

* To guide your intution, work out a small case by hand, again using
pencil and paper.  Ask our famous question, "How can it happen?" and
then follow our famous path, "Break big events down into small events."

* You'll have *and*s and *or*s.  The latter will bring you sums, and the
former will then be converted with the mailing tube P(A and B) =
P(A) P(B | A).

* The key will be to recognize that P(B | A) here will actually be
**tags()**, evaluated at new arguments!  That's how you'll get a
Fibonacci-like relation.
 The coding will then be easy, though the base case might be a little
delicate.  Just implement your equation, just like the Fibonacci number
case.  Do NOT think of the tree of calls that occur; the language, in
this case R, handles that for you, behind the scenes.

* Your first try will likely be incorrect, resulting in either wrong
answers or a never-ending call chain.  In debugging, start with a small
case, and **WALK THROUGH YOUR CODE USING A DEBUGGING TOOL!!!!**




**May 8, 0920:**

As noted in class, you should devise little experiments to check your understanding of various functions and concepts.

For instance, suppose you are not sure what the p** functions do, e.g. **pbinom**. Try a little call on the R command line, say:

```,rc
> pbinom(1,2,0.5)  # does this really give the probability of at most 1 head out of 2 tosses of a coin?
[1] 0.75  # yes
```
**May 6, 0810:**

In Question 2 of the Thursday Quiz, the 4 parts were not graded separately, but rather in terms of the overall view of how a student's answers reflect general understanding of the course concepts. If you had 3 of 4 parts correct, you should have gotten 10 or 15 points; if you got only 5, please let me know, and I'll correct the score, and also correct the letter grade if it changes under the new score.

BTW, note that in computing course grades, your letter grade is all that counts; your actual numerical score does not enter into the computation. Again, see the course [Procedural Information site](https://github.com/matloff/nmGeneralCourseInfo/blob/master/RulesAndProcedures.md) for this and other important information.

**May 5, 2320:**

The grades for the Thursday Quiz 3 have been mailed out, and the solutions posted on our repo.

Scores ranged from 5 (1 student) to 100 (4 students), out of 50 who took the Quiz.

If you feel you were undergraded on some problem, please feel free to contact me, and 
I will take another look.

Again, make sure you read the blog posts of May 5 0925 May 4 1050; and May 2 2135, with 
important information about Quizzes and course grade policies.

**May 5, 0925:**

Important news regarding Quizzes:

* I mentioned that sometimes in a course, I drop the lowest 3 Quizzes,
  rather than 2.  I've decided to do so for our course.

* In Quiz 4, at least one question will be a variant of one in Quizzes 3
  (could be either Tuesday or Thursday). 

* In Quiz 4, at least one question will involve the parking space
  example.

**May 3, 1955:**

The following may help you visualize Problem 2 in our Homework.

Say you're the host.  Prior to the time of the game, you've got to
decide:

* (a) how many prizes to have (there was just one in the original
example) 

* (b) what value prizes do you want to have

* (c) which doors you want to place the prizes behind

Your decisions regarding (a) and (b) are then the vector **v**.

You will randomly choose doors for (c), and these door numbers are then
the vector **A**.  (Remember, in the original problem, **A** was just a
scalar, but now it is a vector, of the same length as **v**.)

As host, you'll need to have at least two doors with no prize behind
them.  This is necessary, because in tempting the contestant to change
her mind, you'll open a door other than the one she guessed but also
other than the ones that do have prizes.  This forces the length of
**v** to be less than or equal to **d-2**.

**May 3, 1050:**

I plan that next week's Quizzes, both Tuesday and Thursday, will include
problems in the setting of the committee example covered in yesterday's
lecture.  The questions will cover new concepts, e.g. probability mass
functions, but in the context of that example.

For instance, a question could ask:

> Write a function with call form **pmm(k)** that returns the probability
> mass function of the random variable **M** in the committee example.

The solution would be

```,r
pmm <- function(k) 
   # number of possible committees with k men and 4-k women),
   # divided by the number of all 4-person committees
   choose(6,k) * choose(3,4-k) / choose(9,4)
```

**May 3, 1035:**

There is a wealth of further examples for our course in our old Quizzes,
including solutions.  Though I previously gave you a link to all the
files, I have now uploaded them to our [GitHub
repo](https://github.com/ucdavis/ecs132/tree/master/Old132Quizzes) for
your convenience.  

You can clone the repo on your local machine, and among other things
do **grep** searches.  For instance, yesterday we covered the concept of
**probability mass function** in lecture, and you may wish to see how
that notion might turn up as a Quiz question.  So you could run

```
grep 'probability mass function' *Questions.txt
```

and then look at the questions that **grep** finds, if any.

**May 3, 0815:**

If you had an answer of 0.25 for Problem 4 on yesterday's Quiz, you will
get full credit.  Please e-mail me.

**May 2, 2135:**

The Tuesday Quiz 3 is now graded, and solutions placed as usual in our
GitHub repo.  Scores ranged from 0 to 90 (there were several at both
ends of this range).  A few comments:

* Problem 1 relied on just an intuitive understanding of independence, and
  it was placed at the first problem, generally intended as the easiest.
It was not difficult, but it did have its subtleties.  For example,
the pair of random variables in choice (a) was NOT independent; the
attachment action of v3 will affect that of v4, since the probabilities
faced by v4 will depend on what v3 does.  If you got at least 15 points
here, consider that a good score.

* Problem 2 was a very straightforward application of our basic E(X)
  formula.  The vast majority of you got this right.

* Problem 3 was a slight variation of an example in class.  And by the
  way, that example in class came from a question that a student asked
in class.

* Problem 4 just used mailing tubes, but required a lot of computation.
  I think that many students just ran out of time.

I should review how our course grades work:

* The basic formula is

    course grade = 0.60 x Quizzes grade + 0.20 x Homework grade + 0.20 x
    Term Project grade

* Your 2 lowest quiz grades (letter grades) are thrown out.  In some
  courses, I actually end up deciding to drop the lowest 3.

* Term projects (done in your Homework Groups) of high quality are
heavily rewarded, boosting your course grade 2 or even 3 notches
about what the above formula gives.  (A notch is a + or -, e.g.
an A is 2 notches above B+.)  Just yesterday I was showing some
colleagues an example of a student in a previous course that had
Quiz grades of D, A, C+, C+, A-, C, B- yet actually ended up with an A
in the course.


**May 2, 1800:**

A couple of students asked me whether they could use helper functions in Problem 3.  The answer is yes, providing your solution is recursive.  However, my recommendation is to NOT do so; it isn't necessary, and you probably would just needlessly make things more complex.

Note:  Though the function tags() is a probability, it still is a function.  Thus the principle is no different from, say a recursive computation of Fibonacci numbers.  You need to construct an equation (write an equation first, NOT code yet) that expresses tags() evaluated at m, k and s in terms of tags evaluated at one or more other sets of parameters.

**May 2, 0955:**

Please read the important message below from Lan right away. Also, NOTE CAREFULLY that
during interactive grading, you will be asked questions **both about your homework 
submission and about the course in general.** The latter is just as important as
the former.

   "Dylan has created a time slot booking page on 
   [Google Calendar](https://calendar.app.google/6W8788hRz1XBb4LRA)
   for interactive grading...We plan to have interactive grading happening 
   at May. 3rd 1-4 pm, May. 5th 10 am - 3 pm, and May. 8th 1-4 pm."

**May 1, 2045:**

In interactive grading, each group will be asked different questions, but
there may be some overlap.  Do not divulge to other groups the questions
asked of you.

**May 1, 1550:**

I have added clarification to Problem 2.

Also, in Quiz 1, Tuesday section, if you answered (2.2) to Problem 1 but did not get credit, let me know and I'll fix it.

**April 30, 1530:**

Earlier I stated that the statement of Problem 2 in the Homework would be changed. It is now changed, and ready for your work.

**April 30, 1010:**

In last Thursday's lecture, I mentioned the subject of course grades varying widely from one instructor to another. In that light, note that I gave some numerics regarding my own grading standards, in [our FAQs](https://github.com/ucdavis/ecs132/blob/master/FAQs.md). You may wish to review that statement.

**April 30, 1005:**

R's **repeat** function is very useful for building certain types of vectors, e.g.

```,r
> rep(8,3)
[1] 8 8 8
```

**April 30, 0940:**

In the coming week's Quizzes, make sure to be ready to compute the expected value and variance of quantities in our examples, e.g. E(L1) in the bus model.

**April 29, 2330:**

The function tag() is a probability:

tags(m,k,s) = P(it takes us s tag draws to accumulate a sum >= k)

Note that this is an unconditional probability, rather than a conditional one, though some conditional probabilities will turn out to play intermediate roles.

As you know, recursion involves finding a relation between a function evaluated at one set of arguments, and the same function evaluated at other arguments. Our general solution pattern of "break big events into small events" will be prominent in the solution.

Recursion coding is often challenging. I strongly recommend that you review how recursive function calls work (e.g. ECS 36C or its community college equivalent, whatever course you took) before starting on the problem.

**April 28, 1335:**

Very sorry, but I will have to change the wording of Problem. Please don't work on that one yet.

**April 28, 1020:**

I've pushed back the Hwk 2 due date to May 10.

**April 27, 1605:**

Some remarks on IDEs:

An IDE should make one more productive, not less.

In general, I am not a fan of IDEs.  I've tried many, many of them, in
languages C/C++, Python and R, and have always found that I am much more
productive by just using the Vim text editor--WITH my [homegrown Vim macros](https://heather.cs.ucdavis.edu/Vimrcs/).

In R, for instance, if I want to write a 'for' loop, I just type 'frl', and Vim automatically expands it to

```,r
for (i in 1:n) {
}
```
To create a matrix, I type 'nmm', and Vim give me

```,r
matrix(nrow=,ncol=)
```

Small things, yes, but it saves me time, allowing me to focus better on the coding itself, and avoids future arthritis in my fingers. :-)

Of course, Vim automatically supplies me (in base form, i.e. not needing my own macros) with syntax highlighting, code completion etc., which the IDEs do. But the IDEs don't give me the ability to write macros.

Most of my macros are 1- or 2-liners, very easy to devise, but Vim actually allows you to write more elaborate macros in Python. Note, I didn't mean one's usage of Vim to edit Python; instead I'm talking about using Python to extend Vim, for usage in editing files in any language. Indeed,[Vim plugins](https://vimawesome.com/) tend to be written in Python.

So the big advantage of Vim is that it allows me to customize my work environment, whether it be for my work in R, Python or LaTeX.

Obviously this is a matter of keen personal preference. Most professional deelopers do use an IDE, but many use Vim. The latter is not just something thrown into a beginning programming class as a "historical example."


**April 27, 1005:**

Please note that when a quiz or homework problem states something like "Use function X, Package Y etc.", then it is a requirement unless it explicitly says it is a suggestion.

**April 26, 1845:**

I've stressed the importance of submitting work using the correct e-mail address--the one to which I send you the "New blog post" announcements--because all of our course records are indexed by that address.

If you use an erroneous address, it's vital that you let me know.  I will fix it and you will receive full credit.

If on the other hand, I do not know about the error when I make out the course grades, it will be difficult to fix with a grade change later on.  It "probably" will be fixable, but we can't count on what the campus does.

**April 26, 1430:**

Homework 2 is now ready!

Please heed the blog post of April 18, 2045, in the statement reading in part "1 week before the due date AT THE LATEST."

**April 26, 0850:**

Simon Adds:

One of the most important cocepts in programming languages is that of a strongly typed language. In C/C++, for instance, one must a variable and its type before using it, and there are definite rules about mixing types.

Languages such as Python and R are much looser, but even they can require much care on the part of the programmer. E.g.:

```,rc
> f <- function(a,g) g(a)
> f(3,sqrt)
[1] 1.732051
> f(3,sqrt(12))
Error in g(a) : could not find function "g"
```

What happened? The second argument **g** of the function **f** was itself a function. In the first example, we used g = sqrt. Since **sqrt** is indeed a function, it worked fine. But in the second example, we used g = 1.732..., which is NOT a function, and things blew up.

So the distinction between a *function* **f** and a *call* to **f** is not a matter of pickiness; it is a *practical* issue, affecting whether code runs properly or produces an error.

Unfortunately, all this is complicated by the general custom in the CS field of using parentheses to signify functions. E.g. if **h** is a function, people often refer to it as 'h()', using the parentheses to tell people that **h** is a function. But as you can see, though one might do this in informal conversation, one must be very careful in actual coding.

This and the previous post address the fact that on Tuesday's quiz, many students incorrectly gave the **replicate** function as an example of a function that has a function argument.

**April 25, 2045:**

Remember the other day when I mentioned the kids' game, Simon Says, to illustrate the supreme necessity in the CS world for precise thinking? Consider this code snippet:

```,rc
> args(replicate)
function (n, expr, simplify = "array") 
> replicate(5,sqrt)
[[1]]
function (x)  .Primitive("sqrt")

[[2]]
function (x)  .Primitive("sqrt")

[[3]]
function (x)  .Primitive("sqrt")

[[4]]
function (x)  .Primitive("sqrt")

[[5]]
function (x)  .Primitive("sqrt")

> replicate(5,sqrt(3))
[1] 1.732051 1.732051 1.732051 1.732051 1.732051
> class(sqrt)
[1] "function"
> class(sqrt(3))
[1] "numeric"
```

The second argument of **replicate()**, **expr**, is an R expression, something to be computed. Well, sqrt(3) can be computed, but sqrt cannot. In other words, Simon Says, "There is a huge difference between a function and a call to that function"; different animals.

**April 24, 1430:**

Following up on the post of April 18, 2300:  In a line like

```,rc
f <- function(x) x^2
```

the expression 'function' is actually a function! I like to say, whimsically,

"The function of the R function named 'function" is to build functions."

So here, on the right-hand side of the assignment, we build a function, then assign it to **f**.

And yes, the '<-' and '^' are functions too. E.g.

```,rc

> 3^2
[1] 9
> '^'(3,2)
[1] 9
```

**April 21, 1615:**

Postscript: a major problem was that that **print()** call was incorrectly specified, missing the **nreps** argument. My bad. Most students just went ahead and added it.

In terms of questions you can ask the TA during a Quiz, it would have been quite reasonable to ask the TA, "Is the **nreps** argument missing here?" By contrast, please don't ask a question like "My code won't run. What's wrong?"

**April 21, 1545:**

Well, miscommunications can occur... :-)

In my blog post of April 20, 0950, I reminded everyone that in Quiz questions with R code answer, you MUST make sure your code runs and prints. It's no coincidence that in yesterday's quiz, there was an explicit **print()** call in the code.

Unfortunately, Dylan didn't notice that, and told students that they could comment-out the **print()** call. So, several students lost points even though their code was mostly correct.

Even more unfortunately, those students chose to believe Dylan instead of me! Dylan is a super-nice guy, but I'm offended. :-) Just kidding. 

But there was more. The reason those students asked Dylan in the first place was that actually their **print()** call was wrong. IOW, those students were asking Dylan to debug their code for them--in a Quiz! Please don't do that.

Anyway, if you were one of those students, you are welcome to ask me to take another look at your solution, for possible increase in points.

**April 21, 1500:**

Sorry, I don't think my Homework submissions directions were clear. Put all your files, named **Problem1.R**, **Problem2.R** and so on, into a **.tar** file. Here's the part I didn't make clear, the file name. It consists of your official UCD e-mail addresses, separated by periods. So e.g. if a Group's members have UCD addresses 'ajones@ucdavsi.edu' and 'blee@ucdavis.edu', then your **.tar** name would be 'ajones.blee.tar'.

I've made corresponding clarifications in the Hwk 1 specs.

**April 21, 1410:**

Quiz solutions are now in our course GitHub repo.

**April 20, 2015:**

As I've explained in class, all your course records, which are handled
by scripts, are indexed by your official UCD e-mail address.  If you
give some other e-mail address for some item (Quiz, Homework, Term
Project), you risk not getting credit for it.  The human grader MIGHT
notice a problem, and correct it, but this is not guaranteed.

Please make sure you use the UCD address at which you have been receiving mail
from me.

**April 20, 0950:**

I'm grading Quiz 1, Tuesday section, right now, and have a few comments:

* When a Quiz question says, "R code answer," it means it! Your submission will be executed by the grading script, and if your submission is English, the script will choke. If your submission has no output, the script will think your code was wrong. The human grader will take a look, but without output you already have trouble.

* Read the question carefully--extra carefully if you are not a native speaker of English. Words like "the," difference between singular and plural forms, etc. can make a big difference in meaning, and can serve as hints on how to solve the problem.

* Similarly, make sure your answer is addressing the question that was asked. If say you are asked about the square of a matrix, your answer should discuss the square. It may be important to also discuss the role of the original matrix, but only as preparation for discussing the square.

* If you are asked for the probability of something, rather than the approximate value, don't use simulation. The official course rules state,

> Note for ECS 132: In numeric problems, exact answers are required, not simulation, unless the latter is specified.

I'll post some more comments later, after doing more grading. 

BTW, remember that your two lowest Quizzes (in letter grades) are thrown out in computing your final course grade.


**April 19, 2255:**

Notes on debugging, both in general and in R:

* Don't use print statements to debug!  Use a debugging tool.

* Any good IDE will have a built-in debugging tool, e.g. VS Code
  (Python, R, whatever) or RStudio (R).  The developers of those IDEs
put them there for a REASON!

* Or use the underlying debugging tool directly, e.g. **gdb** 
(C/C++), **pdb** (Python) or **debug()** (R).

* Use my Principle of Confirmation: Step through your code in the
  debugging tool.  Check variables etc. as you go along, **confirming**
that "what you think is true, IS true."  Eventually, one will not
confirm, and you will then have at least found the location of the bug.

**April 19, 1645:**

As I have said, all the Quizzes are open-book, open notes. You can bring in anything on paper you wish, say your Homework solutions, or incorporate them into the PDF file for your textbook.

**April 19, 1415:**

The other day, I mentioned I would be postponing the Hwk 1 due date, and I did change the actual homework specs file accordingly. But just in case someone didn't check thst file, I'll say it here too: The new date date is Friday, 11:59 pm as usual. 

**April 19, 0845:**

In the Procedural Information document (linked to by the Syllabus in our class repo), it says, "class attendance is vital to doing well in the course." **If you miss many lectures, it is likely that you will get a poor grade in the course.** I do recognize, though, that sometimes it will be necessary for you to miss class. If so, you are welcome to e-mail me to ask what pages of the book I covered in that lecture.

One thing I mentioned in class yesterday is that I do not believe human intelligence has a genetic component, and thus everyone can do well in this class. If you do the reading nonpassively, spend thoughtful time on the homework, and yes, go to class, you will get an excellent grade in the course.

**April 18, 2300:**

A note on interpreted language and code speed:

Consider the code snippet

``` r
for (i in 1:n) {
   tot <- tot + x[i]
}
```

as compared to 

``` r
tot <- sum(x)
```

making use of R's built-in function **sum()**.

In that first snippet, there are function calls galore.  As I mentioned
in class today, '+' is actually a function!

``` r
2+3
```

is actualy 

``` r
'+'(2,3)
```

But not only that, but also '[', '<-' and ':' are functions!  R is
definitely what is called a *functional language*.

Now, as you learned in ECS 50, function calls have substantial
*overhead*.  The arguments must be placed on the stack, followed by the
return address.  If the body of the function is short, then the overhead
becomes a substantial fraction of the run time of the call.

Moreover, depending on implementation, in each iteration of the above
loop, the R interpreter may be doing a lookup to determine where in
memory **x** and **tot** are.  That would be really costly.  By
contrast, if R were a compiled language, that lookup would be done only
once, at compile time.

Similarly, the **sum()** function is straight C, so we (probably) have
no further function calls involved.

Remember, when you do something in Python, say

```
$ python x.py
```

you are not executing **x.py**; you are running the Python interpreter,
a C program that happens to be named 'python'.  It does the various
lookups needed for the lines in **x.py**.  So again, slow, and again, a
need to vectorize.

Some speed improvement is made by the use of Python *byte code*.  When
you "run" **x.py** the first time, it may produce a file **x.pyc**,
containing the byte code.  This is "machine code" for a mythical "Python
machine." In subsequent runs, the Python interpreter
will execute on the byte code, at least free of lookups, though still
slow because it is running the Python machine.  In recent years, the R
interpreter has been doing something similar.


**April 18, 2250:**

To illustrate Bayes' Rule, look at Eqn. (2.38) and those following it.

Let's first rewrite (2.67) as

P(U | V) = P(U) P(V | U) / [P(U) P(V | U) +  P(not U) P(V | not U)]

so that the B in (2.67) doesn't get confused with the B for bonus roll
in (2.38).

On the left-hand side of (2.38), we have

P(U | V)

where U is B > 0 and V is R+B = 4.  

Now look at the numerator of (2.40).  It's

P(V and U) 

which by our mailing tube is 

 P(V) P(U | V)

This already is beginning to look like (2.67).  And in fact, the
denominator of (2.40) is exactly the denominator of (2.67), again after
applying the same mailing tube.

So, Bayes' Rule is just a formalization of what we did in
(2.38)-(2.40) and in (2.64)-(2.66).   In other words, it's just a short
cut designed to save steps.

**April 18, 2045:**

As I emphasized in my message of April 14, 1820, Group collaboration is
essential in this course.  Today I had to contact one student to remind
him/her of this.

Each member of your Group should make a serious start on a Homework
assignment 1 week before the due date AT THE LATEST, and should get
together at that time to plan how to operate in the remaining time.

As I have said, there may be some variability regarding math or coding
skill among Group members, but everyone must do their best to
participate.  Remember, even if you think about a problem for a long
time but don't come up with a solution, you will have greatly deepened
your insight.

**April 18, 1605:**

Things apparently went smoothly for most but not all students in today's
Quiz.  Here are some announcements.

* Making Quiz 0 take-home was supposed to prevent OMSI problems in
  subsequent Quizzes.  Maybe there were VPN issues for some students.

* There was also the issue of using a PDF viewer from within OMSI.  As
  you know, disallowing the use of any apps besides OMSI is an
anti-cheating measure in OMSI, e.g. to prevent a student from e-mailing
someone during a Quiz etc.  But I did not realize that Windows does not
come with its own PDF viewer, and that Windows refers its users to the
Web browser, which could be used for cheating.  I actually was rude to
one student after class in saying that students are not allowed to use a
browser during a Quiz.  I apologize to him for that, and told Lan that
for today's Quiz only, students could use a browser.  But everyone who
is on Windows, please install Acrobat or whatever *before your next
Quiz,* whether it be this Thursday or next Tuesday.

* If you are in the Tuesday section and had OMSI problems today, you can
  take the Thursday Quiz this week if you wish.  Let me know before I
grade today's Quiz, probably tomorrow evening.

* Make sure to do a full test of OMSI, where you play the roles of both
  the instructor (you run the server) and the student (you run the
client). Run the server on CSIF and the client in a campus classroom,
for the most realistic test.  Be sure to test the PDF viewing aspect as
well.


**April 17, 2150:**

Picture yourself teaching someone to program.  You tell them about
arrays, loops and so on.  They then ask you, "When do I use arrays?"
Of course you know there is no good answer, because *programming is a
creative process*; there are no rules telling when to use arrays, etc.
All you could tell this person is 

> Arrays, loops, if-then-else, and so on make up your programming toolkit.
> You then must think how to creatively combine these tools into code that
> accomplishes your goal.  And it is indeed creative, as there are many
> possible code implementations that will accomplish your goal; different
> peple will come up with different code to achieve the same goal.

And that's true even more so for solving probability problems,
conducting statistical analyses, and developing machine learning prediction
models.  It's a creative process.  Your "toolkit" starts with the
mailing tubes, and then on the distribution models, ML algorithms and so
on.  There is no "formula" for any of this.  You try something, and if
you find out it isn't useful, you try something else.

**April 17, 2110:**

Below are notes I made for a student during my office hour today.  

The experiment here is to flip a set of 20 coins, each of which has
probability 0.1 of heads.  Let H denote the number of heads we get.

E(H)--by definition--is the long-run average in the H column of the notebook.
We will later learn how to derive the fact that E(H) = 2 here, but for
now, just take it as true (and intuitively plausible).

The second column is labeled "squared distance of H to its mean."  Its
mean is 2, so these entries are (2-2)^2, (11-2)^2 etc.  Var(H)--by
definition--is the long-run average of these squared distances.

As noted, a simulation merely puts into code what we have in the notebook.
So for Hwk 1, Problem 2's question about E(W), we have a W column, and
our code is finding the long-run average of this column.  In code terms,
we are simulating nDays days of bus operation, corresponding to nDays
lines in the notebook.  Our code will have nDays iterations, in each
which we generate W and add it to our running total.  Our (approximate
value of E(W) is then that total, divided by nDays.

Now, what about Var(W)?  In the notes in the picture, we would have
squared distances as (W - E(W))^2, one on each line.  Var(W) is then
(approximately)  the long-run average of those squared values.  So our
code would then have a *second* loop to compute this long-run average.
The reason we would need as a separate loop is that the squares in the
second column of the notebook *depend on first finding the average of
the first column.*

However, there is a trick, which is a mailing tube that we will cover
soon:  For any random variable X, Var(X) = E(X^2) - (E(X))^2.  So, in
our first loop, we can find running totals of both W and W^2, obviating
the need for a second loop.  You are not required to use this trick, but
you may do so if you wish.

**MAKE ABSOLUTELY SURE YOU UNDERSTAND ALL THIS, THE "WHY" OF EVERY STEP
RATHER THAN MERELY THE "HOW."**  This is vital to your doing well in the
course.  *If you master this--i.e. get to the point at which you can
cogently explain it to your classmates-- you will be will on your way to
getting an excellent grade in the course.*

Note:  For the exact analysis in this problem, I had intended that you
compute only 2 quantities, not 10.  I've changed the problem to have you
compute only the second and third quantities in the list.

![alt text](ohnotes.png)


**April 17, 1830:**

For any Quiz, the lecture and reading coverage is all material through the most recent lecture, but not the same day's lecture. For our class, the coverage for Tuesday Quizzes is the material through the preceding Thursday's lecture, while for Thursday Quizzes, it is the material through Tuesday of the same week.

**April 17, 1635:**

In my post of April 15, 1500, I introduced the new chat feature that Lan has added to OMSI. It makes asking questions during a Quiz very convenient for both you and the TA. I think you'll really like it.

However, Lan told me just now that you do need to use Python 3 for this app, not the old Python. So if you wish to use this app (it's optional), you'll need to install Python 3 on your machine, and of course make sure it's in your path etc.

Python paths, environments etc. can get pretty complicated. (To me, a drawback of an otherwise wonderful language.) For that reason, I always recommend installing miniconda, which will give you the Python package rather than just Python. Of course, you must still set your system's search path accordingly.

If you install the chat, make sure to test it on your machine, just like you tested OMSI.

**April 17, 1545:**

This is just a brief note to say I will be pushing back the due date for Hwk 1. I also will be posting some hints and so on, arising from questions students asked in my office hours today.

**April 17, 1345:**

Quiz questions will typically refer to page numbers, equation numbers, section numbers, example names and so on in the book. It is thus imperative that you have a copy of the book, either in printed or PDF form. 

**April 15, 1500:**

Remember, on Quizzes your OMSI window (including chat box; see below) must fill your laptop screen at all times. If you
think you will need a copy of this blog, or your Homework submission etc., you may bring paper hard copies to the Quiz (and for that matter, paper copies of anything else).

Lan has added a new feature to OMSI, in the files chatXXX. You can use this to ask the TA questions during Quizzes. To use it, update your OMSI directory (e.g. 'git pull origin'), and note the chatXXX files. You run the chat client like you do the OMSI client:

```
python3 chat_client.py servermachinename serverportnumber youremailaddress
```

This hopefully will work better than your raising your hand and the TA trying to walk through the seats to interact with you.

Needless to say, there are still questions the TA will not answer, e.g. "What page in this book is this?", "I don't know what this term from the course means," etc.

The PDF viewer and chat are considered part of OMSI, so having them on your screen does not violate the rule. But be sure to start both the main OMSI client and the chat client at the start of the Quiz.

**April 15, 1035:**

In Quiz problems designated as "R code answer," you are NOT required to write code that is short, efficient or elegant. Just make it work. And remember, OMSI allows you to test your code, a vitally important feature.

**April 15, 0955:**

A couple of trivia items:

* For some reason the Registrar's student roster site is down this morning. I noticed in the error messages I got from running 
Lynx that the site uses Adobe Cold Fusion, an early Web development tool that has gone through various new versions.

    The original inventor of Cold Fusion was JJ Allaire. JJ wrote it as an undergrad and sold it to Microsoft for millions. He then became a "serial entrepreneur," founding a series of successful startups.

    A few years ago, JJ decided that the R language needed an IDE, so he developed RStudio, and founded the firm of that name. He's 
an amazing guy (and very nice personally). He still loves coding, and spends a lot of his day in that activity, even though he is the CEO.

* I mentioned Bob Metcalfe in class. He invented the Ethernet, which added "Listen before talk" to the ALOHA network, and it became his PhD thesis (with complex probability analysis on every page). He then founded 3-Com, and the Ethernet became the industry standard.

    Well, now he has won this year's [Turing Award](https://news.mit.edu/2023/bob-metcalfe-wins-acm-turing-award-0322), "the
    Nobel Prize of Computer Science."


**April 14, 1820:**

I must again emphasize the **UTMOST** importance of close cooperation with your teammates. If one of your teammates contacts you, you should reply right away, acknowledging receipt of the message. Give the sender an estimate as to when you can address his/her points. As I said in class, in someone turns out to be 
unreliable as a teammate, I will have to put that person into a 1-student team, i.e. by him/herself.

**April 14, 1740:**

Problem 2 uses the concepts of *expected value* and *variance*, which we have not yet covered in our course. Here is what you need:

* The expected value of a random variable X, denoted by E(X) (or EX if we just have a single symbol) is the long-run average value of X in the notebook. 
* A function of X is a new random variable, and we can define its expected value similarly. 
    E.g. E(X<sup>0.5</sup>) is the long-run average value of X<sup>0.5</sup>.
* The variance of X, Var(X), is the long-run average value of this function of X: (X - EX)<sup>2</sup>.

Of course there are issues of interpretation etc., but this is enough for you to do the Homework problem.

**April 14, 1530:**

As you know, you can view the "man page" (online help) of an R function
by using a question mark, e.g.

``` r
?ls
```

to obtain information about the **ls()** function.  But you can also 
do this via a call to the **help()** function, e.g.

``` r
help(ls)
```

This could come in handy in an OMSI session.  Just temporarily put your
call to **help()** in the Answers box in your OMSI screen, then click
Submit and Run.


**April 14, 1440:**

A student contacted me, unsure of Problem 2 in the Homework. I'll share my response with everyone here.

The entity p is a vector of probabilities, describing the behavior of
the Li's.  E.g. if p = (0.25,0,35,0.40), then for any i,

P(Li = 1) = 0.25, <br>
P(Li = 2) = 0.40, <br>
P(Li = 3) = 0.35

The quantity v is the travel a bus needs to reach the stop of our
passenger of interest, starting from the main station.  So, for instance
if Bus 3 leaves the main station at time 12, it will arrive at our
special passenger's stop at time 12+v.

Bus 1 leaves the main station at time L1; <br>
Bus 2 leaves the main station at time L1+L2; <br>
Bus 3 leaves the main station at time L1+L2+L3; <br>
and so on.

W is the wait time for our special passenger.  Varies from day to day.

The number k is a parameter in our analysis of this bus system.  We are
interested in P(W = k) for various values of k.  You will find P(W = 1)
"by hand," i.e. mathematically, but will write simulation code that will
find the value of P(W = k) for any k.

**April 13, 2240:**

Thanks, everyone who replied to my Extra Credit challenge. Several people were correct. I will answer everyone individually tomorrow.

The basic problem was that ChatGPT computed P(A and B) instead of P(A | B), where A is the first die having < 3 dots and B is the dice total being > 8. This of course is a very common student error, and ChatGPT made the same error.

**April 13, 2025:**

I gave this request (Section 2.14.5) to ChatGPT:

> Suppose three fair dice are rolled.  Fnd the approximate
> probability that the first die shows fewer than 3 dots, given that the
> total number of dots for the 3 dice is more than 8, using simulation in R.

Here is what it gave me:

``` rc
n_sims <- 100000  # Number of simulations
count <- 0  # Counter for events of interest

# Run the simulations
for (i in 1:n_sims) {
  # Roll three fair dice
  dice <- sample(1:6, size = 3, replace = TRUE)
  
  # Check if first die shows fewer than 3 dots and total dots > 8
  if (dice[1] < 3 & sum(dice) > 8) {
    count <- count + 1
  }
}

# Calculate the approximate probability
prob <- count / n_sims
prob
```

This evaluates to about 0.16, rather than the correct 0.23.

**Extra Credit to the first person who can tell me where ChatGPT went wrong.**


**April 13, 2010:**

An alert student noticed an "off by 1" error in Problem 2 of the Homework. I've made slight changes to the specifications of the bus system accordingly.

I've also added more detail on the submission procedure.

**April 11, 1530:**

I see that my wording in Problem 4 of Quiz 0 was confusing. The freeway trip itself is 60 miles, and this figure does not include the 1.5 miles on surface streets. 

If you thought the 60 mile figure included the 1.5-mile trip, I am hereby instructing the TA to give you full credit if your solution is correct for this interpretation.

**April 11, 0915:**

It's important to distinguish between definitions and properties that follow from the definitions.

For example, the *definition* of P(A|B) is based on the "notebook," the long-run proportion of lines in which A occurs, among the lines in which B occurs. It turns out that that *implies* that P(A|B) = P(A and B) / P(B) (where again, the *definitions* of P(A and B) and P(B) are based on the notebook.

In many cases, you will have P(A|B) simply by intuition. For instance, say an urn contains 10 blue marbles and 4 yellow ones. We choose two marbles at random without replacement. Find (2nd marble is blue | 1st marble is yellow). Well, if the first marble is yellow, then we still have 10 marbles in the urn, but the total number is now 13. Since all marbles are equally likely to be chosen, the probability is 10/13.

Similarly, though the definition of independent events is P(A and B) = P(A) P(B), we often know two events are independent simply from intuition. In the marbles example, if the experiment is to choose two marbles *with* replacement, then the colors of the first and second marbles are independent.

**April 10, 1515:**

Due date for Quiz 0 has been postponed until April 14.

**April 9, 2305:**

Hwk 1 is now official. Please start early.

**April 8, 2250:**

Just uploaded a (very) partial version of the simulation code you will write in Problem 2.

Hwk 1 is still not official, but I will make it so as soon as I get feedback from the TAs. I don't anticipate any major changes at this point.

**April 8, 2150:**

Concerning Problem 1 of the homework (not official yet, but close), the point of the problem is to give you practice in interpreting P(A), P(A|B) etc. So, you find the probabilities directly. E.g.

``` r
> sum(ucb[1,2,]) / sum(ucb)  # P(admit and female)
[1] 0.1230667
```

Ask me or the TA if you have any questions on this.

**April 8, 1410:**

If you added the course once the quarter started, please note [our class GitHub repo](https://github.com/ucdavis/ecs132). Read the syllabus, and the linked information, especially the class procedures. Also, please note that it is required that you read the class blog every day.

**April 8, 1100:**

I've now added Problem 1 to Hwk 1.  Again, still just a draft.

**April 7, 1650:**

I've put a draft of Hwk 1 on our repo here, in the **Hwk** directory. Just a draft, as the TAs and I need to check and refine it, but it will give you an idea of what homework will be like in the course. Approximate due date Apirl 18.

**April 7, 0955:**

We will not have a quiz next week.  Instead, Dylan and Lan will give a mini-lecture. Of course any such presentation could be the subject of quiz questions.

**April 7, 0945:**

I've pushed the [full version of our textbook](https://github.com/ucdavis/ecs132/edit/master/FullProbStatBook.pdf) to our class repo here. It is NOT required that you read it, but it is there in case you wish to read more about some topic. Also, our official version contains '?' symbols, which are references to material that is in the full book but not in our version.

**April 6, 2150:**

Office hours:

NM: M 2-4, 3053 Kemper <br>
DC: MW 1-2, 47 Kemper <br>
LJ: W 2-3PM, F 2-4PM, 55 Kemper (starting week 2)

**April 6, 2020:**

My [op-ed](https://tinyurl.com/yc8cduej) on ChatGPT and statistics is now out. You may find it interesting.

**April 6, 1905:**

Can you answer this question: "How does a computer boot up?" Most CS students can't. And when I mention that to non-CS people, they are shocked that such a basic thing would be foreign to budding computer experts.

It's not your fault. This topic should, IMO, be taught in ECS 50 and/or 150, and usually is not, I believe. But yes, it is indeed a basic thing, something very important to know, as are "systems" issues in general. In the last day or so, for example, I've encountered several students whose trouble with OMSI seems to be related to lack of knowledge of environment variables such as PATH, knowledge that is taken for granted in real-world software development. It is not enough to just know how to code. Nor is it enough to ace the PATH questions on the ECS 36B final exam but then erase the material from your brain after the exam.

**April 5, 1805:**

Please see my [ECS 189G blog post](https://github.com/ucdavis/FairMLCourse/blob/main/Blog.md) of 17:35, re seeking help, the Unix **script** command, etc.

**April 4, 2010:**

I mentioned in class today that anyone who considers him/herself to be well versed with computers should know something about client/server programming. If you haven't done this kind of coding before, I urge you to read [my tutorial](https://heather.cs.ucdavis.edu/matloff/public_html/Python/PyNet.pdf). You will NOT need this for our class, just something to back up your future claims of expertise. :-) And by the way, it will help you understand OMSI better.

**April 4, 1830**

Someone brought up the perennial R-vs.-PYthon-for-data-science issue in both of my classes today. In the afternoon class, I made a comment about random forests, which I will elaborate on below, but first I should make one point clear: Our course is not an R-in-probability-and-statistics class; it's a probability-and-statistics class, period. The emphasis is on the concepts and methods, not on the language. Keep in mind always: this is a MATH class.

At any rate, I mentioned in the afternoon class that IMO there are better libraries for random forests in R than in Python. In case anyone is curious, I would cite e.g. the grf package by the Stanford Econ and Stat people. The linear interpolation capability is especially important.

But again, though the grf package was developed in R (I think there is now a Python version, though not in sklearn), this was not because R is a "better" language but because Stat people tend to use R.

**April 4, 1225**

All my old ECS 132 quizzes are available [here](https://heather.cs.ucdavis.edu/OldECS132Quizzes).

**April 3, 2106**

We will soon be forming our Homework Groups. Group size is 3 or 4. If you have 1 to 3 people you would like to be in a Group with, please so inform Lan Jiang (lanjiang@ucdavis.edu) by Friday, April 7, 11:59 pm (even if you are in Dylan's section). Otherwise, Lan will assign you to a group.

Details of how the Groups work are in the [general course info doc](https://github.com/matloff/nmGeneralCourseInfo/blob/master/RulesAndProcedures.md). Note carefully that this document is vital to your success in the course, regarding homework, exams, grading and so on; please read it right away.

**April 3, 2052**

My earlier e-mail messages said our blog was on the machine Heather. Of course, that is incorect. The blog is the GitHub file you are now reading.

**April 3, 2048:**

Our [course syllabus](https://github.com/ucdavis/ecs132/blob/master/Syllabus.md) is now ready!

**April 3, 2015:**

It may be a couple of days before we have days/times/locations for office hours. For now, if you have questions about Quiz 0, please e-mail NM on quiz content matters, or your assigned TA (see Syllabus, available later this evening) on OMSI issues.

**April 3, 1405:**


All class announcements from this point onward will be made here in this
blog, rather than by mass e-mail.  When making a blog post, I will also
try to send a message notifying you of a new post, but may not always do
so.  You are required to read the blog at least once per day.

