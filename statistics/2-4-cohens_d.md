[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

>> weight: 0.088; length: 0.00042

# Answer description
Cohen's D (weight): **0.088**  
Cohen's D (length): **0.00042**

# Code 
Import required modules
            
    import thinkstats2
    import nsfg
    import first
    import math

Read data and define 'live', 'first', 'others' with function from first module.

    live, first, others = first.MakeFrames()

Calculate cohen's d of weight.

    first_weight_mean = first.totalwgt_lb.mean()
    others_weight_mean = others.totalwgt_lb.mean()
    first_var = first.totalwgt_lb.var()
    others_var = others.totalwgt_lb.var()
    pooled_var = ((len(first)*first_var)+(len(others)*others_var)) / (len(first)+len(others))
    wt_pooled_dv = math.sqrt(pooled_var)
    cohens_d_weight = abs((first_weight_mean - others_weight_mean))/ wt_pooled_dv
    print(cohens_d_weight)

Calculate cohen's d of length.

    first_length_mean = first.prglngth.mean()
    others_length_mean = others.prglngth.mean()
    first_length_var = first.prglngth.var()
    others_length_var = first.prglngth.var()

    lg_pooled_var = (len(first)*first_length_var)+(len(others)*others_length_var) / (len(first)+len(others))    
    lg_pooled_dv = math.sqrt(lg_pooled_var)
    cohens_d_length = abs((first_length_mean - others_length_mean) / lg_pooled_dv)
    print(cohens_d_length)
    
