===========
Common Conventions
===========
The following are some hopefully-helpful pointers to common conventions we're using across *most* automation projects.

Their adoption aims to make automation easily repeatable, runnable, more reliable, and with clearer output.

Code Coverage
-------------
Blurb about code coverage (what/why/how?) -- particularly our current defacto, `Coveralls <https://coveralls.io>`_ -- goes here.

Dependencies/Requirements
-------------------------

pyup.io
~~~~~~~

Docker
------
We use Docker to help ensure consistent, portable builds, with dependency/environment control.

There are typically two files associated with our use of Docker:

#. Dockerfile
#. .dockerignore

For both of these files, see the official docs at https://docs.docker.com/engine/reference/builder

Linting
-------
PEP8 and `flake8 <http://flake8.pycqa.org>`_.

pipenv
------
Blurb about why and how we use `pipenv <https://docs.pipenv.org/>`_.

.gitignore
----------
