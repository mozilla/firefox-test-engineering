Firefox Test Engineering
========================
A tutorial on some of the basic things you'd want to know when
contributing to `Firefox Test Engineering`_ at Mozilla.

This can be read on the `Firefox Test Engineering Read the Docs <http://firefox-test-engineering.readthedocs.io/en/latest/>`_ website.

This document is based off of the excellent `Webdev Bootcamp`_ documentation.

Patches are always welcome! If you'd like to contribute, fork and make a pull
request.

.. _`Firefox Test Engineering`: https://wiki.mozilla.org/TestEngineering
.. _`Webdev Bootcamp`: https://mozweb.readthedocs.io/

Building locally
----------------
The instructions below assume you have Python and `pip`_ installed. It is also
strongly recommended that you create and activate a `virtualenv`_ first.

If you'd like to build locally:

.. code-block:: sh

   pip install -r requirements.txt
   make html

The resulting docs can be located under the ``_build/html`` directory.

You can also run ``make livehtml`` to launch a webserver on
http://127.0.0.1:8000 that auto-rebuilds the documentation when any files are
changed.

.. _pip: https://pip.pypa.io/
.. _virtualenv: https://virtualenv.pypa.io/

Licensing
---------

Feel free to fork this repo or adapt its work for your own needs. All work
is licensed under a `Creative Commons Attribution`_.

.. _`Creative Commons Attribution`: https://creativecommons.org/licenses/by/4.0/
