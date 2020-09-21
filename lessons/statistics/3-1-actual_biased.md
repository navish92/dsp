[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

>> REPLACE THIS TEXT WITH YOUR RESPONSE
```{python}
df_resp = nsfg.ReadFemResp()

pmf = thinkstats2.Pmf(df_resp.numkdhh,label = "actual")

#biasing the distribution by the oberseved family size

bias_pmf = pmf.Copy(label="observed")

for size,prob in bias_pmf.Items():
    bias_pmf.Mult(size,size)

bias_pmf.Normalize()

thinkplot.PrePlot(2)
thinkplot.Pmfs([pmf, bias_pmf])
thinkplot.Show(xlabel='class size', ylabel='PMF')


```
