# APM1110-FA8
# 1. An urn contains 10 red, 8 black, and 7 green balls. One of the colors is chosen at random (meaning that the chosen color is equally likely to be any of the 3 colors), and then 4 balls are randomly chosen from the urn.
##
# Let X be the number of these balls that are of the chosen color.
##
## Given:
## Red = 10, Black = 8, Green = 7
## Total = 25 balls
## Number of draws = 4
## Each color is equally likely to be selected.
##
# (a) Find P(X = 0).
## Using the hypergeometric distribution:
## P(X = x) = [choose(m,x) * choose(N-m,n-x)] / choose(N,n)
##
## Where:
## N = 25
## n = 4
## x = 0
##
## For RED:
## P(X = 0 | Red)
## = [choose(10,0) * choose(15,4)] / choose(25,4)
## = [1 * 1365] / 12650
## = 1365 / 12650
## = 0.1079
##
## For BLACK:
## P(X = 0 | Black)
## = [choose(8,0) * choose(17,4)] / choose(25,4)
## = [1 * 2380] / 12650
## = 2380 / 12650
## = 0.1881
##
## For GREEN:
## P(X = 0 | Green)
## = [choose(7,0) * choose(18,4)] / choose(25,4)
## = [1 * 3060] / 12650
## = 3060 / 12650
## = 0.2419
##
## Since each color is equally likely:
## P(X = 0)
## = (1/3)[P(X=0 | Red) + P(X=0 | Black)
##         + P(X=0 | Green)]
## = (1/3)[1365/12650 + 2380/12650 + 3060/12650]
## = (1/3)(6805/12650)
## = 6805/37950
## = 0.1793
##
## FINAL ANSWER:
## P(X = 0) = 0.1793
##
# (b) Find P(Xi = 1), i = 1, 2, 3, 4.
## For any position i:
## P(Xi = 1)
## = (1/3)(10/25) + (1/3)(8/25) + (1/3)(7/25)
## = (1/3)[(10 + 8 + 7)/25]
## = (1/3)(25/25)
## = 1/3
## = 0.3333
##
## Since each position has the same probability:
## P(X1 = 1) = 0.3333
## P(X2 = 1) = 0.3333
## P(X3 = 1) = 0.3333
## P(X4 = 1) = 0.3333
##
## FINAL ANSWER:
## P(Xi = 1) = 0.3333, for i = 1, 2, 3, 4.
##
# (c) Find E[X].
## Given:
## X = X1 + X2 + X3 + X4
##
## By linearity of expectation:
## E[X] = E[X1] + E[X2] + E[X3] + E[X4]
## Since E[Xi] = P(Xi = 1):
## E[X] = 4P(Xi = 1)
## = 4(1/3)
## = 4/3
## = 1.3333
##
## FINAL ANSWER:
## E[X] = 1.3333
##
# 2. The random variable X is said to have the Yule-Simon distribution if
## P(X=n) = 4/n(n+1)(n+2)' n>=1
##
# (a) Show that the PMF sums to 1.
## Sum P(X = n), from n = 1 to infinity:
## = 4 * Sum [1 / (n(n+1)(n+2))]
##
## Using partial fractions:
## 1/[n(n+1)(n+2)]
## = (1/2)[1/(n(n+1)) - 1/((n+1)(n+2))]
##
## Therefore:
## Sum P(X = n)
## = 2 * Sum [1/(n(n+1)) - 1/((n+1)(n+2))]
##
## Expanding:
## = 2[(1/(1*2) - 1/(2*3))
##   + (1/(2*3) - 1/(3*4))
##   + (1/(3*4) - 1/(4*5)) + ...]
##
## By telescoping:
## = 2[1/2 - 1/((N+1)(N+2))]
##
## Taking the limit as N approaches infinity:
## = 2[1/2 - 0]
## = 1
##
## FINAL ANSWER:
## Sum P(X = n) = 1
##
# (b) Show that E[X] = 2.
## E[X] = Sum nP(X = n)
## = Sum [n * 4/(n(n+1)(n+2))]
## = 4 * Sum [1/((n+1)(n+2))]
##
## Using partial fractions:
## 1/((n+1)(n+2))
## = 1/(n+1) - 1/(n+2)
##
## Therefore:
## E[X] = 4 * Sum [1/(n+1) - 1/(n+2)]
##
## Expanding:
## = 4[(1/2 - 1/3)
##   + (1/3 - 1/4)
##   + (1/4 - 1/5) + ...]
##
## By telescoping:
## = 4[1/2 - 1/(N+2)]
##
## Taking the limit as N approaches infinity:
## = 4(1/2 - 0)
## = 4(1/2)
## = 2
##
## FINAL ANSWER:
## E[X] = 2.0000
##
# (c) Show that E[X^2] = infinity.
## E[X^2] = Sum n^2 P(X = n)
## = Sum [n^2 * 4/(n(n+1)(n+2))]
## = Sum [4n/((n+1)(n+2))]
##
## For large values of n:
## 4n/((n+1)(n+2)) is approximately equal to 4/n.
##
## Apply the limit comparison test:
## Limit as n approaches infinity of:
## [4n/((n+1)(n+2))] / (4/n)
## = Limit [n^2/((n+1)(n+2))]
## = 1
##
## Since the harmonic series:
## Sum (1/n)
## diverges, the series for E[X^2] also diverges.
##
## Therefore:
## E[X^2] = infinity
##
## FINAL ANSWER:
## E[X^2] = Inf
##
# 3. The probability density function of X is given by
## GIVEN:
##
## f(x) = a + bx^2, for 0 <= x <= 1
## f(x) = 0, otherwise
##
## E[X] = 3/5
##
## Find a and b.
##
## Step 1: Use the total probability condition.
## Integral from 0 to 1 of f(x) dx = 1
## Integral from 0 to 1 of (a + bx^2) dx = 1
## a Integral from 0 to 1 of dx
## + b Integral from 0 to 1 of x^2 dx = 1
## a[x] from 0 to 1 + b[x^3/3] from 0 to 1 = 1
## a(1 - 0) + b(1/3 - 0) = 1
## a + b/3 = 1
##
## Multiply both sides by 3:
## 3a + b = 3                         (Equation 1)
##
## Step 2: Use the expected value condition.
## E[X] = Integral from 0 to 1 of x*f(x) dx
## 3/5 = Integral from 0 to 1 of x(a + bx^2) dx
## 3/5 = Integral from 0 to 1 of (ax + bx^3) dx
## 3/5 = a[x^2/2] from 0 to 1
##       + b[x^4/4] from 0 to 1
## 3/5 = a(1/2) + b(1/4)
## a/2 + b/4 = 3/5
##
## Multiply both sides by 4:
## 2a + b = 12/5                      (Equation 2)
##
## Step 3: Solve the simultaneous equations.
## Equation 1: 3a + b = 3
## Equation 2: 2a + b = 12/5
##
## Subtract Equation 2 from Equation 1:
## (3a + b) - (2a + b) = 3 - 12/5
## 3a - 2a = 15/5 - 12/5
## a = 3/5
## a = 0.6000
##
## Step 4: Solve for b.
## Substitute a = 3/5 into Equation 1:
## 3a + b = 3
## 3(3/5) + b = 3
## 9/5 + b = 3
## b = 3 - 9/5
## b = 15/5 - 9/5
## b = 6/5
## b = 1.2000
##
## FINAL ANSWERS:
## a = 0.6000
## b = 1.2000
##
# 4. Let X be a random variable having expected value mu and variance sigma2. Find the expected value and variance of
## Y = X-mu/sigma
##
## GIVEN:
## E[X] = mu
## Var(X) = sigma^2
## Y = (X - mu)/sigma
## Find E[Y] and Var(Y)
##
# (a) Find E[Y].
## Given:
## Y = (X - mu)/sigma
## E[Y] = E[(X - mu)/sigma]
## = (1/sigma)E[X - mu]
## = (1/sigma)[E[X] - mu]
##
## Since E[X] = mu:
## = (1/sigma)(mu - mu)
## = (1/sigma)(0)
## = 0
##
## FINAL ANSWER:
## E[Y] = 0.0000
##
# (b) Find Var(Y).
## Given:
## Y = (X - mu)/sigma
## Var(Y) = Var[(X - mu)/sigma]
## Using Var(aX + b) = a^2 Var(X):
## Var(Y) = (1/sigma^2)Var(X - mu)
## = (1/sigma^2)Var(X)
##
## Since Var(X) = sigma^2:
## = (1/sigma^2)(sigma^2)
## = 1
##
## FINAL ANSWER:
## Var(Y) = 1.0000
##
# 5.  Let X and Y be independent Poisson random variables with parameters lambda1 = 2 and lambda2 = 3, respectively. Let W = X + Y. 
##
# (a) Using the property of sums of independent random variables, derive the moment generating function (MGF) MW (t) of W.
##
# (b) Based on the uniqueness property of MGFs, identify the probability distribution and parameter(s) of W.
##
# (c) Determine the expected value E[W ] and the second moment E[W 2] by successively differentiating MW (t) and evaluating it at t = 0.
##
# (a) Derive the MGF of W.
## The MGF of a Poisson random variable is:
## M(t) = exp(lambda * (exp(t) - 1))
##
## For X ~ Poisson(2):
## M_X(t) = exp(2(exp(t) - 1))
##
## For Y ~ Poisson(3):
## M_Y(t) = exp(3(exp(t) - 1))
##
## Since X and Y are independent:
## M_W(t) = M_X(t) * M_Y(t)
## = exp(2(exp(t) - 1)) * exp(3(exp(t) - 1))
## = exp(2(exp(t) - 1) + 3(exp(t) - 1))
## = exp((2 + 3)(exp(t) - 1))
## = exp(5(exp(t) - 1))
##
## FINAL ANSWER:
## M_W(t) = exp(5(exp(t) - 1))
##
# (b) Identify the probability distribution of W.
## The MGF of a Poisson random variable is:
## M(t) = exp(lambda(exp(t) - 1))
##
## Our derived MGF is:
## M_W(t) = exp(5(exp(t) - 1))
##
## Comparing the two expressions:
## lambda = 5
##
## Therefore:
## W ~ Poisson(5)
##
## FINAL ANSWER:
## W follows a Poisson distribution with parameter 5.
##
# (c) Find E[W] and E[W^2].
## Given:
## M_W(t) = exp(5(exp(t) - 1))
##
## First derivative:
## M'_W(t) = 5exp(t) * exp(5(exp(t) - 1))
## = 5exp(t)exp(5(exp(t) - 1))
##
## Expected value:
## E[W] = M'_W(0)
## = 5exp(0)exp(5(exp(0) - 1))
## = 5(1)exp(5(1 - 1))
## = 5(1)exp(0)
## = 5
## E[W] = 5.0000
##
## Second derivative:
## M''_W(t)
## = 5exp(t)exp(5(exp(t)-1))
##   + 25exp(2t)exp(5(exp(t)-1))
## = (5exp(t) + 25exp(2t))
##   * exp(5(exp(t)-1))
##
## Second moment:
## E[W^2] = M''_W(0)
## = (5exp(0) + 25exp(2(0)))
##   * exp(5(exp(0)-1))
## = (5(1) + 25(1)) * exp(0)
## = (5 + 25)(1)
## = 30
##
## E[W^2] = 30.0000
##
## FINAL ANSWERS:
## E[W] = 5.0000
## E[W^2] = 30.0000
