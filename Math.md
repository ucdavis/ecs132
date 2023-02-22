
# Use of Math in Norm Matloff's ECS 132

                                                                              
Note that we will use the OMSI app for quizzes.  You come to class with
your laptop and take the quiz on your laptop via OMSI.  You will
write and run code on quizzes using OMSI.                                                         
                                                                                
So, generally you won't be doing any calculations by hand.  You will use
R.     
                                                                                
Example:

``` r
                                                                                
> m <- rbind(c(1,4),c(0,-2.5))  # "row bind" operation
> m                                                                             
     [,1] [,2]
[1,]    1  4.0
[2,]    0 -2.5                                                                  
> minv <- solve(m)  # find the matrix inverse of m 
> minv                                                                          
     [,1] [,2]
[1,]    1  1.6
[2,]    0 -0.4                                                                  
> m %*% minv  # check by multiplying; do we get the identity matrix?            
     [,1] [,2]           
[1,]    1    0
[2,]    0    1
# yes
```

                                                                                
There are also R ops for finding derivatives and integrals etc.
However, it will be expected that you remember how to do the simple
stuff by hand, e.g.    
                                                                                
d/dx x^3 = 3 x^2                                                                

So, you will mainly need to know calculus and linear algebra on an
inutitive level. **But do not underestimate the need for a keen intuition.**   
