# Setup Instructions

```{tip}

The instruction below are for Authors, but you can modify this page to specify 
setup instructions for Readers in case if you are installing any special libraries or frameworks. 
```

### Pre-requisities

install nodejs  (https://nodejs.org/en/download)

`pip install mystmd`  <-- The enhanced version of Markdown 

`myst -v`  --> to confirm successful installation 
should see version number

--

### Install Jupyter Lab and MyST Extension for Jupyter Lab

`pip install jupyterlab`


Install the MyST extension for JupyterLab: <br/>
`pip install jupyterlab_myst`   <--  would enable MyST MD for jupyter cells 


Verify that the MyST extension is installed:
`jupyter labextension list`

You should see:
jupyterlab-myst v2.*.* enabled OK (python, jupyterlab_myst)

--

### Install Jupyter Book v2 (next)

`pip install "jupyter-book>=2.0.0a0"`   <-- installs jupyter book 

Make sure you install v2 of Jupter Book and not v1. 

Juputer Book will convert your Notebooks (.ipynb) and .MD files into a nice web-hosted book 