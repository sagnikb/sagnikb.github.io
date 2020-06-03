---
layout: single
title:  "Real time updation in gnuplot"
date:   2017-03-15 00:23:20 +0530
excerpt: Plotting data generated in real time using gnuplot
tags: gnu-plot data-visualisation
categories: academic
comments: true
---
Last summer, two of my friends and I did a project under [Programming Club, IITK](http://pclub.in). The topic of the project was N-Body Simulation, and we had to write parallelised code to simulate the motion of a specified number of bodies (~30) with specified 'masses' under a 'gravitational force' acting between each of them. For this purpose we had to have something that could plot the data obtained in real time.  We gave a lot of importance to this real time updation because otherwise we were generating text files in the gigabyte range which then took ages to plot. We tried various options, including Matlab, the matplotlib and scipy libraries in Python, but didn't get the speed required for our work in any of them. Finally we stumbled upon a solution to this problem, in which we used gnuplot with a pause/reread instruction, and that solved our problem perfectly.The required commands in gnuplot are 

```gnuplot
pause
reread
```

The specific code is shown below

```gnuplot
set term x11 size 1500, 1200
set xrange [-500:500]
set yrange [-500:500]
set zrange [-5:5]
splot "List.txt" with points ps 1 pt 7 title "N-Body Simulation"
pause 1
reread
```

The first line sets the output termnal type and size, and the next three lines sets the x, y and z ranges for the plot. The next line takes data about seven bodies from the file "List.txt" and plots them. The script then pauses for a second and after that the contents of the text file are read again for plotiing. Over time, we were able to see full simulation of the generated data, almost in real time. Hope this helps anyone stuck on a similar problem.

The whole code for the project is available at [Simulati-ON](http://sagnikb.github.io/Simulati-ON). You are welcome to take a look!
