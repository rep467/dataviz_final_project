# Data Visualization

> Per Sander.

## Mini-Project 3

In this project, I explored the 2022 data from the FSU Florida Climate Center and the text of the lyrics of the top 100 songs from 2015. The purpose of this project was to explore different types of graphs and to perform a text analysis using bigrams.

The report can be found in sander_project_03.html or sander_project_03.md (The md file on github does not display interactive graphs correctly)

## 1 Interactive Chart

The following interactive barchart graph was created: *(check out sander_project_03.html for an interactive version)*

<img src="../figures/project-3-graph-7-2-non-interactive.png"/>

When hovering over the bars total occurrences and unique occurrences in songs are shown. Furthermore, the graph can be switched between showing the most common word, bigrams of length 2, or bigrams of length 3. Through these interactive graph, I noticed that the dataset is missing spaces in the song lyrics. (check out report for more info)

<img src="../figures/project-3-graph-7-2-non-interactive-showcase.png"/>

## 2 Accessibility

For accessibility fig.alt text were included for each graph, and colorblind safe colors and pallets were chosen.(various viridis color pallets used and other colors were tested using this tool <https://rgblind.com/color-blindness-simulator>)

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

For this project a bad chart was created on purpose.

### bad example

<img src="../figures/project-2-graph-1-bad-example.png"/>

### reworked graph

<img src="../figures/project-2-graph-1-reworked.png"/>


The bad graph is hard to read as the value for USA is very large while all other values are comparatively small. Furthermore, some aesthetics like labels and including title can be improved. 
The axis labels were improved by using Country names instead of a 3 letter country code and x and y was switched to have more space for the country names.
The scale was changed into a log arithmetic scale for readability. However, While this can visualize small values better it makes the overall scale less intuitive to read. 
To address this issue axis markers for specific participation numbers were added.