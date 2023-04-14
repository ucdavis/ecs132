
# ECS 132 Blog

**Spring 2023**

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

