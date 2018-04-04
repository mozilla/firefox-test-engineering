==================
Common Conventions
==================
The following are some hopefully-helpful pointers to common conventions we're using across *most* automation projects.  Their adoption aims to make automation easily repeatable, runnable, more reliable, and with clearer output.  This list is neither exhaustive nor authoritative, but we strive to keep it as up-to-date and relevant as possible. 

Code Coverage
-------------
**Purpose:** Blurb about code coverage (what/why/how?) -- particularly our current defacto, `Coveralls <https://coveralls.io>`_ -- goes here.

Dependencies + Virtual Environments
-----------------------------------

pyup
~~~~~~~
**Purpose:** `pyup.io <https://pyup.io>`_ helps us manage updating our dependencies and requirements.

There are a few scenarios for its use:

* Test suite lives in a separate directory within project repo
 - `Example <https://github.com/mozilla-services/socorro/blob/3232f5e420fd7e5b80fa456c8f4c583b58ef1fbb/.pyup.yml>`_ from Socorro
 - `Example <https://github.com/mozilla-services/go-bouncer/blob/86e9b428eee25e1d708935397da884f99f9be051/.pyup.yml>`_ from Bouncer
* Self-contained test suite
 - `Example <https://github.com/mozilla/mozillians-tests/blob/44f8d87560576549e801493dfb4069723d2d1506/.pyup.yml>`_ from Mozillians

pipenv
~~~~~~
**Purpose:** We use `pipenv <https://docs.pipenv.org/>`_ for managing virtual environments and installing dependencies.

Typically, we:

#. Pin pipenv with pipenv.txt `(Example) <https://github.com/mozilla/stubattribution-tests/blob/730551c564833ce6488fb181f7fb08405928124e/pipenv.txt>`_
#. Install directly from the Pipfile
#. Ignore generating and using the Pipfile.lock

tox
~~~
**Purpose:** We use `tox <https://tox.readthedocs.io>`_ to run tests using multiple Python versions.

Docker
------
**Purpose:** We use `Docker <https://www.docker.com>`_ to help ensure consistent, portable builds, with dependency/environment control.

In most cases, we build our Docker image directly from its **master** branch in GitHub, in any one (or combination) of the following: Travis CI, Circle CI, and Jenkins.

Typically, we use two (2) main files, for Docker:

#. Dockerfile
#. .dockerignore

Examples:

#. Example one
#. Example two

For both of these files, see the official docs at https://docs.docker.com/engine/reference/builder

Jenkins
-------

Linting
-------
**Purpose:** 

`PEP8 <https://www.python.org/dev/peps/pep-0008/>`_ and `flake8 <http://flake8.pycqa.org>`_.  Other considerations for specific linting are:

#. `flake8-isort <https://pypi.python.org/pypi/flake8-isort>`_
#. `flake8-docstrings <https://pypi.python.org/pypi/flake8-docstrings>`_
#. `pylint <https://www.pylint.org/>`_

Travis CI
---------
**Purpose:**

We use `Travis CI <https://www.travis-ci.org/>`_ for linting pull requests/commits.
