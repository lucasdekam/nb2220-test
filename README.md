# nb2220-test
Test version for publishing the open lecture notes that are being developed for the course NB2220 Statistical Physics at TU Delft. Published [here](https://nb2220-test.netlify.app/intro.html) using Netlify (to be removed) and [here](https://lucasdekam.github.io/nb2220-test/) using GitHub Actions and GitHub Pages.

## How the website is going to work
* Jupyter Book is a Python module that can build markdown and .ipynb files into
a website that looks like this (you can also include python scripts for
interactive plots, etc.)
* The markdown files are stored in the main branch
* The website is deployed in the gh-pages branch using GitHub Actions, and published using GitHub Pages. (The \_build folder is still there for publishing on Netlify, which I tried earlier. However, it is redundant for publishing using Actions and Pages.) 
