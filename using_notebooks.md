---
jupyter:
  jupytext:
    notebook_metadata_filter: rise
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.2'
      jupytext_version: 1.4.2
  kernelspec:
    display_name: Python 3
    language: python
    name: python3
  rise:
    enable_chalkboard: true
    scroll: true
---

<!-- #region slideshow={"slide_type": "slide"} -->
## The Jupyter Notebook Environment

The teaching and learning materials used to support the activities are provided as Jupyter notebooks. 
<!-- #endregion -->

<!-- #region slideshow={"slide_type": "skip"} -->
Jupyter notebooks have been used deliver practical activities in *TM351 Data Management and Analysis*, the OU produced FutureLearn/OpenLearn unit *Learn to Code for Data Analysis*, materials which are also used in *S818 Space Science*, and to support a brief, optional set of activities in TM112.

They will also be used in several courses currently in production including the *TM129 Technologies in Practice* robotics unit, *M269 Algorithms*, *TM358 Machine Learning* and *M348 Linear Models*, although not necessarily delivered using the *Open Computing Lab* approach.
<!-- #endregion -->

<!-- #region slideshow={"slide_type": "slide"} -->
Originally developed to support computational research activities, Jupyter notebooks provide a cell based web-based read-write-execute document editor that blends rich text, executable code and code outputs.
<!-- #endregion -->

<!-- #region slideshow={"slide_type": "fragment"} -->
Within text areas, code can by highlighted in a language sensitive way:
<!-- #endregion -->

<!-- #region -->
```python
def sayHello():
    print('Hello World')
```
<!-- #endregion -->

<!-- #region slideshow={"slide_type": "slide"} -->
Code is executed in a "kernel" shell environment running on a backend server.
<!-- #endregion -->

<!-- #region slideshow={"slide_type": "skip"} -->
Kernels for a [wide variety of programming languages](https://github.com/jupyter/jupyter/wiki/Jupyter-kernels) are available; in TM129, we will be using a full Python kernel, as well as a simple in-browser Skulpt Python environment that runs code inside a simple in-browser 2D robot simulator.
<!-- #endregion -->

<!-- #region slideshow={"slide_type": "slide"} -->
When a code cell is run, outputs can be printed or displayed, and any value returned by the last object in the cell object will be displayed as cell output.
<!-- #endregion -->

```python slideshow={"slide_type": "fragment"}
def sayHello():
    print('Hello World')
    return "done..."
    
sayHello()
```

<!-- #region slideshow={"slide_type": "skip"} -->
## What Next?

If you are not familiar with Jupyter notebooks, please spend some time familiarising yourself with them.

We believe they provide a powerful tool to support teaching and learning and it's still early days for us in finding out how to make most effective use of them.

If you have any ideas anout how we can imporve our current use of the notebooks, or make more effective use of them, please let us know.
<!-- #endregion -->

