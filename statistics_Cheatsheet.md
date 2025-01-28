# statistical Analysis incomplete notes
## Know your Data
the first step should always be an overview. divide in subgroups if necessary eg control/case or sexes
* What Data is there 
    * is it categorical, Time-Series, discrete (countable) Numerical, Continuous (Measured)
* Whats incomplete/ misspelled/ has the wrong format eg dates
* Which Data will be relevant fore the analysis? is it complete
* reformatting and fixing what can be fixed   
* a graphical exploration   
    * are there outliers
    * what does the distrobution look like
    * are linear regessions possible
    * are there any obvious relations between sets

## testing single Vars
* test for distrobution 
    * shapiro-wilk for small samples (scipy.stats.shapiro)
    * Kolmogorov-Smirnov Test for bigger (>50) sizes (scipy.stats.kstest)




## Plots
### showing distribution
* single var - histogramm densityplot
* two var - scatterplot
* more vars - boxplots w beeswarm
* violin plot

### showing composition
* few vars over time - bar plot w regressions
* many vars over time - area plot
* shares - pie chart
* static changes - waterfall plot
* undercategories barchart with subcomponents

## showing relationships
* two vars - scatter plot w regressions
* more vars - bubble plot

## showing comparisons
* bar plots
* boxplots
* violin plots
* circular area plot
* line plot
* all in facet plots for more vars/ complexity