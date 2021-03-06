PyQt5 Application Boilerplate
=============================

This repository contains a boilerplate for PyQt5 based applications.

.. image:: https://user-images.githubusercontent.com/25011557/36483230-da4620c6-1715-11e8-9ee5-c10053641440.png
    :alt: PyQt5 Application Boilerplate

Features
--------

- Dependency management using pipenv_
- Use the *standard* ``setup.py`` to build resources, docs, etc.
- Manage resources and UI forms using a Qt Creator project
- Generate a *compiled* application for Windows, Linux and macOS using
  PyInstaller_
- Multilanguage support
- Document using Sphinx_
- Flake8 linting

Getting started
---------------

First of all make sure you have pipenv_ installed and then initialize a
working development environment like this::

    pipenv install --dev

Once all dependencies are installed, you should enter the environment shell like
this::

    pipenv shell

Autogenerated files such as translation binaries or compiled forms are required
but not pushed to the repository, so the first time you will need to generate
them as described in the coming section. Once done, you can run the application
like this::

    app

Resources and translations
--------------------------

In order to ease the development process, the Qt Creator project ``app.pro`` is
provided. You can open it to edit the UI files or to manage resources. The
Python source files are also present on the project so that the translation tool
can extract strings from sources. Qt Linguist can be used to translate.

You can build the resources and UI files like this::

    python setup.py build_ui

Translations can be edited using Qt Linguist, part of the Qt SDK. In order to
build the translations, you will need to have the Qt SDK tools to your ``PATH``,
in particular the ``lrelease`` command. Translations can be built like this::

    python setup.py build_tr

Note that these steps are also required prior to installation and/or
distribution.

Compiled application
--------------------

You can generate a *compiled* application so that end-users do not need to
install anything. You can tweak some settings on the ``app.spec`` file. It can
be generated like this::

    python setup.py bdist_app

Documentation
-------------

Sphinx_ is used for documentation purposes. You can tweak its configuration in
``docs/conf.py`` and the documentation can be built like this::

    python setup.py build_docs

Linting
-------

Flake8 is a great tool to check for style issues, unused imports and similar
stuff. You can tweak ``.flake8`` to ignore certain types of errors, increase the
maximum line length, etc. pipenv_ integrates Flake8, you can run it like
this::

    pipenv check --style app


.. _pipenv: https://docs.pipenv.org/
.. _PyInstaller: http://www.pyinstaller.org/
.. _Sphinx: http://www.sphinx-doc.org/
