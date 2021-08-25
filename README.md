Open Education Statistical Physics for Nanobiology
===================================================

The aim of this project is to create and publish lecture notes for NB2220
Statistical Physics for Nanobiology using [Jupyter Book](https://jupyterbook.org/intro.html). This README serves
as the documentation for teachers or TA's working on this book.

## Writing the book
The book is written in an extended version of the Markdown language used by Jupyter Book.
Documentation for this language is available [here](https://jupyterbook.org/content/myst.html).
You can use LaTeX equations and reference them, create figures, etc.
The Markdown source files are located in the `content` folder (apart from the
homepage, `index.md`). The way these files
appear as chapters in the book is specified in the `_toc.yml` file. If you want
to add chapters or change the structure of the book, you should read the
documentation [here](https://jupyterbook.org/customize/toc.html).

Ordered lists in Markdown are a bit tricky to work with. There's a CSS file in
the `_static` folder that makes all ordered lists look like a), b), c), etc.
This means that it is currently not possible to (simply) make numbered lists with numbers.

The `_config.yml` file specifies things like the author, the logo and the
title of the book, and the way things should be executed or compiled. Also, the
line `hypothesis: true` enables [Hypothesis](https://jupyterbook.org/interactive/comments/hypothesis.html),
which is a way for students and
teachers to comment on pieces of text (when the book is published).
You simply need to create an account and then you can view and add comments.

The Python packages that you need to work with the book are listed in
`requirements.txt`.
Currently, there are some static plots written in `matplotlib` and some
interactive plots written in `plotly`. If you want to edit these, I would
highly recommend opening the Markdown files as Jupyter Notebooks, or copying
the code to a Jupyter Notebook. Editing code in the Markdown files themselves
is rather cumbersome. You can choose to show the code, hide the code, or
show the code in a drop-down box by specifying *tags* in the code cell.

## Building the book
To build the book, clone this repository and run `jupyter-book build .` in the repository root from a
shell or command prompt (if it doesn't work, check if your computer can find
`jupyter-book`, i.e. check if it is added to PATH). This
creates a new folder, `_build`, in which the HTML files are located; you can view
these in your browser. Currently, the _build folder is ignored by Git (specified
in `.gitignore`).

**IMPORTANT:** Building the book on Windows currently only works with Python 3.7 (due to
the execution of code in Problem set 6). If no code is executed, newer versions
of python work as well. You might want to use a [virtualenv](https://virtualenv.pypa.io/en/latest/user_guide.html)
to use a Python 3.7 installation when you work on the book.

## Publishing the book
...

## To-do list
* Publish the website
* Write documentation on publishing
* Add learning goals to each chapter in an admonition box?
* Publish documentation on the OLMO Teams and Google Drive, so it is accessible for people in
other projects as well

<!-- ## Feedback
[Document with summary of all course feedback for 2020/2021](https://docs.google.com/document/d/1PffzMkjXvT5hYC_5ylx8LJYlzYyWNNwSCUNJjPjUUfk/edit?usp=sharing) -->
