# Statistics 159/259, Homework 1. 

* Due 1/24/2021 11:59PM PT
* Profs. Perez and Stark, Department of Statistics, UC Berkeley
* This assignment is worth a maximum of 20 points.


For this and all assignments in this course, we will be using a platform known as [Github Classroom](https://classroom.github.com/classrooms/42591242-stat-159-259-spring-2021-university-of-california-berkeley). You will have to manage your submissions as Git repositories that will be hosted here.

For this assignment, you will create a file called `hw01-solution.md` where you will type up your solutions. 
Create the file initially as a copy of this `hw01-background.md` file, and fill in your answer below each question.

You will need to add the file `hw01-solution.md` to your repository and push it back up to Github Classroom so we can see it.


## [2 points] Expectations

Consider a set of ordered pairs, $\{ (x_j, y_j)\}_{j=1}^n$.
Let $\bar{x} \equiv \frac{1}{n} \sum_{j=1}^n x_j$,
$\bar{x} \equiv \frac{1}{n} \sum_{j=1}^n x_j$, and
$\bar{xy} \equiv \frac{1}{n} \sum_{j=1}^n x_j y_j$.
+ Is $\bar{xy} = \bar{x}\bar{y}$? If so, sketch a proof; if not, give a counter example.
    - Answer: The above statement is inaccurate, as $\bar{x}\bar{y}$ is the average of the product of two sums while $\bar{xy}$ is a sum of the average of $n$ products. Taking  $n=2$ with the $X$ and $Y$ vectors as (0,2) and (2,6) respectively, a counterexample is found where $\bar{xy}=15$ while $\bar{x}\bar{y}=10$, disproving the above statement.

## [2 points] $P$-values

+ In your own words, explain what a $P$-value is (not how to calculate it: what it means).
    - A $P$-Value, in simple terms, is the probability that the value of a given test statistic is as large or larger than what the value of that test statistic would be under the null hypothesis. Essentially it is the probability we see the data we are seeing given the null hypothesis holds
+ Suppose that the $P$-value is 0.04. What does that mean about the null hypothesis?
    - A very low $P$-value is indicative of a rejection of the null hypothesis, as it states that the probability of the observed data aligning with the null is very low, as the observed data allows us to assemble test statistics which we then can compare against the null. A test with an outcome like this can be deemed "statistically significant"


## [7 points] Hypothesis testing

+ What is the complete null hypothesis for a $Z$-test?
    - $H_0 : \mu=\mu_0$ is the null for a two sided $Z$-test
+ Consider testing $N$ null hypotheses at significance level $\alpha$.
Answer the following using closed-form expressions
(not numbers).
    - Suppose all $N$ null hypotheses are true and that the data used to test the 
hypotheses are independent across hypotheses.
        - What is the expected number of null hypotheses that will be rejected erroneously?
            - In this case we are looking for the number of Type I errors over $N$ tests at a significance level $\alpha$. As the significance level can be conceptualized as the probability of a Type I error, the expected number of erroneously rejected nulls will be $(N*\alpha)$
        - What is the chance of erroneously rejecting at least one of the null hypotheses?
            - Once again, we're looking for probability of a Type I error here, only this time we want to know the chance that at least one takes place which can be thought of as the complement of a Type I error never occurring which can be expressed as follows: $1-(1-\alpha)^N$
        - What is the chance of erroneously rejecting at least $k$ of the null hypotheses, $k=1, \ldots, N$?
            - As the case of a Type I error or not ammounts to a bernoulli trial, this probability can be expressed by the Binomial distribution's PDF as follows. $P_1 = \sum_{k=1}^{N}{N \choose k} (1-\alpha)^{N-k} \alpha^k $
    - Suppose $T$ of the null hypotheses are true and that the data used to test the hypotheses are independent
across hypotheses.
        - What is the chance of erroneously rejecting at least $k$ of the true null hypotheses, $k=1, \ldots, N-T$?
            - With independent data we can conceptualize the $T$ true null hypotheses as the number of Bernoulli trials and use and identical approach to what was employed for the previous question, that is: $P_1 = \sum_{k=1}^{N-T}{T \choose k} (1-alpha)^{T-K} \alpha^k$
    - Suppose all $N$ null hypotheses are true but that the data used to test the null hypotheses are not
independent across hypotheses: their dependence is arbitrary.
        - What is the expected number of null hypotheses that will be rejected erroneously?
        - Find a sharp upper bound on the chance of rejecting at least one null hypothesis.

## [4 points] DataHub and Git Practice

Log into the [class DataHub](https://stat159.datahub.berkeley.edu) with your campus credentials. Open a terminal and clone [this github repository that contains a "whirlwind tour" of Python for science](https://github.com/jakevdp/WhirlwindTourOfPython). Note that the same content can be viewed as a regular website [here](https://jakevdp.github.io/WhirlwindTourOfPython/index.html).

You should be reasonably comfortable with most of the material in that overview of Python. Make sure you go through the notebooks, execute their code, make small changes and experiment.

As proof of work, include an image such as the one below in your repo, that shows how in your own hub directory you have the right repository cloned and some of the files in it (this is taken from my account in the Hub):

-See Stat159HW1Q4.jpg


## [5 points ] Git Practice: collaborating with yourself

- Install Git on your personal laptop (search for and follow the Git installation instructions appropriate to your operating system, be it Windows, MacOS or Linux).
- Clone your homework repository on your personal laptop.
- Create a text file from your laptop named `test.txt` with the following content:

```
Text file created on my personal laptop.
```

- Add it to your repository and push it to Github.

- Pull that file to the DataHub and make further edits to the file from the Hub. Add to the file the output of the command `free` as 
executed on the Hub, as well as the output of the command `pwd`.

- Commit all your changes and push them up to your repo for final submission.

