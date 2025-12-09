Getting Started
===============

This guide will help you get the StudyFlow project up and running on your local machine.

Prerequisites
-------------

For the Jekyll Website:

* **Ruby** 2.7 or higher
* **Bundler** (for managing Ruby gems)
* **Git**

For Future Application Development:

* **Node.js** 16 or higher
* **npm** (comes with Node.js)

Installation
------------

**1. Clone the repository**::

    git clone https://github.com/luisjarquec/studyflow-app.git
    cd studyflow-app

Running the Jekyll Website
---------------------------

The ``website/`` directory contains the Jekyll-based marketing site.

**1. Navigate to the website directory**::

    cd website

**2. Install Jekyll and dependencies**::

    gem install jekyll bundler
    bundle install

**3. Run the development server**::

    bundle exec jekyll serve

**4. Access the website**:

Open your browser and navigate to ``http://localhost:4000``

Building Documentation
----------------------

To build the Sphinx documentation locally:

**On Windows**::

    cd docs
    .\make html

**On Unix/Mac**::

    cd docs
    make html

Then open ``docs/_build/html/index.html`` in your browser to view the documentation.

Future Application Setup
-------------------------

For contributing to the main StudyFlow application (when available):

**1. Install dependencies**::

    npm install

**2. Start the development server**::

    npm run dev

**3. Access the application**:

Open your browser and navigate to ``http://localhost:3000``

Next Steps
----------

* Read the :doc:`usage` guide to learn how to use StudyFlow
* Check out the :doc:`contributing` guide to start contributing
* Join our community on `Discord <https://discord.gg/v2ctzYdp>`_ or `GitHub Discussions <https://github.com/luisjarquec/studyflow-app/discussions>`_
