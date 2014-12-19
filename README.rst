A-team Bootcamp
===============
`View this document at ateam-bootcamp.readthedocs.org
<http://ateam-bootcamp.readthedocs.org>`_

A tutorial on some of the basic things you'd want to know when
contributing to `Automation & Tools`_ at Mozilla.

This document is based off of the excellent `webdev bootcamp`_ documentation.

Patches are always welcome! If you'd like to contribute, fork and make a pull
request.

.. _`Automation & Tools`: https://wiki.mozilla.org/Auto-tools
.. _`webdev bootcamp`: http://mozweb.readthedocs.org

Building locally
----------------
The instructions below assume you have Python and `pip`_ installed. It is also
strongly recommended that you create and activate a `virtualenv`_ first.

If you'd like to build the bootcamp locally:

.. code-block:: sh

   pip install -r requirements.txt
   make html

The resulting docs can be located under the ``_build/html`` directory.

You can also run ``make livehtml`` to launch a webserver on
http://127.0.0.1:8000 that auto-rebuild the documentation when any files are
changed.

.. _pip: https://pip.pypa.io/
.. _virtualenv: https://virtualenv.pypa.io/

Licensing
---------

Feel free to fork this repo or adapt its work for your own bootcamp. All work
is licensed under a `Creative Commons Attribution`_.

.. _`Creative Commons Attribution`: https://creativecommons.org/licenses/by/4.0/
