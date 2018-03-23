[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

>> Started...

# Problem description
Referenced the solution to understand how to initiate the code with the relevant information.
Finally I understand the process of importing the nsfg module which does importing and framing
for you. I was trying to work through that process manually which was... unnecessary.

After getting the dataframe set up, the solution was straightfoward based on the chapter's description of the 
biased vs. unbiased survey results.

I also printed the means of each the original pmf and biased_pmf to get a quick numeric summary to quickly
contextualize the information in the graphs. They look correct.

# Code
### import relevant modules
    import thinkstats2
    import thinkplot
    import nsfg

### read info into dataframe
    df = nsfg.ReadFemResp()

### convert relevant data to pmf, print mean for future comparison
    pmf = thinkstats2.Pmf(df.numkdhh, label='numkdhh')
    print(pmf.Mean())

### plot the numkdhh data
    thinkplot.Pmf(pmf)
    thinkplot.show(xlabel='children_count', ylabel='PMF', title='unbiased')

### re-analyze the data considering the bias we would expect if
### the children had been surveyed

    biased_pmf = pmf.Copy(label='biased')
    for x, p in biased_pmf.Items():
        biased_pmf.Mult(x, x)

    biased_pmf.Normalize()
    print(biased_pmf.Mean())

    thinkplot.PrePlot(2)
    thinkplot.Pmfs([pmf, biased_pmf])
    thinkplot.Show(xlabel='child_count', ylabel='PMF')
