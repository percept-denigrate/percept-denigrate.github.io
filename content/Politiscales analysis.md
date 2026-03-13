---
tags:
  - project
---

I downloaded over 300 screenshots of Politiscales results. They were taken from X and public Discord servers. I manually transcribed the values to a CSV file. I thought about automating it with some image recognition model, but the images have different formats, and some values aren't shown directly and have to be deduced, so I figured it would be faster to do it manually.

I then ran a [[PCA]].

The correlation heatmap shows a strong clustering of all political axes.

![[politiscales_correlation.png]]

Most of the variance is explained by PC1, which represents the left-right axis.

![[politiscales_variance.png]]

Projecting all data points on a 2D plot along PC1 and PC2 yields this. Note that the left-right axis is inverted, the leftmost points are more right-wing and vice versa.

![[politiscales_scatter_plot.png]]
