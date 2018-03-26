[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

>> 34.xx%

##Answer Explanation & Code
The simplest way to derive the answer is to use the summary statistics of the male heights from the brfss survey which are provided in the text. (mu = 178cm; omega = 7.7cm)/

Convert heights to (cm) from (ft,in).

    short = ((5*12)+ 10) * (1/0.3937)
    tall = ((6*12)+ 1) * (1/0.3937)

Use scipy's cdf function to determine percentile of the short and tall ends of the Blue Man Group's requirement range.

    cdf_short = scipy.stats.norm.cdf(short, loc=178, scale=7.7)
    cdf_tall = scipy.stats.norm.cdf(tall, loc=178, scale=7.7)

Subtract the short percentile range from the tall percentile range to be left with the % of US male population that fits within the required height range. 

    us_blue_men_pct = (cdf_tall - cdf_short) * 100
    print(us_blue_men_pct)
    
$$$It is slightly more fun to start from a half-step back and derive your own summary statistics. For this, I went the following route:

Import required modules

    import thinkstats2
    import scipy.stats
    import brfss
    
Read in the data with Downey's pre-defined data reader/cleaner function 'ReadBrfss().'

    df = brfss.ReadBrfss()
    df.dropna(subset=['htm3'])
   
Create a copy of the df which includes only the question-relevant, male data.

    df_male = df[df.sex == 1]
    
Summarize the male height data for mu and omega.

    mu = df_male.htm3.mean()
    omega = df_male.htm3.std()
    
Feed these summary statistics into the original answer above and viola.
