Software and Tools
==================

The software you'll need to download and install on your computer in order to
contribute varies between projects; please refer to the documentation for the
project you want to contribute to for details.

The following information is a generic description of software or tools that
you'll most likely need regardless of the project you work on.

Operating Systems: Windows, Linux, or OS X?
-------------------------------------------

Generally speaking, automation and test tools need to run on the
platforms that are being tested. Linux and Mac are often used as
development environments because the tooling is much more
comprehensive. If you are a Windows user, you may want to use a
program like `VirtualBox`_ to create a virtual machine running a
Linux-based operating system. The rest of this guide assumes you are
using OS X or a Linux-based operating system.

If you are running Mac OS X, most of the software mentioned here can be
installed using the `Homebrew`_ package manager.

.. _VirtualBox: https://www.virtualbox.org/
.. _Homebrew: http://brew.sh/

Git
---

Git_ is a distributed version control system. It tracks the history of changes
we make to our code, which allows us to see how the code has changed over time.
Git also makes it very easy for multiple people to work on the same code at the
same time and merge their changes together at the end.

If you are a contributor who is completely new to distributed version
control systems, you might enjoy stepping through some or all of this
`fun and easy tutorial <https://try.github.io/levels/1/challenges/1>`_.

.. seealso::

   `help.github.com <https://help.github.com/>`_
      A great guide to getting started with Git and GitHub, which hosts most of
      our Git repositories.

   `GitHub for Windows <https://windows.github.com/>`_
      A Windows program for interacting with GitHub as an alternative to using
      Git in a terminal. Useful if you are not used to using a terminal yet.

   `GitHub for Mac <https://mac.github.com/>`_
      A Mac OS X program for interacting with GitHub as an alternative to using
      Git in a terminal. Useful if you are not used to using a terminal yet.

.. _Git: https://git-scm.com/

Mercurial
---------

Mercurial_ is a version control system similar to Git. We use it to
track the source code to Firefox itself, as well as much of the
automated test infrastructure around it (mochitest, reftest, etc.).

.. seealso::

   `Mozilla's Guide to Mercurial <https://developer.mozilla.org/en-US/docs/Mercurial>`_
     The MDN page on Mercurial contains some useful links for getting
     started.

.. _Mercurial: https://www.mercurial-scm.org/


Pastebin
---------

Pastebin is a tool that can be used to capture snippits of log or error messages for collaborative debugging.

To "pastebin" something, `paste it here <https://pastebin.mozilla.org/>`_ and hand the link you're given after clicking "submit" to people on IRC.


Python
------

Python_ is a programming language that we use in many of our tools and
automation frameworks. Our bigger web-based tools are often implemented
using Django_, a Python-based framework for making websites.

Most of our Python-based projects are developed to run under Python 2.

.. seealso::

   `The Hitchhiker's Guide to Python <http://docs.python-guide.org/en/latest/>`_
      A useful guide for beginner and expert Python developers. If you need to
      install Python on your computer, this guide will help!

.. _Python: https://www.python.org/
.. _Django: https://www.djangoproject.com/


