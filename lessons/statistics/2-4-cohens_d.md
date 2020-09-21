[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

``` {python}
# Deriving the total weight from the dataframe split by the pregnenancy order column

first_baby_weight = df[df.birthord==1].totalwgt_lb
second_baby_weight = df[df.birthord != 1].totalwgt_lb

#calculating cohen's D
def CohenEffectSize(group1, group2):
    import math
    diff = group1.mean() - group2.mean()
    var1 = group1.var()
    var2 = group2.var()
    n1, n2 = len(group1), len(group2)
    pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
    d = diff / math.sqrt(pooled_var)
    return d

d = CohenEffectSize(first_baby_weight,second_baby_weight)

print(d)

-0.08893641177719079
```

Although, it could be that subsequent babies are slightly lighter, with the difference in mean being very just -0.069 standard deviations, we can conclude that the birth order does not contribute significantly to the weight of the baby.
