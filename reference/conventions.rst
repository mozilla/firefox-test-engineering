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

Examples:

#. Example one
#. Example two

pipenv
~~~~~~
**Purpose:** We use `pipenv <https://docs.pipenv.org/>`_ 

Typically, we:

#. Pin pipenv
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
