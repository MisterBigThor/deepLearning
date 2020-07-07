## Matplotlib.pyplot

[TOC]

### Plot x versus y - Simple

````mermaid
graph LR;

A(MATPLOTLIB) ==> b{"plt.plot(x, y, 'style')"}
A ==> Z
Z["plt.subplot(nrows, ncols, index)"] ==> b
b ==> c["plt.xlabel('X axis title')"] ==>f["fig = plt.show()"]
b ==> d["plt.ylabel('X axis title')"] ==>f
b ==> e["plt.title('title')"] ==> f

````



### Subplots & Object Oriented Model

````mermaid
graph LR;
A["fig = plt.figure()"] ==> B("ax[n]= fig.add_axes(...)") ==> Z
C["fig, axes = plt.subplots()"] ==> Z{"ax[n].plot(..)"}
C ==> H
A ==> H("fig.savefig('name.png')")
````



The ``plt.figure(figsize=(x,y), dpi=n)`` object represents the viewport, we can add axes with:

* ``ax = fig.add_axes([left, bottom, width, height])|[0, 1]``.

* ``fig, axes = plt.subplots(nrows=1, ncols=1)``. Return nrows*ncols axes in a array.
* The figure object can be called to represent the plot. The ``plt.tight_layout()`` adjust the padding, also the figure can use the figsize and the dpi parameters to adjust the plot size.
* The ``plt.subplot(...)`` activates each subplot with the index.

* This figure can be saved with ``fig.savefig('name.png')``.

### Legend

Activate the legend with ``ax.legend(loc=0)``  and use options for location, colors, etc...

### Styles



## All together

````mermaid
graph LR;

subgraph Basics
A(MATPLOTLIB) ==> b{"plt.plot(x, y, 'style')"}
A ==> Z
Z["plt.subplot(nrows, ncols, index)"] ==> b
b ==> c["plt.xlabel('X axis title')"] ==>f["fig = plt.show()"]
b ==> d["plt.ylabel('X axis title')"] ==>f
b ==> e["plt.title('title')"] ==> f
end;

subgraph subplots
H["fig = plt.figure()"] ==> B("fig.add_axes(...)") ==> b
I["fig, axes = plt.subplots()"] ==> b 
H ==> t("fig.savefig('name.png')")
end;
````



