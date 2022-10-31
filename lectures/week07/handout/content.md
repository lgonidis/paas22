```{r}
#| echo: false
#| message: false
require(tidyverse)
require(cowplot)
require(patchwork)
knitr::opts_knit$set(eval.after = "fig.cap")
```

Last week we started learning about the tools we can use to describe data.
Specifically, we learned about the **mean**, **mode**, and **median**. And we
learned about how they are different ways of describing the typical value. But
apart describing the _typical value_, we might also want a way to
describe how **spread** out the data is around this value. We'll start this week
off by talking about ways to measure this spread.

## Measures of spread

If you look at @fig-hist-width you'll see two data sets that are centered at the
same value but have very different amounts of variability. Both sets of data
have a mean of 0. But, as you can see, the values of one are spread out much
more widely than the values of the other.

```{r}
#| echo: false 
#| warning: false
#| label: fig-hist-width
#| fig-cap: |
#|  Histogram of two distributions with equal means but different spreads. 
#|  *N = 10,000* in each case.

set.seed(123)
dist_narrow <- rnorm(10000, mean = 0, sd = 1)
dist_wide <- rnorm(10000, mean = 0, sd = 3)
tibble::tibble(
  narrrow = dist_narrow,
  wide = dist_wide
) |>
  tidyr::pivot_longer(1:2) |>
  ggplot2::ggplot(aes(
    x = value,
    # group = name,
    fill = name,
    alpha = name
  )) +
  geom_histogram(color = "black", position = "identity") +
  scale_alpha_manual(values = c(1, 0.7), guide = "none") +
  scale_fill_manual(values = c("seagreen", "blue"), guide = "none") +
  theme_cowplot() + 
  NULL
```


This is why, apart from measures of central tendency, we also need measures
that tell us about the spread, or _dispersion_ of a variable. Once again, there
are several measures of spread available, and we'll talk about five of them:

1. Range

2. Interquartile range

3. Deviation

4. Variance

5. Standard deviation



### Range

The **range** of a variable is the distance between its smallest and
largest values. For example, if we gather a sample of 100 participants and the
youngest is 17 years old, and the oldest is 67 years old, then the range
of our age variable in this sample if 67 - 15 = `r 67 - 17` years.

Checking the range of a variable can tell us something about whether our data
makes sense. Let's say that we've run a study examining reading ability in
primary school age children. In this study, we've also measured the ages of the
children. If the range of our age variable is, for example, 50 years, then that
tells us that we've measured _at least_ one person that is not school age.

Beyond that, the range doesn't tell us much of the information we'd usually like
to know. This is because the range is _extremely_ **sensitive to outliers**.
What this means is that it only takes one extreme value to inflate the range. In
our school example, it might be that all but one of the people measured is
actually in the correct age range. But the range alone cannot tell us if this is
the case. You can explore the range in @exm-range-only below.

::::{.callout-tip icon="false" appearance="simple"}

:::{#exm-range-only}
#### Explore the Range
:::

To explore the **range**, first add some data points. Notice how the range is
based on the two most extreme value. You can add more data points
anywhere in the middle and the range won't change. Try clicking on **Preset 1**
and then on **Preset 2**. Notice how the data points in **Preset 1** are more
bunched in the middle, but in **Preset 2** they are more spread out. Although
the data points in the middle are different in these two displays, the extreme
points are unchanged, so the range is unchanged.





```{ojs}
//| echo: false
import {viewof preset1_range} from "@ljcolling/measures-of-spread-range"
import {viewof preset2_range} from "@ljcolling/measures-of-spread-range"
import {central_tendency_display as central_tendency_display_range} from "@ljcolling/measures-of-spread-range"
import {viewof display_range as display_range} from "@ljcolling/measures-of-spread-range"
```

```{ojs}
//| echo: false
central_tendency_display_range
```



```{ojs}
//| echo: false
//| panel: center
//| layout-ncol: 2
viewof preset1_range
viewof preset2_range
```

```{ojs}
//| echo: false
viewof display_range
```

::::

### Interquartile range

A slightly more useful measure than the range is the **interquartile range** or
IQR. The IQR is the distance between the 1st and 3rd quartiles of the data.
Quartiles, like the name suggests, are created by splitting the data into four
chunks where each chunk has the same number of observations. Or put another way,
the median splits the data into two, with half the observations on either side.
Quartiles are created by taking each of these halves and splitting them in half
again. The range covered by the middle two 25% chunks is the IQR. It is the
range that covers the middle 50% of the data.

The benefit of the IQR over a simple range is that the IQR is not sensitive to
occasional extreme values. This is because the bottom 25% and the top 25% are
discarded. However, by discarding these data, the IQR provides no information
about how spread out these outer areas are. You can explore the 
interquartile range in @exm-iqr-only.



::::{.callout-tip icon="false" appearance="simple"}

:::{#exm-iqr-only}
#### Explore the Interquartile Range
:::

To explore the **interquartile range**, first add some data points. Notice how
the interquartile range takes into account more than just the two most extreme
data points. 

Try clicking on **Preset 1** and then on **Preset 2**. Notice how the data
points in **Preset 1** are more bunched in the middle, but in **Preset 2** they
are more spread out. The two sets of data points have the same **range**, but 
they have different **interquartile ranges**.

But notice that you can also have data where the range differs and the
interquartile range stays the same. Try clicking on **Preset 3** and **Preset
4**. With these presets, the ranges change, but the interquartile ranges stay
the same.  


```{ojs}
//| echo: false
import {viewof preset1_range as preset1_iqr} from "@ljcolling/measures-of-spread-iqr"
import {viewof preset2_range as preset2_iqr} from "@ljcolling/measures-of-spread-iqr"
import {viewof preset3_iqr} from "@ljcolling/measures-of-spread-iqr"
import {viewof preset4_iqr} from "@ljcolling/measures-of-spread-iqr"
import {central_tendency_display as central_tendency_display_iqr} from "@ljcolling/measures-of-spread-iqr"
import {viewof display_range as display_iqr} from "@ljcolling/measures-of-spread-iqr"
```

```{ojs}
//| echo: false
central_tendency_display_iqr
```



```{ojs}
//| echo: false
//| panel: center
//| layout-ncol: 2
viewof preset1_iqr
viewof preset2_iqr
viewof preset3_iqr
viewof preset4_iqr
```

```{ojs}
//| echo: false
viewof display_iqr
```

::::

Both the range and the IQR work by looking at the distance between only two
observations in the entire dataset. For the range, it's the distance between the
minimum point and the maximum point. For the IQR, it's the distance between the
midpoint of the upper half and the midpoint of the lower half. As a result, you
can get arrangements of data that have very different spreads, but have the same
range or IQR. You can explore this in @exm-both. 



::::{.callout-tip icon="false" appearance="simple"}

:::{#exm-both}
#### Explore the Interquartile Range
:::

The **range** and the **interquartile range** only tell us limited information
about how spread out the data is. Two datasets can have identical ranges and
IQRs but still look very different. If you click **Preset 1** you'll see the
data bunched around the middle. If you click **Preset 2** you'll see the data
spread out along the entire range. But for both of these datasets the range and
interquartile range are the same.


```{ojs}
//| echo: false
import {viewof preset1} from "@ljcolling/measures-of-spread"
import {viewof preset2} from "@ljcolling/measures-of-spread"
import {central_tendency_display} from "@ljcolling/measures-of-spread"
import {viewof summaryText} from "@ljcolling/measures-of-spread"
import {viewof show_data_table} from "@ljcolling/measures-of-spread"
import {data_table} from "@ljcolling/measures-of-spread"
```

```{ojs}
//| echo: false
central_tendency_display
```



```{ojs}
//| echo: false
//| panel: center
//| layout-ncol: 2
viewof preset1
viewof preset2
```

```{ojs}
//| echo: false
viewof summaryText
```

```{ojs}
//| echo: false
viewof show_data_table
data_table
```


::::


### Deviation

To get a more fine-grained idea of the spread, we'll need a new way of
measuring it, one where we take into account every data-point. One way to do
this is to take each data point and calculate how far it is away from some
reference point, such as the mean. This is known as the deviation. You can
explore deviation in @exm-deviation, below.

::::{.callout-tip icon="false" appearance="simple"}

:::{#exm-deviation}
#### Explore deviation
:::

```{ojs}
//| echo: false
import {deviationplot} from "@ljcolling/samples"
import {viewof clear as dev_clear} from "@ljcolling/samples"
import {viewof show_data_table as show_dev_table} from "@ljcolling/samples"
import {data_table as dev_table} from "@ljcolling/samples"
import {sum_stats} from "@ljcolling/samples"
import {viewof show_sq_devs} from "@ljcolling/samples"
```

```{ojs}
//| echo: false
deviationplot
```

```{ojs}
//| echo: false
viewof dev_clear
```

```{ojs}
//| echo: false
//| panel: center
//| layout-ncol: 2
viewof show_dev_table
viewof show_sq_devs
```

```{ojs}
//| echo: false
dev_table(show_dev_table)
```

::::


Mathematically, we can represent deviation with the equation in @eq-dev, below:


$$D=x_i - \bar{x}$${#eq-dev}

Because we are calculating this for every data point there will be as many
deviations as we have values for our variable. To get a _single measure_, we'll
have to perform another step.

One thing we could try doing is to add up the numbers. But this won't work.
To see why, try adding a few points in @exm-deviation. Click **Show table** so
that you can see the actual values of the points, and the calculated deviations
from the mean. Try adding up all the deviations. What do you notice? 

As you can see, if you add up all the deviations, they add up to zero. Because
the mean is our midpoint, the distances for all the points higher than the mean
cancel out the distances for all the points lower than the mean.

We can get around this problem by taking the square of the deviations before
adding them up. Squaring a number will turn a negative number into a positive
number. Click **Show squared deviations** in @exm-deviation, to add a column for
the squared deviations. 

```{ojs}
//| echo: false
md`Now when we add up all the squared deviations we won't get zero. Now they add up 
to ${Math.round(sum_stats.sq_devs * 100) / 100 || "<font color='red'>warning: add some data!</font>"}.
But now we have another problem. As you add more data above, the sum of the squared
deviations will get bigger and bigger. `
```

That's not good because even big samples can have a small amount of variation,
while smaller samples can vary a lot. We want our measure of spread to be able
to capture this. To get around this, we'll move on to our next measure of spread.


### Variance

Our next measure of spread is the **variance**. The **variance** gets around the
problem of the measure of spread getting bigger when we have bigger datasets.
It's gets around this problem by working out the **average squared deviation**
from the mean. Or more precisely, the **average squared deviations** from the
**population** mean. This point is important, and we'll get to why further
down below. But for now, we'll keep it simple.

In @exm-deviation, we can work out the average squared deviations from the
**population** mean, because our **population** in this case is just _the data
points you've added to the plot_. So in this example, we have access to the
entire population, because we've specifically created it.

```{ojs}
//| echo: false
md`If we now work out the **mean** of the squared deviations, rather than the 
**sum** of the squared deviations we get: ${Math.round(sum_stats.popvar * 100) / 100 || "<font color='red'>warning: add some data!</font>"}. `
```



But usually this is
not the case. Usually, we only have access to a sample, and we don't know the
value of the population mean. Recall from Lecture 6, that sometimes the sample
mean was higher than the population mean, sometimes the sample mean was
lower than the population, and sometimes the sample mean, just by chance, was
equal to the population mean. However, without actually knowing the population
mean, we never know which one of these scenarios is the case. But does this
matter? 

Well, it turns out it does (as we'll see below). And for this reason, there's
actually two ways of calculating the variance. We use one way when we know about
characteristics of the population (this is called the **population variance**),
and we use another way when all we have access to is the sample (this is called
the **sample variance**). We'll explore both of these below, to get an
understanding of why both methods exist.

#### Population variance

We'll start with the population variance, because it's the most straightforward,
and it's calculated exactly as described above. To work out the population
variance, we just perform the following steps:

1. Compute the squared deviation between **each point in the population** from
    the **population** mean.

2. Average these together.


But what is we don't have access to every point in the population? What if we
only have access to the sample points? We can explore this scenario in @exm-pop-dev.

::::{.callout-tip icon="false" appearance="simple"}

:::{#exm-pop-dev}
##### Explore the population variance
:::

::::


So we can see from @exm-pop-dev, if we only have access to a sample, then as
long as we know the value of the population mean our estimate of the variance
will _on average_ be the same as the population variance. Even if with some
samples it will be higher and with other samples it will be lower. But this is
still an idealised scenario. In this scenario, even though we only have access
to the sample points, we still knew the value of the population mean. Usually,
we won't know the value of the population mean. Instead, we will have to compute
the mean from our sample!

#### Sample variance

When all we have access to is the sample, and we don't know the population mean,
then we'll have to modify our method of working out the variance. We can explore
this scenario in @exm-sample-dev


::::{.callout-tip icon="false" appearance="simple"}

:::{#exm-sample-dev}
##### Explore the sample variance
:::

::::

So can see from @exm-sample-dev, when all we have access to is the sample,
working out the simple **average deviation** from the sample mean gives us a
value that _on average_ is not equal to the population variance. We can see
that we'll calculate a value that, _on average_, will be lower than the
population variance. We need to somehow correct for this bias.

The way to do this, is to compute the **sample variance**. To compute the
**sample variance** we just modify the formula for computing the **population
variance** so that instead of working out a simple average (dividing by sample
size), we divide by N - 1. We can represent this mathematically with the formula
in @eq-sample-var, below:


In @exm-sample-dev, you can click on **Divide by N - 1** to see what happens. As
you can see, when we divide by one less than the sample size, the variance value
we compute will now _on average_ be the same and the variance of the population.


:::{.callout-warning}

The terminology **sample variance** and **population variance** can be very
confusing. But the way to remember it is by thinking about what you have access
to. 

If you have access to the **population characteristics** then you can compute the
**population variance**. 

If you only have access to a **sample** then you must compute the **sample
variance**.

The confusing part is that both these values, the **population variance** and
the **sample variance** will _on average_ be equal to the **variance of the
population**. The **population variance** and the **sample variance** are values
you calculate. The **variance of the population** is a feature of the
population.

:::

Because you'll almost never have access to the features of the population, it's
always the **sample variance** that you'll be calculating. In `R` the function
for computing the variance is called `var()`, and this function will give you
the **sample variance** (divided by N - 1).  


### The standard deviation

Variance is a good measure of dispersion and it's widely used. However, there
is one downside to variance, and that is that it can be difficult to interpret:
it's measured in _squared units_. For example, going back to our Salary example
from Lecture 6, if salary is measured in USD, then the **variance** would be
expressed in USD^2^, whatever that means!

Fortunately, the solution to this problem is easy: we simply take the square
root of the variance. This measure is called the **standard deviation**. Just
like with variance, there is a **population** standard deviation, denoted with
$\sigma$. And a **sample** standard deviation, denoted with $s$ or $SD$.

The **sample** standard deviation is what we compute when all we have access to
is the **sample**. It's the square root for the **sample** variance. The
**population** standard deviation is what we compute when we have access to the
**population** characteristics. It's the square root of the **population**
variance. Because we almost never have access to the population characteristics
you'll almost always be calculating the **sample standard deviation**. In `R`,
the function for computing the standard deviation is called `sd()` and this
computes the **sample** standard deviation (that is, it uses N - 1).


:::{.callout-tip collapse="true"} 
#### Why squared and not the absolute value

To turn all the deviations into positive values we square these values. 
But you might be thinking, why do we square them and why don't we just
take the **absolute value** instead? The short answer to this question
is that taking the **mean of the absolute values** doesn't really 
give us the kind of measure we want. To see what I mean, take a look
and the plot below. Try clicking on **Preset 1** and then **Preset 2**.

When you click **Preset 1** the data are more spread out than when you hit
**Preset 2**. But the **mean of the absolute values of the deviations** is the
same in both plots. That's not really what we want. But notice what happens to
the **standard deviation**, which is calculated from the **squared
deviations**. The **standard deviation** changes between the two displays so
that it is smaller when the points are less spread out and larger when the
points are more spread.

:::


## Understanding the relationship between samples and populations

Now we have some tools for describing measurements, both in terms of where
they are centered (the **mean**) and in terms of how spread out they are (the
**standard deviation**). With these tools in hand, we can return to the problem
we talked about last lecture. That is, the problem of knowing whether our sample
resembles the population.

In the previous lecture, we saw that when we took samples from the population,
sometimes the sample mean was higher than the population mean, and sometimes it
was lower. But _on average_ the sample mean was the same as the population mean.
We can see this again in @exm-sample-means.

<!-- TODO:

Add plot that shows points higher and lower than population mean
Add plot showing that the sample mean converges on the population mean

-->

```{r}
#| echo: false
#| message: false
source("./two_plots.r")
```

In the previous lecture, I also said that we wouldn't know whether a particular
sample mean was higher, lower, close to, or far away from the population mean.
We can't know this, because we don't know the value of the population mean. But
one thing we can know, is how much, _on average_, the sample means will deviate
from the population. To see what I mean by this, let's say a look at the two
plots in @fig-se. In @fig-se​a you can see the means of 10 different samples
taken from the sample population. Sometimes the sample mean is higher than the
population mean, sometimes it's lower. But the thing I want you to notice is
how spread out the values are. In @fig-se​b you can see the means of a
different collection of 10 samples. Again, some are higher and some are lower.
But notice the spread of the values. If we were to calculate the standard
deviation for @fig-se​a, we would find that the sample means deviate from the
population mean by an average of `r round(sd(d1$y), 2)`. And if we were to
calculate the standard deviation for @fig-se​b, we would find that the sample
means deviate from the population mean by an average of `r round(sd(d2$y), 2)`. 

Now we're not using the **standard deviation** to tell us about the spread of
the values in our sample. Instead, we're using the idea to tell us about the
spread of our sample means. This **standard deviation**, the **standard
deviations of the sample means from the population mean** has a special name.
It is called the **standard error of the mean**. 

<!--
We'll learn about two factors that influence the size of the **standard error
of the mean**. The first factor has to do with features of our sample, and the
second will depend on a feature of the population. We'll cover that in the next
lecture, but if you think about it, you might be able to work out what they are
yourself.
-->

<!-- TODO: These can just be ggplots 
But they'll need some styling etc
-->

```{r}
#| echo: false 
#| warning: false
#| label: fig-se
#| fig-cap: !expr glue::glue("(a) 10 samples with a standard deviation of {round(sd(d1$y), 2)} (b) 10 samples with a standard deviation of {round(sd(d2$y), 2)}") 
p1 + p2 + plot_annotation(tag_levels = "a")
```

The **standard error** will be an important concept and we'll talk about it
again in upcoming lectures. But for now, I just want you to keep this idea---the idea
that individual sample means are spread out around the population mean---in the back 
of your mind.

<!--

TODO: Move to lecture 8?

Let's thing about what these standard deviation values tell us. They tell us,
that _on average_ the samples in @fig-plot-a more closely resemble the
population than the samples in @fig-plot-b. This seems like it could be useful
information. In fact, it is so useful that this measure has a special name. It
is called the **standard error of the mean** or more commonly just the
**standard error**. And there is a way for use to *estimate* it. We'll learn how
to estimate it in the next lecture, but for now I want to develop some
intuitions about what will influence it's value.

To figure out what will influence how spread out the sample means are around
the population mean, we'll do a simple thought experiment. In the thought
experiment, we'll think of two **extreme cases**.

First, consider the case where **every value in the population** is
**identical**. For example, imagine we're interested in the height of people in
the UK, but it just so happens that everyone in the UK is **exactly** 178cm
tall. If we were to take samples from this population, and work out the sample
mean, then all the sample means will be identical to the population mean. 

Or put more technically: If the standard deviation of the population is 0 (all the
values in the population are the same) then the standard error would also be 0.
But if the population standard deviation was some value other than 0 (all the
values in the population weren't exactly the same) then the standard error would
be some value other than 0.

In the second scenario, consider the case where we take samples that are so big
that they **include every member of the population**. That is, in our height
example, our **"sample"** would actually include all the people in the UK. If we
did this, then **by definition** our sample mean would be same as the population
mean. Collecting samples in this way would mean all the sample means would be
the same, and they would all be the same as the population mean.

Or put more technically: If the sample size is so big that it includes the
entire population then the standard error would be 0. If the sample size were
smaller than the entire population, then the standard error would be some value
other than 0.

Based on this reasoning, we can say that two things will influence whether your
_sample_ resembles your _population_. These are 1) the amount of **variation**
in our population, and 2) the **size** of our sample. We'll cover the formula
for the standard error in the next lecture, but from this little thought
experiment we can correctly assume that the formula will have to include at
least these two bits of information: An estimate of the standard deviation of
the population, which we can get from the **sample standard deviation**. And
some measure of the size of our sample, which we can get from just counting how
big our sample is.

-->