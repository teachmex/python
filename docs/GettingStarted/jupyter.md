# Installing Jupyter Notebook

By far the easiest way to install Jupyter is with Anaconda. Jupyter notebooks automatically come with the distribution. You'll be able to use notebooks from the default environment.

To install Jupyter notebooks in a conda environment, use 
```
conda install jupyter notebook
```

Jupyter notebooks are also available through pip with 
```
pip install jupyter notebook
```

Markdown Cheatsheet : https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet


Convert a notebook to an HTML file, in your terminal use
```
jupyter nbconvert --to html notebook.ipynb

```
Convert: https://nbconvert.readthedocs.io/en/latest/usage.html

To create the slideshow from the notebook file, you'll need to use nbconvert:
```
    jupyter nbconvert notebook.ipynb --to slides
    
```
This just converts the notebook to the necessary files for the slideshow, but you need to serve it with an HTTP server to actually see the presentation.
```
To convert it and immediately see it, use
```
jupyter nbconvert notebook.ipynb --to slides --post serve
This will open up the slideshow in your browser so you can present it.

panda presentation: [presentation](http://nbviewer.jupyter.org/format/slides/github/jorisvandenbossche/2015-PyDataParis/blob/master/pandas_introduction.ipynb#/)








