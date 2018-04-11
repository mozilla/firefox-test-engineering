==================
Common Conventions
==================
The following are some hopefully-helpful pointers to common conventions we're using across *most* automation projects.  Their adoption aims to make automation easily repeatable, runnable, more reliable, and with clearer output.  This list is neither exhaustive nor authoritative, but we strive to keep it as up-to-date and relevant as possible. 

Code Coverage
-------------
**Purpose:** Particularly relevant for our Python packages (which are used themselves in other testing projects and development repos), quite a few of our projects have implemented `Coveralls <https://coveralls.io>`_ code-coverage/analysis tool.

For a real-world example of code removal that Coveralls caught, see https://github.com/mozilla/FoxPuppet/pull/162#issuecomment-373110700

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
#. Install directly from the Pipfile `(Example) <https://github.com/mozilla/stubattribution-tests/blob/730551c564833ce6488fb181f7fb08405928124e/Dockerfile#L5>`_
#. Ignore generating and using the Pipfile.lock `(Example) <https://github.com/Kinto/kinto-integration-tests/blob/67239fe202a94fd9dd6aec664497f8c8343c7e46/Dockerfile#L6>`_

tox
~~~
**Purpose:** We use `tox <https://tox.readthedocs.io>`_ to run tests using multiple Python versions, as it automagically takes care of their respective virtual environments.

Docker
------
**Purpose:** We use `Docker <https://www.docker.com>`_ to help ensure consistent, portable builds, with dependency/environment control.

In most cases, we build our Docker image directly from its **master** branch in GitHub, in any one (or combination) of the following: Travis CI, Circle CI, and Jenkins.

Typically, we use two (2) main files, for Docker:

#. Dockerfile
#. .dockerignore

For both of these files, see the official docs at https://docs.docker.com/engine/reference/builder

Jenkins/Jenkinsfile
-------
We prefer tests running in Jenkins to use a Jenkinsfile (and Docker, as much as possible).

Linting
-------
**Purpose:** `PEP8 <https://www.python.org/dev/peps/pep-0008/>`_ and `flake8 <http://flake8.pycqa.org>`_.  Other considerations for specific linting are:

#. `flake8-isort <https://pypi.python.org/pypi/flake8-isort>`_
#. `flake8-docstrings <https://pypi.python.org/pypi/flake8-docstrings>`_
#. `pylint <https://www.pylint.org/>`_

Travis CI
---------
**Purpose:** We use `Travis CI <https://www.travis-ci.org/>`_ for linting pull requests/commits.
