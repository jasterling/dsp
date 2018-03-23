[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

>> I'm coming back to this...

# Answer description
Below is my answer for comparing the cohen's d of weight and length in first babies
to a mother and those that come afterwards.

# Code 
      
    def differences(live, first, others)
        first_weight_mean = first.totalwgt_lb.mean()
        others_weight_mean = others.totalwgt_lb.mean()
        first_var = first.var()
        others_var = others.var()
        pooled_var = (len(first)*first_var)+(len(others)*others_var) / (len(first)+len(others))
        wt_pooled_dv = math.sqrt(pooled_var)
        cohens_d_weight = (first_weight_mean - others_weight_mean)/ wt_pooled_dvprint('Cohens d for weight is: '+cohens_d_weight)
        return (cohens_d_weight)
        
        first_length_mean = first.prglngth.mean()
        others_length_mean = others.prglngth.mean()
        first_length_var = first.prglngth.var()
        others_length_var = first.prglngth.var()

        lg_pooled_var = (len(first)*first_length_var)+(len(others)*others_length_var) / (len(first)+len(others))    
        lg_pooled_dv = math.sqrt(lg_pooled_var)
        cohens_d_length = (first_length_mean - others_length_mean) / lg_pooled_dv
        return (cohens_d_length)
        
        print('Cohens d for length is:'+cohens_d_length)

    
