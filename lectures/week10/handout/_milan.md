
## Overview

[**Why use tables and plots?**](#why)

[**Tables**](#tables)
- What makes a good table?
- Frequency tables
- Summary tables

[**Plotting basics**](#plots)
- What makes a good plot?
- Structure of a plot
- Frequency plots
- Summary plots

&lt;br&gt;

.center[**All plots and tables in the slides made in `R`**]

---

## Data



- 4,468 films pulled from [IMDB.com](https://www.imdb.com)

- **Inclusion criteria**
  - Rated at least 5,000 times
  - Released in 2010 or later

- Data available [here](./assets/movies_tidy.csv)

&lt;small&gt;
Of the 4,468 titles, 52 (1.16%) were produced, or co-produced by at least one African country, 3,009 (67.35%) by at least one country in the Americas, 1,058 (23.68%) by a country in Asia, 1,604 (35.9%) in Europe, and 153 (3.42%) in Oceania.
The sum of these numbers is necessarily higher than the total number of titles in the data set, as one title can have multiple production attributions and so can count towards several "Continent" categories.

The number of IMDB ratings ranged from 5,003 to 2.03&amp;times;10&lt;sup&gt;6&lt;/sup&gt;, with a mean of 6.31&amp;times;10&lt;sup&gt;4&lt;/sup&gt; and _SD_ of 1.23&amp;times;10&lt;sup&gt;5&lt;/sup&gt;. The average user rating for a given title spanned the range 1&amp;ndash;9.2; _M_=6.37, _SD_=1.02.

Information on estimated budget was only available for 2,170 of the titles in the data set: 18&amp;ndash;3.56&amp;times;10&lt;sup&gt;8&lt;/sup&gt;, _M_=3.96&amp;times;10&lt;sup&gt;7&lt;/sup&gt;, _SD_=5.09&amp;times;10&lt;sup&gt;7&lt;/sup&gt;.
&lt;/small&gt;

---

name: why

## Why and when to use tables and plots?

### Why 

- Plots and tables allow us to convey a lot of information using relatively small amounts of space
- They structure the information we're communicating so that it's easier to understand than a wall of text
- Good tables and plots are simply #aesthetic

### When 

- Tables and plot are not just for reports
- They are a good way of exploring data before analysis in order for us to get to know them
- Not all plots and table we create should be put in reports/papers
- If we are including them in reports/papers, they should be used to convey important information that would be cumbersome to convey in body text

---

name: tables

## Tables

- Tidy way of presenting a lot of numbers
- A good table should be **easy to read, well-organised, and clear**
- Good for exploring and summarising data (this lecture), and presenting results (future modules)

### Structural elements

- **Number**: all tables should be numbered and the number should be referenced in paper/report
- **Title**: should be descriptive
- **Header**: clearly indicates what the data in each column mean
- **Body**: logically organised into rows and columns
- **Note**: optional, provides additional information necessary to correctly interpret data in the table

---

## Frequency tables

&lt;table class="table" style="width: auto !important; margin-left: auto; margin-right: auto;border-bottom: 0;"&gt;
&lt;caption&gt;Table 1&lt;br&gt;&lt;em&gt;Distribution of film titles by continent with absolute and relative frequencies&lt;/em&gt;
&lt;/caption&gt;
 &lt;thead&gt;
  &lt;tr&gt;
   &lt;th style="text-align:left;"&gt; Continent &lt;/th&gt;
   &lt;th style="text-align:right;"&gt; &lt;em&gt;N&lt;/em&gt; &lt;sup class="symbol"&gt;*&lt;/sup&gt; &lt;/th&gt;
   &lt;th style="text-align:right;"&gt; %&lt;sup class="symbol"&gt;†&lt;/sup&gt; &lt;/th&gt;
  &lt;/tr&gt;
 &lt;/thead&gt;
&lt;tbody&gt;
  &lt;tr&gt;
   &lt;td style="text-align:left;"&gt; Africa &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 52 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 1.2 &lt;/td&gt;
  &lt;/tr&gt;
  &lt;tr&gt;
   &lt;td style="text-align:left;"&gt; Americas &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 3,009 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 67.3 &lt;/td&gt;
  &lt;/tr&gt;
  &lt;tr&gt;
   &lt;td style="text-align:left;"&gt; Asia &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 1,058 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 23.7 &lt;/td&gt;
  &lt;/tr&gt;
  &lt;tr&gt;
   &lt;td style="text-align:left;"&gt; Europe &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 1,604 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 35.9 &lt;/td&gt;
  &lt;/tr&gt;
  &lt;tr&gt;
   &lt;td style="text-align:left;"&gt; Oceania &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 153 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 3.4 &lt;/td&gt;
  &lt;/tr&gt;
&lt;/tbody&gt;
&lt;tfoot&gt;
&lt;tr&gt;&lt;td style="padding: 0; " colspan="100%"&gt;&lt;span style="font-style: italic;"&gt;Note: &lt;/span&gt;&lt;/td&gt;&lt;/tr&gt;
&lt;tr&gt;&lt;td style="padding: 0; " colspan="100%"&gt;
&lt;sup&gt;&lt;/sup&gt; Based on a sample of 4,468 full feature films released since 2010 with 5,000 or more ratings on IMDB.com.&lt;/td&gt;&lt;/tr&gt;
&lt;tr&gt;&lt;td style="padding: 0; " colspan="100%"&gt;
&lt;sup&gt;*&lt;/sup&gt; Column does not add up to total number of titles, as a single title can have multiple continent attributions.&lt;/td&gt;&lt;/tr&gt;
&lt;tr&gt;&lt;td style="padding: 0; " colspan="100%"&gt;
&lt;sup&gt;†&lt;/sup&gt; Percentage of total number of titles (does not add up to 100%).&lt;/td&gt;&lt;/tr&gt;
&lt;/tfoot&gt;
&lt;/table&gt;

---

## Grouped frequency tables

.small[
&lt;table style="NAborder-bottom: 0;"&gt;
&lt;caption&gt;Table 2&lt;br&gt;&lt;em&gt;Distribution of film titles by genres for Europe and the Americas&lt;/em&gt;
&lt;/caption&gt;
 &lt;thead&gt;
&lt;tr&gt;
&lt;th style="empty-cells: hide;border-bottom:hidden;" colspan="1"&gt;&lt;/th&gt;
&lt;th style="border-bottom:hidden;padding-bottom:0; padding-left:3px;padding-right:3px;text-align: center; border-bottom: solid 1px #644e48; padding-bottom: 3px" colspan="2"&gt;&lt;div style=""&gt;Americas&lt;/div&gt;&lt;/th&gt;
&lt;th style="border-bottom:hidden;padding-bottom:0; padding-left:3px;padding-right:3px;text-align: center; border-bottom: solid 1px #644e48; padding-bottom: 3px" colspan="2"&gt;&lt;div style=""&gt;Europe&lt;/div&gt;&lt;/th&gt;
&lt;/tr&gt;
  &lt;tr&gt;
   &lt;th style="text-align:left;"&gt; Continent &lt;/th&gt;
   &lt;th style="text-align:right;"&gt; &lt;em&gt;N&lt;/em&gt; &lt;sup class="symbol"&gt;*&lt;/sup&gt; &lt;/th&gt;
   &lt;th style="text-align:right;"&gt; %&lt;sup class="symbol"&gt;†&lt;/sup&gt; &lt;/th&gt;
   &lt;th style="text-align:right;"&gt; &lt;em&gt;N&lt;/em&gt; &lt;sup class="symbol"&gt;*&lt;/sup&gt; &lt;/th&gt;
   &lt;th style="text-align:right;"&gt; %&lt;sup class="symbol"&gt;†&lt;/sup&gt; &lt;/th&gt;
  &lt;/tr&gt;
 &lt;/thead&gt;
&lt;tbody&gt;
  &lt;tr&gt;
   &lt;td style="text-align:left;"&gt; Drama &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 1,704 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 56.6 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 1,075 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 67.0 &lt;/td&gt;
  &lt;/tr&gt;
  &lt;tr&gt;
   &lt;td style="text-align:left;"&gt; Thriller &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 1,142 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 38.0 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 620 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 38.7 &lt;/td&gt;
  &lt;/tr&gt;
  &lt;tr&gt;
   &lt;td style="text-align:left;"&gt; Comedy &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 1,069 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 35.5 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 439 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 27.4 &lt;/td&gt;
  &lt;/tr&gt;
  &lt;tr&gt;
   &lt;td style="text-align:left;"&gt; Action &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 779 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 25.9 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 363 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 22.6 &lt;/td&gt;
  &lt;/tr&gt;
  &lt;tr&gt;
   &lt;td style="text-align:left;"&gt; Romance &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 551 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 18.3 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 325 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 20.3 &lt;/td&gt;
  &lt;/tr&gt;
  &lt;tr&gt;
   &lt;td style="text-align:left;"&gt; Crime &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 547 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 18.2 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 295 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 18.4 &lt;/td&gt;
  &lt;/tr&gt;
  &lt;tr&gt;
   &lt;td style="text-align:left;"&gt; Adventure &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 541 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 18.0 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 267 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 16.6 &lt;/td&gt;
  &lt;/tr&gt;
  &lt;tr&gt;
   &lt;td style="text-align:left;"&gt; Other &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 2,934 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 97.5 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 1,548 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 96.5 &lt;/td&gt;
  &lt;/tr&gt;
&lt;/tbody&gt;
&lt;tfoot&gt;
&lt;tr&gt;&lt;td style="padding: 0; " colspan="100%"&gt;&lt;span style="font-style: italic;"&gt;Note: &lt;/span&gt;&lt;/td&gt;&lt;/tr&gt;
&lt;tr&gt;&lt;td style="padding: 0; " colspan="100%"&gt;
&lt;sup&gt;&lt;/sup&gt; Based on a sample of 4,468 full feature films released since 2010 with 5,000 or more ratings on IMDB.com.&lt;/td&gt;&lt;/tr&gt;
&lt;tr&gt;&lt;td style="padding: 0; " colspan="100%"&gt;
&lt;sup&gt;*&lt;/sup&gt; Column does not add up to total number of titles, as a single title can have multiple genre attributions.&lt;/td&gt;&lt;/tr&gt;
&lt;tr&gt;&lt;td style="padding: 0; " colspan="100%"&gt;
&lt;sup&gt;†&lt;/sup&gt; Percentage of total number of titles within given continent (does not add up to 100%).&lt;/td&gt;&lt;/tr&gt;
&lt;/tfoot&gt;
&lt;/table&gt;
]

---

## Summary tables

&lt;table class="table" style="margin-left: auto; margin-right: auto;"&gt;
&lt;caption&gt;Table 3&lt;br&gt;&lt;em&gt;Summary statistics of the measured continuous variables&lt;/em&gt;
&lt;/caption&gt;
 &lt;thead&gt;
  &lt;tr&gt;
   &lt;th style="text-align:left;text-align: center;"&gt;  &lt;/th&gt;
   &lt;th style="text-align:right;text-align: center;"&gt; &lt;em&gt;N &lt;/em&gt;
&lt;/th&gt;
   &lt;th style="text-align:right;text-align: center;"&gt; Min &lt;/th&gt;
   &lt;th style="text-align:right;text-align: center;"&gt; Max &lt;/th&gt;
   &lt;th style="text-align:right;text-align: center;"&gt; &lt;em&gt;M&lt;/em&gt; &lt;/th&gt;
   &lt;th style="text-align:right;text-align: center;"&gt; &lt;em&gt;SD&lt;/em&gt; &lt;/th&gt;
   &lt;th style="text-align:right;text-align: center;"&gt; &lt;em&gt;SEM&lt;/em&gt; &lt;/th&gt;
  &lt;/tr&gt;
 &lt;/thead&gt;
&lt;tbody&gt;
  &lt;tr&gt;
   &lt;td style="text-align:left;"&gt; Average IMDB rating &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 4,468 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 1 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 9.2 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 6.37 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 1.02 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 0.02 &lt;/td&gt;
  &lt;/tr&gt;
  &lt;tr&gt;
   &lt;td style="text-align:left;"&gt; Number of IMDB ratings &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 4,468 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 5,003 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 2.03×10&lt;sup&gt;6&lt;/sup&gt; &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 6.31×10&lt;sup&gt;4&lt;/sup&gt; &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 1.23×10&lt;sup&gt;5&lt;/sup&gt; &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 1844.18 &lt;/td&gt;
  &lt;/tr&gt;
  &lt;tr&gt;
   &lt;td style="text-align:left;"&gt; Estimated budget (USD) &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 2,170 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 18 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 3.56×10&lt;sup&gt;8&lt;/sup&gt; &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 3.96×10&lt;sup&gt;7&lt;/sup&gt; &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 5.09×10&lt;sup&gt;7&lt;/sup&gt; &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 1.09×10&lt;sup&gt;6&lt;/sup&gt; &lt;/td&gt;
  &lt;/tr&gt;
  &lt;tr&gt;
   &lt;td style="text-align:left;"&gt; Opening week grossing (USD) &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 2,842 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 63 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 3.57×10&lt;sup&gt;8&lt;/sup&gt; &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 1.14×10&lt;sup&gt;7&lt;/sup&gt; &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 2.52×10&lt;sup&gt;7&lt;/sup&gt; &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 4.73×10&lt;sup&gt;5&lt;/sup&gt; &lt;/td&gt;
  &lt;/tr&gt;
  &lt;tr&gt;
   &lt;td style="text-align:left;"&gt; Runtime in minutes &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 4,387 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 45 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 321 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 109.22 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 20.33 &lt;/td&gt;
   &lt;td style="text-align:right;"&gt; 0.31 &lt;/td&gt;
  &lt;/tr&gt;
&lt;/tbody&gt;
&lt;/table&gt;


---

exclude: ![:live]

&lt;iframe src="https://embed.polleverywhere.com/discourses/IXL29dEI4tgTYG0zH1Sef?controls=none&amp;short_poll=true" width="800" height="600" frameBorder="0"&gt;&lt;/iframe&gt;

---

name: plots

## Plots

- Sometimes, a picture is worth a thousand words
- Great for communicating information about data that takes a lot of space to explain in writing
- Good graphics should be both clear and packed full of information

### Structural elements

- **Number**: just like tables, all plots should be numbered and the number should be referenced
- **Title**: should be descriptive
- **Axes**: clearly labelled, with sensible ticks along them, and **units of measurement**
- **Graphics**: clear, well designed, good size
- **Legend**: if graphical elements are used to distinguish levels of variables, legend must be provided
- **Note**: optional, provides additional information necessary to correctly interpret the plot


---

## Frequency plots

- Good for exploring distributions of data

- They are intended for you, the analyst, not for the readers of your paper/report

- They can be nice but take up too much space, use up too much ink, and convey too little information

---

## Histogram

- Useful for plotting distributions of **continuous** variables only (_interval_ and _ratio_)
- Data need to be binned; width of individual bins is our decision, explicit or implicit

Figure 1

_A histogram of the distribution of average viewer ratings in the sample_

.codePanel[

```r
df %&gt;%
  distinct(title, .keep_all = T) %&gt;%
  ggplot(aes(x = rating)) +
  geom_bar(fill = "steelblue") +
  labs(x = "Mean viewer rating", y = "Count") +
  scale_x_continuous(breaks = 1:10)
```

![](index_files/figure-html/unnamed-chunk-5-1.png)&lt;!-- --&gt;]

---

## Density plots

- Also for continuous variables only
- Simulate what a histogram with infinitely narrow bins would look like

Figure 2

_Density plots provide a smoother representation of the distribution of a variable_

.codePanel[

```r
df %&gt;%
  distinct(title, .keep_all = T) %&gt;%
  ggplot(aes(x = rating)) +
  geom_density(fill = "#3d755b88", colour = "#3d755b") +
  labs(x = "Mean viewer rating", y = "Density") +
  scale_x_continuous(breaks = 1:10)
```

![](index_files/figure-html/unnamed-chunk-6-1.png)&lt;!-- --&gt;]

---

## Bar charts

- Visualise distributions of **categorical** data (_nominal_ and _ordinal_)

- They are still used for summarising data 

- Even the APA website shows them in their [list of sample figures](https://apastyle.apa.org/style-grammar-guidelines/tables-figures/sample-figures#bar)

- You shouldn't do it though - it's a waste of space!

---

## Simple bar chart

Figure 3

_A bar chart showing the number of films produced within a region_

.codePanel[

```r
df %&gt;%
  distinct(title, country, .keep_all = T) %&gt;%
  mutate(region = factor(region)) %&gt;%
  ggplot(aes(x = region)) +
  geom_bar(fill = "#00356888", colour="#003568") +
  labs(x = "Region", y = "Count") +
  theme(axis.text.x = element_text(angle = 30, vjust = 1, hjust=1))
```

&lt;img src="index_files/figure-html/unnamed-chunk-7-1.png" width="58%" /&gt;]

&lt;small&gt;
_Note._
Categorisation of countries into regions is based on World Bank Development Indicators.
&lt;/small&gt;

---

## Bar charts

.small[
- Colour isn't necessary here but it's at least meaningful (British Board of Film Classification labels)

Figure 4

_Bar charts can also show distributions of ordinal variables_
]
  
.codePanel[

```r
df %&gt;%
  distinct(title, .keep_all=T) %&gt;%
  mutate(cert = forcats::fct_explicit_na(cert)) %&gt;%
  ggplot(aes(x = cert, fill = cert, colour = cert)) +
  geom_bar() +
  labs(x = "BBFC Certificate", y = "Count") +
  scale_fill_manual(values = c("#2aa832", "#fab900", "#ef7910",
                               "#ef7910", "#ec5692", "#d8011e", "#007ec8", "#aaaaaa"),
                    guide=F) +
  scale_color_manual(values = c("#2aa832", "#fab900", "#ef7910",
                                "#ef7910", "#ec5692", "#d8011e", "#007ec8", "#aaaaaa"),
                     guide=F) +
  geom_hline(yintercept = rep(seq(500, 2000, by = 500), 2), size = 2, colour = bg_col)
```

&lt;img src="index_files/figure-html/unnamed-chunk-8-1.png" width="80%" /&gt;]

&lt;small&gt;
*Note.* U: universally suitable; PG: parental guidance recommended; 12: suitable for children from 12 years of age; 12A: suitable for children from 12 years of age accompanied by adult; 15: suitable for 15-year-olds and older; 18: only suitable for adults.
&lt;/small&gt;

---

## Bar charts

.small[
- Sometimes it makes more sense to flip them horizontally
- Grid lines can help comparing things in all kinds of plots

Figure 5

_An example of a horizontal bar chart with grid lines_
]

.codePanel[

```r
df %&gt;%
  distinct(title, genre, .keep_all = T) %&gt;%
  mutate(genre = factor(genre) %&gt;%
           forcats::fct_infreq() %&gt;%
           forcats::fct_rev()) %&gt;%
  ggplot(aes(x = genre)) +
  geom_bar(fill = "#3d755b88", colour = "#3d755b") +
  coord_flip() +
  labs(x = "Genre", y = "Count") +
  theme(panel.grid.major.x = element_line(size=0.1, colour = "#00000044"),
        panel.grid.minor.x = element_line(size=0.1, colour = "#00000022"))
```

&lt;img src="index_files/figure-html/unnamed-chunk-9-1.png" width="80%" /&gt;]


---

## Summary plots

- Unlike frequency plots, their primary aim is to summarise the data in term of key statistics

- They are often used to compare variables across groups

- *Some of them* can be used to gauge **differences between groups** and **relationships between variables**

- They are _not a substitute for data analysis!_

---

## Box plot

- AKA box-and-whiskers plots

Figure 6

_A box plot gives a more detailed info about a variable's distribution and basic descriptive statistics_

.codePanel[

```r
df %&gt;%
  distinct(title, .keep_all = T) %&gt;%
  ggplot(aes(x = rating)) +
  geom_boxplot(outlier.fill = "#e20000", outlier.shape = 21, width = 0.2) +
  annotate("line", x = c(6.4, 6.4), y = c(-0.1, 0.1), colour = "#007ec8", size = 1.5) +
  labs(x = "Mean viewer rating", y = "") +
  coord_cartesian(ylim = c(-0.3, 0.3)) +
  scale_x_continuous(breaks = 0:11) +
  theme(axis.ticks.y = element_blank(),
        axis.text.y = element_blank(), axis.line.y = element_blank())
```

![](index_files/figure-html/unnamed-chunk-10-1.png)&lt;!-- --&gt;]

---

## Box plot

- AKA box-and-whiskers plots

Figure 6

_A box plot gives a more detailed info about a variable's distribution and basic descriptive statistics_

.codePanel[

```r
df %&gt;%
  distinct(title, .keep_all = T) %&gt;%
  ggplot(aes(x = rating)) +
  geom_boxplot(outlier.fill = "#e20000", outlier.shape = 21, width = 0.2) +
  labs(x = "Mean viewer rating", y = "") +
  annotate("text", x = 6.4, y = -0.18, label="Median", size = 7, colour="#007ec8") +
  annotate("text", x = 2.4, y = 0.12, label="Outliers", size = 7, colour = "#e20000") +
  annotate("text", x = 6.5, y = 0.23, label="IQR", size = 6, colour=default_col) +
  annotate("line", x = c(5.8, 7.1), y = c(0.15, 0.15), colour = default_col) +
  annotate("line", x = c(5.8, 5.8), y = c(0.12, 0.15), colour = default_col) +
  annotate("line", x = c(7.1, 7.1), y = c(0.12, 0.15), colour = default_col) +
  annotate("line", x = c(6.4, 6.4), y = c(-0.1, 0.1), colour = "#007ec8", size = 1.5) +
  coord_cartesian(ylim = c(-0.3, 0.3)) +
  scale_x_continuous(breaks = 0:11) +
  theme(axis.ticks.y = element_blank(),
        axis.text.y = element_blank(), axis.line.y = element_blank())
```

![](index_files/figure-html/unnamed-chunk-11-1.png)&lt;!-- --&gt;]

---

## Grouped box plot

Figure 7

_Boxplots are useful to compare distributions of a variable between groups_

.codePanel[

```r
df %&gt;%
  distinct(title, continent, .keep_all = T) %&gt;%
  ggplot(aes(x = continent, y = rating)) +
  geom_boxplot(outlier.fill = "#e20000", outlier.shape = 21, varwidth = T) +
  labs(x = "Continent", y = "Mean viewer rating") +
  theme(panel.grid.major.y = element_line(colour = "#00000033"),
        panel.grid.minor.y = element_line(colour = "#00000010"))
```

![](index_files/figure-html/unnamed-chunk-12-1.png)&lt;!-- --&gt;]

&lt;small&gt;
*Note.* Width of boxes proportional to number of observation per category of the Continent variable
&lt;/small&gt;
---

## [Violin plot](https://xkcd.com/1967/)

.small[
Figure 8

_Violin plots with inserted box plots showing mean viewer rating by different levels of BBFC certificate_
]

.codePanel[

```r
df %&gt;%
  distinct(title, .keep_all = T) %&gt;%
  mutate(cert = forcats::fct_explicit_na(cert)) %&gt;%
  ggplot(aes(x = cert, y = rating, fill = cert)) +
  geom_violin(draw_quantiles = T, trim = F) +
  geom_boxplot(width=0.1, outlier.size = 2, fill = "white") +
  labs(x = "BBFC Certificate", y = "Mean viewer rating") +
  scale_fill_manual(values = c("#2aa832", "#fab900", "#ef7910",
                               "#ef7910", "#ec5692", "#d8011e", "#007ec8", "#aaaaaa"),
                    guide=F) +
  theme(panel.grid.major.y = element_line(colour = "#00000033"),
        panel.grid.minor.y = element_line(colour = "#00000010"))
```

&lt;img src="index_files/figure-html/unnamed-chunk-13-1.png" width="80%" /&gt;]

&lt;small&gt;
*Note.* U: universally suitable; PG: parental guidance recommended; 12: suitable for children from 12 years of age; 12A: suitable for children from 12 years of age accompanied by adult; 15: suitable for 15-year-olds and older; 18: only suitable for adults.
&lt;/small&gt;

---

## Errorbar plot

- Errorbar plots are great for showing means and spread/inferential statistics

- Some of them can be used to gauge _statistical_ differences between groups

- Error bars can show several things (*e.g,* standard deviations, standard errors, their multiples)

- Plot should clearly indicate what they represent

- Pay attention to what the error bars mean

- Interpretation of plots changes based on what the bars show!

---

## Errorbar plot

Figure 9

_Errorbar plot showing mean estimated budget of movies by level of BBFC certificate_

.codePanel[

```r
df %&gt;%
  distinct(title, .keep_all = T) %&gt;%
  mutate(cert = forcats::fct_explicit_na(cert)) %&gt;%
  ggplot(aes(x = cert, y = budget/1000000, fill = cert)) + 
  stat_summary(fun.data = mean_se, geom = "errorbar", width=0.1, fun.args = 2) +
  stat_summary(fun.y = mean, geom = "point", pch=23, size = 4) + 
  labs(x = "BBFC Certificate", y = "Budget in millions of USD") +
  scale_fill_manual(values = c("#2aa832", "#fab900", "#ef7910",
                               "#ef7910", "#ec5692", "#d8011e", "#007ec8", "#aaaaaa"),
                    guide=F) +
  theme(panel.grid.major.y = element_line(colour = "#00000033"),
        panel.grid.minor.y = element_line(colour = "#00000010"))
```

![](index_files/figure-html/unnamed-chunk-14-1.png)&lt;!-- --&gt;]

&lt;small&gt;
*Note.* Error bars represent &amp;pm;2 _SE_ from the mean.
&lt;/small&gt;

---

## Errorbar plot

Figure 10

_Errorbar plot showing mean estimated budget of movies by level of BBFC certificate_

.codePanel[

```r
df %&gt;%
  distinct(title, .keep_all = T) %&gt;%
  mutate(cert = forcats::fct_explicit_na(cert)) %&gt;%
  ggplot(aes(x = cert, y = budget/1000000, fill = cert)) + 
  stat_summary(fun.data = function (x, mult = 1) {
    x &lt;- stats::na.omit(x)
    sd &lt;- stats::sd(x)
    mean &lt;- mean(x)
    ggplot2:::new_data_frame(list(y = mean, ymin = mean - sd, ymax = mean + 
                                    sd), n = 1)},
    geom = "errorbar", width=0.1) +
  stat_summary(fun.y = mean, geom = "point", pch=23, size = 4) + 
  labs(x = "BBFC Certificate", y = "Budget in millions of USD") +
  scale_fill_manual(values = c("#2aa832", "#fab900", "#ef7910", 
                               "#ef7910", "#ec5692", "#d8011e", "#007ec8", "#aaaaaa"),
                    guide=F) +
  scale_y_continuous(breaks = seq(0, 160, by = 20)) +
  theme(panel.grid.major.y = element_line(colour = "#00000033"),
        panel.grid.minor.y = element_line(colour = "#00000010"))
```

![](index_files/figure-html/unnamed-chunk-15-1.png)&lt;!-- --&gt;]

&lt;small&gt;
*Note.* Error bars represent &amp;pm;1 _SD_ from the mean.
&lt;/small&gt;

---

## Scatter plot

- Best way to show **relationships between two continuous variables**.

Figure 11

_The relationship between a film's budget and its opening week box office performance_


.codePanel[

```r
df %&gt;%
  distinct(title, .keep_all = T) %&gt;%
  ggplot(aes(x = budget/1000000, y = opening_week/1000000)) + 
  geom_point(colour = "orangered", size = 2, alpha = .2,
             position = position_jitter(width = 1, height = 1)) +
  labs(x = "Budget in millions of USD", y = "Opening week grossing\n(millions of USD)")
```

![](index_files/figure-html/unnamed-chunk-16-1.png)&lt;!-- --&gt;]

---

## Line plot

.small[
- Great for highlighting **repeated measures** and **within-subject structure** 

Figure 12

_Average film runtime over time in the second decade of the 21&lt;sup&gt;st&lt;/sup&gt; century_
]

.codePanel[

```r
df %&gt;%
  distinct(title, continent, .keep_all = T) %&gt;%
  ggplot(aes(x = ordered(year), y = runtime, group=1)) + 
  stat_summary(fun.data = "mean_se", geom = "errorbar", width = 0, lty = 1) +
  stat_summary(fun = mean, geom = "line") + 
  stat_summary(fun = mean, geom = "point", size = 4, colour="steelblue") + 
  labs(x = "Year of release", y = "Runtime in minutes") +
  coord_cartesian(ylim=c(105, 115)) +
  scale_y_continuous(breaks = 105:115)
```

![](index_files/figure-html/unnamed-chunk-17-1.png)&lt;!-- --&gt;]

&lt;small&gt;
*Note.* Error bars represent &amp;pm;1 _SE_ from the mean.
&lt;/small&gt;


---

## Lot of info!

Figure 13

_Mean number of IMDB viewer rating of films by continent over time_

.codePanel[

```r
df %&gt;%
  distinct(title, continent, .keep_all = T) %&gt;%
  ggplot(aes(x = ordered(year), y = n_ratings/100000,
             group = continent, fill = continent, shape = continent)) + 
  stat_summary(fun.data = "mean_se", geom = "errorbar", width = 0, lty = 1) +
  stat_summary(fun.y = mean, geom = "line") + 
  stat_summary(fun.y = mean, geom = "point", size = 3) + 
  labs(x = "Year of release", y = "Number of IMDB ratings\n(in 100k)") +
  scale_shape_manual(values=21:25, name="Continent") +
  scale_fill_brewer(palette = "Set1", name="Continent") +
  theme(legend.position = c(.77, 0.74)) +
  coord_cartesian(ylim = c(0, 4.1))
```

![](index_files/figure-html/unnamed-chunk-18-1.png)&lt;!-- --&gt;]

&lt;small&gt;
*Note.* Error bars represent &amp;pm;1 _SE_ from the mean.
&lt;/small&gt;


---

exclude: ![:live]

&lt;iframe src="https://embed.polleverywhere.com/discourses/IXL29dEI4tgTYG0zH1Sef?controls=none&amp;short_poll=true" width="800" height="600" frameBorder="0"&gt;&lt;/iframe&gt;

---

## Sometimes less is more!

- Plots and tables should _supplement_ body text, not repeat what's already there

- There's no need to show the same thing in a table AND in a plot at the same time!

- Always make sure font size and size of graphics are big enough to be easily legible

- For more detailed APA guidelines, see the [APA website](https://apastyle.apa.org/style-grammar-guidelines/tables-figures)

  - They also provide sample [tables](https://apastyle.apa.org/style-grammar-guidelines/tables-figures/sample-tables) and [figures](https://apastyle.apa.org/style-grammar-guidelines/tables-figures/sample-figures). (But remember, not bar charts for summary stats! Not ever!)

---