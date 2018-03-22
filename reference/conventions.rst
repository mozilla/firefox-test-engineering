===========
Common Conventions
===========
The following are some hopefully-helpful pointers to common conventions we're using across *most* automation projects.

Their adoption aims to make automation easily repeatable, runnable, more reliable, and with clearer output.

Code Coverage
-------------
**Purpose:** Blurb about code coverage (what/why/how?) -- particularly our current defacto, `Coveralls <https://coveralls.io>`_ -- goes here.

Dependencies/Requirements
-------------------------

pyup.io
~~~~~~~
**Purpose:**

pipenv
~~~~~~
**Purpose:** Blurb about why and how we use `pipenv <https://docs.pipenv.org/>`_.

Docker
------
**Purpose:** We use `Docker <https://www.docker.com>`_ to help ensure consistent, portable builds, with dependency/environment control.

We use typically two (2) main files, for Docker:

#. Dockerfile
#. .dockerignore

For both of these files, see the official docs at https://docs.docker.com/engine/reference/builder

Linting
-------
**Purpose:** `PEP8 <https://www.python.org/dev/peps/pep-0008/>`_ and `flake8 <http://flake8.pycqa.org>`_.

.gitignore
----------
