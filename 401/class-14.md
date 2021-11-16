# Matplotlib Tutorial

- matplotlib is python package used in 2D-graphics. It is a fast way to visualize data and it provides high quality output in many formats.
#### IPython
- IPython is an interactive Python shell that has many features including named inputs and outputs, access to shell commands, improved debugging and much more.
#### pyplot
- pyplot is an interface to the matplotlib object-oriented plotting library.There are  majority of plotting commands in pyplot.
  

### Simple plot 
```python 
import numpy as np
%matplotlib inline
import matplotlib.pyplot as plt

X = np.linspace(-np.pi, np.pi, 256, endpoint=True)
C,S = np.cos(X), np.sin(X)

plt.plot(X,C)
plt.plot(X,S)

plt.show()
```
![](https://github.com/rougier/matplotlib-tutorial/raw/master/figures/exercice_1.png)

* Changing colors and line widths 

```python
plt.figure(figsize=(10,6), dpi=80)
plt.plot(X, C, color="blue", linewidth=2.5, linestyle="-")
plt.plot(X, S, color="red",  linewidth=2.5, linestyle="-")
```

![Changing colors and line widths](https://github.com/rougier/matplotlib-tutorial/raw/master/figures/exercice_3.png) 

* Setting limits 
- you can increase the limit of x or y axies to see the data in clearer way.
```python
plt.xlim(X.min()*1.1, X.max()*1.1)
plt.ylim(C.min()*1.1, C.max()*1.1)
```

![Setting limits](https://raw.githubusercontent.com/rougier/matplotlib-tutorial/master/figures/exercice_4.png) 

* Setting ticks

- as we do this tutorial for sin and cos we need show the interesting values (+/-π,+/-π/2) for sine and cosine. We'll change ticks such that they show only these values.
  
```python
plt.xticks( [-np.pi, -np.pi/2, 0, np.pi/2, np.pi])
plt.yticks([-1, 0, +1]) 
```

![Setting ticks](https://raw.githubusercontent.com/rougier/matplotlib-tutorial/master/figures/exercice_5.png) 

* Setting tick labels 
- we can enhance the ticks to represent the data in better way so the user can figure out what he can see at some point.
  
```python
plt.xticks([-np.pi, -np.pi/2, 0, np.pi/2, np.pi],
       [r'$-\pi$', r'$-\pi/2$', r'$0$', r'$+\pi/2$', r'$+\pi$'])

plt.yticks([-1, 0, +1],
       [r'$-1$', r'$0$', r'$+1$'])
```

![Setting tick labels ](https://raw.githubusercontent.com/rougier/matplotlib-tutorial/master/figures/exercice_6.png) 

* Moving spines
* spines are the lines which form data area. we can change them by setting top and right color to non and move left and bottom to be at 0 coordinate.
```python
ax = plt.gca()
ax.spines['right'].set_color('none')
ax.spines['top'].set_color('none')
ax.xaxis.set_ticks_position('bottom')
ax.spines['bottom'].set_position(('data',0))
ax.yaxis.set_ticks_position('left')
ax.spines['left'].set_position(('data',0))
```

![Moving spines](https://raw.githubusercontent.com/rougier/matplotlib-tutorial/master/figures/exercice_7.png) 

* Adding a legend

- we can add legened on the top left corner of the graph.
```python 
plt.plot(X, C, color="blue", linewidth=2.5, linestyle="-", label="cosine")
plt.plot(X, S, color="red",  linewidth=2.5, linestyle="-", label="sine")

plt.legend(loc='upper left', frameon=False)
```

![](https://github.com/rougier/matplotlib-tutorial/raw/master/figures/exercice_8.png)

---

* Devil is in the details 
* To show the tick lables in a clean way we can adjust their properities.
 
 ```python
 for label in ax.get_xticklabels() + ax.get_yticklabels():
    label.set_fontsize(16)
    label.set_bbox(dict(facecolor='white', edgecolor='None', alpha=0.65 ))
 ```

![Devil is in the details](https://raw.githubusercontent.com/rougier/matplotlib-tutorial/master/figures/exercice_10.png)

### Figures, Subplots, Axes and Ticks 

> Figures 

**A figure is the windows in the GUI that has "Figure #" as title. Figures are numbered starting from 1 as opposed to the normal Python way starting from 0. This is clearly MATLAB-style.** 

> Subplots

**With subplot you can arrange plots in a regular grid. You need to specify the number of rows and columns and the number of the plot.**

> Axes 

**Axes are very similar to subplots but allow placement of plots at any location in the figure. So if we want to put a smaller plot inside a bigger one we do so with axes.** 

> Ticks 

**Well formatted ticks are an important part of publishing-ready figures. Matplotlib provides a totally configurable system for ticks. There are tick locators to specify where ticks should appear and tick formatters to give ticks the appearance you want. Major and minor ticks can be located and formatted independently from each other. By default minor ticks are not shown**

### Animation 

***The most easy way to make an animation in matplotlib is to declare a FuncAnimation object that specifies to matplotlib what is the figure to update, what is the update function and what is the delay between frames.***

### References
[Matplotlib Tutorial](https://github.com/rougier/matplotlib-tutorial)