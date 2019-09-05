About
=====

Public source code repository of this scientific paper, titled:

    An automated workflow for writing and preparing LaTeX papers for submission
    in PLOS journals

Installation
============

This project doesn't require system wide installation, simply clone it to get
started::

    $ git clone https://github.com/petarmaric/paper-2019-automated-plos-workflow.git
    $ cd paper-2019-automated-plos-workflow
    $ pipenv install

Usage
=====

Show help::

    $ pipenv run make help
    Usage: make [TARGET]...

    Targets:
      help              Display this help message
      build             Build the paper
      export            Prepare the paper for journal submission
      clean-built       Remove the papers build directory
      clean-exported    Remove the papers export directory
      clean             Remove both the build and export directories
      view-built        View the papers built PDF file (runs 'build' if needed)
      view-exported     View the papers exported PDF file (runs 'export' if needed)
      view              View both the built and exported PDF files

Quick start:

#. write your paper, while keeping in mind you can edit **any** file freely:

   #. add/remove sections
   #. update ``Makefile`` to build your figures programmatically
   #. add more LaTeX packages to ``preamble.tex``, or change their options
   #. ...

#. build (and check) your paper often as you write::

    $ pipenv run make view-built

#. prepare your paper for journal submission::

    $ pipenv run make view-exported

#. submit files from the ``export`` directory to the journal

Using Docker
------------

If you do not wish to install a LaTeX distribution on your system you can use
the dockerized version of template4plos instead:

- show help::

    $ ./dockerized.sh help
    Usage: make [TARGET]...

    Targets:
      help              Display this help message
      build             Build the paper
      export            Prepare the paper for journal submission
      clean-built       Remove the papers build directory
      clean-exported    Remove the papers export directory
      clean             Remove both the build and export directories
      view-built        View the papers built PDF file (runs 'build' if needed)
      view-exported     View the papers exported PDF file (runs 'export' if needed)
      view              View both the built and exported PDF files

- build your paper::

    $ ./dockerized.sh build

- prepare your paper for journal submission::

    $ ./dockerized.sh export
