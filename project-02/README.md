# Data Visualization

> Per Sander.

## Mini-Project 2

In this project, I explored data from the Boston marathon 2017. 
The goal of the project was to explore interactive graphs and spatial visualization. 
The library ggigraph with geom_sf was used for the graphs. 
The data included data such as age country of origin and various times. 

The data seems to have a weak trend that counties and countries with lower participation seem to be doing better then counties and countries with high participation.
However, these results can be affected by the very low sample size of countries and counties with low participation. 
Another possible explanation is that as travel becomes more difficult the remaining participants take the marathon more seriously.

## 1 Interactive Chart

The following interactive boxplot graph was created: *(check out sander_project_01.html for an interactive version)*

<img src="../figures/project-1-graph4-non-interactive.png"/>

When hovering over the boxplots for each year additional information for the data for that year is shown as seen in the image below:

<img src="../figures/project-1-graph4-non-interactive-showcase.png"/>

The additonal data shows what influence the type of cars had to the overall population as well as the exact average for the population.

## 2 Accessibility

For accessibility fig.alt text were included for each graph, and colorblind safe colors and pallets were chosen.(viridis magma and xxx used and blue and black colors tested using this tool <https://rgblind.com/color-blindness-simulator>)

The library ggigraph did not seem to include the fig.alt text. The following workaround was used:

``` r
library(htmltools)

browsable(
  tags$div(
    `aria-label` = "fig.alt text here ...",
    role = "img",
    interactive_graph
  )
)
```

This workaround puts the graph into a div container with text for screen readers.

## 3 bad chart redesign

All graphs were slightly reworked but the original graph 2 is still included as a bad example and for before/after comparisons.

### bad example

<img src="../figures/project-1-graph3-bad-example.png"/>

### reworked graph

<img src="../figures/project-1-graph4-non-interactive.png"/>

The graph before was a scatterplot with the purpose of showing a trend of average mpg from year 1984 to 2017. The graph afterwards is an interactive boxplot graph *(check out sander_project_01.html for an interactive version)*.

The main problem of the original graph was that the trend was visible in the trend line but not in the scatterplot data. The problem was that even though points were slightly opaque, to many points had the same value and stacked on each other hid how many points were at each point. One solution used in other graphs in this project would been to inccrease some jitter in the horizontal spacing of the points. However, for this graph I decided to redesign it as an interactive boxplot. A boxplot visualizes the distribution of a population while also making outliers easily visible. The interactive part of the graph gives some additional information to the population for each year such as the actual average, and what car types within that distribution made up the population.
