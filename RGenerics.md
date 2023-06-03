
# R Generic Functions

R is both a functional language and an object-oriented one.  One feature
is *polymorphism*. R has a number of *generic functions*, such as
**print()**, **plot(()** and **summary()**.  They are not functions in
the usual sense of performing actual work.  Instead, their job is simply
to *call other functions*.

As an example, consider R's **ecdf()** function, which produces the
*empirical cdf* from the usual data set X<sub>1</sub>,...,X<sub>n</sub>.
The empirical CDF is the estimate of the population CDF,
F<sub>X</sub>(t).  For instance, the empirical CDF of the **Nile**
dataset, evaluated at t = 1129.2, is the proportion of data points below
or equal to that number, 0.85:

``` r
mean(Nile <= 1129.2)  # 0.85
```

We can get that using the **ecdf()** function:

``` r
> z <- ecdf(Nile)
> z(1129.2)
[1] 0.85
```

Obviously, the object **z** here is a function.  Let's confirm:

``` r
> class(z)
[1] "ecdf"     "stepfun"  "function"
```

Ah, yes, **z** is indeed of class 'function'.  (All class names in R are
quoted strings.)  But there's more:  It turns out that the 'function'
class has as subclass, 'stepfun', not too surprising since empirical
CDFs are step functions.  And in turn, one of the subclasses of
'stepfun' (there are probably many) is 'ecdf'.

Now, what happens in the call

``` r
plot(z)
```

A graph of the empirical CDF of **Nile** does pop up (not shown here),
but the drawing on the screen is NOT done by the **plot()** function.
Instead, the R interpreter *dispatches* the **plot()** call to a function
**plot.ecdf()**, which does the actual work of drawing on the screen.

We can check that by a direct call():

``` r
plot.ecdf(z)
```

which produces the same graph.

Note carefully that **plot()** and **plot.ecdf()** are two entirely
separate functions.  The convention is to give the name **plot.x()** to the function that **plot()** dispatches to, where x is the name of the class.  There are
many, many **plot.x** functions in both base R and the tens of thousands of
contributed R packages in the CRAN repository.  

In other words, **plot()** is merely a go-between.

You'll find on the other hand that for instance there is no function
**summary.ecdf()**.  A more sophisticated mechanism is used here.
But there are **summary.data.frame()** and **print.data.frame()**:

``` r
> summary.data.frame
function (object, maxsum = 7L, digits = max(3L, getOption("digits") - 
    3L), ...) 
{
    ncw <- function(x) {
        z <- nchar(x, type = "w")
        if (any(na <- is.na(z))) {
            z[na] <- nchar(encodeString(z[na]), "b")
        }
        z
    }
    z <- lapply(X = as.list(object), FUN = summary, maxsum = maxsum, 
        digits = 12L, ...)
...
```



