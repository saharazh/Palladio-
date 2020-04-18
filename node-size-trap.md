---
layout: default
title: The Node Size Caveat
nav_order: 4
---


## The trap of node size

The first thing to notice here on this graph is the nodes’ size. Vancouver and Victoria loom to be the most prominent destinations. Hmm.. let’s pause for a second here, do you think that’s because Vancouver and Victoria are connected to the largest number of villages, as the graph seemingly suggests? In other words, do you think the node size corresponds only to how many lines it connects to? To find the answer, let’s see how we can simplify our data. So below is an extremely simplified spreadsheet with only 4 rows of hypothetical records. Note that each row represents an immigrant. In the original dataset, there are many other variables about the immigrants' demographic information such as age, arrival year, and height, but for the sake of clarify only the two variables-the origin (village code) and destination are retained. <br /> 
![](http://blogs.ubc.ca/szhang/files/2018/06/屏幕快照-2018-06-21-上午11.00.47.png) <br /> 

After feeding it to Palladio (put village code as Source, and destination as Target), here is the visualization Palladio spit out: <br /> 
![](http://blogs.ubc.ca/szhang/files/2018/06/屏幕快照-2018-06-21-上午10.42.56-300x206.png) <br /> 


Now let's put a spotlight on Destination 3: it is only connected to one village (237), then how come its size is larger than that of Destination 1 and 2? Well, it turns out, a node size is related to how many lines it connects to, but this is not the whole picture. In fact, a node size is also tied to another factor: how many immigrants a village sent. We can write an equation like this: <br /> 
![](http://blogs.ubc.ca/szhang/files/2018/06/屏幕快照-2018-06-21-下午12.06.33.png) 


Let’s first take a destination node as an example to see how we can apply the equation: n= how many villages the destination is connected to (how many lines a destination is connected to) Ai= the number of immigrants each village sent So what this equation computes is the sum of the immigrants that each village sent which is connected to this destination. Now it’s clear that a node size equals the total number of immigrants that the corresponding destination received, or if we speak in the statistical language, the node size corresponds to the **frequency** of this destination! I find it fascinating to build a mental linkage between the network visualization and the statistics based off on the same data. 

To this point, if you have used Gephi or another network analysis tool, you may find it ridiculous to go through all the trouble of playing with dumb numbers just to find the meaning of the node size- it may have been clear to you all along. For a beginner to network analysis however, this may not be true. I’ll admit that I jumped into using Palladio without knowing much about network analysis theories. And later I realized that unlike mapping a point that comes with coordinates, you can choose to visualize a node by **any attribute**. And usually in network analysis, the weighted node size will default to represent the number of entities of the attribute.  In other words, while a point on a map and a node in a network appear to be the same (why, they are all just dots!), they are in fact rather different in terms of what a point represents.
 
To illustrate this point, let’s look at these two graphs below. 




