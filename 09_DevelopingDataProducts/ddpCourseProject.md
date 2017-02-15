Developing Data Products - Course Project - Shiny App
========================================================
author: Brian Monedero Linn
date: 02/15/2017
autosize: true
transition: linear
css: custom.css

Shiny Application
========================================================
transition: rotate
The application developed for this project is called 'Diamond Price Analysis'.   
The analysis includes:
- Documentation describing the function and use of the tool
- Exploratory Analysis Visualizations
- Price Predictions

Exploratory Analysis
========================================================
transition:fade
The exploratory analysis allows the user to visualize the relationships between the price of a diamond and the various predictor data elements.

```r
library(ggplot2)
data(diamonds)
smallDiamonds <- diamonds[sample(nrow(diamonds), (.1 * nrow(diamonds)), replace = FALSE, prob = NULL), ]
smallDiamonds$size <- smallDiamonds$x * smallDiamonds$y * smallDiamonds$z
gCut <- ggplot(smallDiamonds, aes(x = cut, y = (price/carat))) + geom_point(aes(size = carat, colour = factor(clarity))) + scale_colour_discrete(name  = "Clarity") +
        scale_size_continuous(name  = "Carat") + xlab("Cut") + ylab("Price per Carat") 
gCut
```

![plot of chunk samplePlot](ddpCourseProject-figure/samplePlot-1.png)

Price Predictions
========================================================
transition: zoom
The price predictions tool allows the user to manipulate a sample diamond's variable values. The application will display a predicted price for various models of the data based on the parameters input by the user.


Accessing the Application
========================================================
transition: zoom
The application can be found at the following:
[Developing Data Products - Course Project](https://blinn.shinyapps.io/ddpCourseProjectApp/)