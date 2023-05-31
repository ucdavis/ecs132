
# What "T is an Estimator of &theta;" Means, and Implications for Unbalanced Data

## The issues

Yesterday in class, we revisited the issue of statistical consistency,
which arises in answer to the general question, "What do we mean when we
say T is an estimator of &theta;?  All this arose in the context of our
asking whether unbalanced data is a problem in ML.  More on this later
in this post. Here we'll take a closer look at this.

## Notation and setting

Let's write T<sub>n</sub> instead of T, to emphasize dependence on our
sample size n.  Statistical consistency means that

lim<sub>n -> &infin;</sub> T<sub>n</sub> = &theta;,

i.e. as we take larger and larger samples, T<sub>n</sub> converges to
the right value, &theta;.  But when I first taught this, I don't think I
stated clearly that, since T<sub>n</sub> works as desired for large data
(i.e. large n), we then have faith that it is in some sense doing so for
small n.  

As a starting example, take &theta; to be the population
mean of some quantity X.  It's natural to take T<sub>n</sub> to be the
sample mean, i.e. the average value of X in our data points, no one
would question the statement "T is an Estimator of &theta;."

But what does this really mean?  

# Answers based on *bias*

We might at first take it to mean that
T<sub>n</sub> is an *unbiased* estimator of &theta;,

E(T<sub>n</sub>) = &theta;

where the expected value is taken over all possible samples of size n
(i.e. samples consisting of n data points).  In some samples,
T<sub>n</sub> is larger than &theta;, in other samples less, but "On
average it comes out right."

But unbiasedness is much too strong a criterion.  Most estimators do
have some amount of bias.  

Consider the case of estimating the &beta;<sub>i</sub> coefficients in a
logistic model.  (Say the model is exactly correct.)  Due to
nonlinearity etc., the estimates b<sub>i</sub> of the &beta;<sub>i</sub>
will not be unbiased.  But intuitively, **the amount of bias is small.**

So, in turn, what does "small" mean?  The answer is that the bias can be
shown to be O(1/n), hence "small."  So **even the bias is gauged in the
context of asymptotics**.  We have no usable expression for bias, so we
take it on faith that the small asymptotic bias expression is an
indication that T<sub>n</sub> works pretty well for small n.

# Statistical consistency

But bias depends on expected value, which is greatly influenced by
outliers, so we basically settle for the simpler, less mathematically
restrictive condition,

lim<sub>n -> &infin;</sub> T<sub>n</sub> = &theta;,

Actually, the usual definition is even weaker,

lim<sub>n -> &infin;</sub> P(|T<sub>n</sub> = &theta;| < &epsilon;)

for all &epsilon; > 0, but the point is that the answer to the question,
"What do we mean in saying that T<sub>n</sub> estimates &theta;?" boils
down to definitions based on large n.  And, by extension we put our
faith in T<sub>n</sub> even for small n.

# Implications for unbalanced data

Now returning to the topic of unbalanced data, consider the example
discussed in class.  Say we are interested in a possible pay gap between
men and women, and that a linear model holds.  Say the pay gap is the
same at all age levels; the same comments will apply to the general
case.  

But also suppose there are 5 times as many women in our data.  And in
the theoretical asymptotic context, lim<sub>n -> &infin;</sub>, say we
always have n<sub>mean</sub> = 5 n<sub>women</sub>.  What are the
implications, if any of this gender imbalance?

To answer this question, let's first consider a simpler example,
modeling mean weight as a function of height.  Say a linear model holds,

E(weight | height=t) =
&beta;<sub>0</sub>
&beta;<sub>1</sub> height

We wish to estimate the &beta;<sub>i</sub>.

Some terminology:  

* In *random-X* regression, we simply sample n people at random, so both
  our weight and height data are random.

* If *fixed-X* regression, we decide specific heights of interest to us,
  and then sample random people from those height groups.

Statistically, it doesn't really matter.  If we do random-X, we will
look at the conditional distribution of Y given X anyway, so the X
values might as well be considered fixed.

Now, consider two sampling schemes:

* Plan A:  We will sample n people, but with most on the shorter end,
  say 5/6 of them under 68 inches tall.

* Plan B:  We will sample n people, but with most on the taller end,
  say 5/6 of them over 68 inches tall.

The key point:

Under either sampling scheme, our b<sub>i</sub> will estimate the
&beta;<sub>i</sub>, in the sense discussed before.  Plan B will probably
give us smaller standard errors for the b<sub>i</sub>, but either plan
will give us statistically consistent estimators of the
&beta;<sub>i</sub>.  (And by the way, the b<sub>i</sub> will be
unbiased under either plan.)


Of course, then there is the question of the inevitable 
