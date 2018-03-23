[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

>> Yes, the distribution of randomly generated numbers is uniform.

# Problem
In this case the sample is random and its distribution is uniform. It may deviated slightly, however with a large enough sample
size it would be expected to be perfectly uniform.

# Code

Import the necessary modules

    import thinkstats2
    import thinkplot
    import random

Generate nums in a type that will be read by Pmf and Cdf (list works)
    
    rand_nums = []
    for x in range(1000):
        rand_nums.append(random.random())

Create the Pmf

    pmf = thinkstats2.Pmf(rand_nums, label='PMF')
    print('Mean:', pmf.Mean())

Create the Cdf

    cdf = thinkstats2.Cdf(rand_nums, label = 'CDF')
    thinkplot.Cdf(cdf)
    thinkplot.Show(xlabel='random_numbers', ylabel='CDF')

