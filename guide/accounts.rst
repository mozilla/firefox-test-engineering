Accounts
========

We use a few websites/services/applications to manage our test-automation and infrastructure code, bugs, test cases, etc., and while it is possible to
get by without signing up for these sites, it's *strongly* recommended that
you create accounts on these websites.

GitHub
------

Many Firefox Test Engineering projects are hosted on GitHub_. GitHub provides hosting for our
source code, as well as tools we use for collaboration and code review. GitHub
is based on Git_, a distributed version control system that lets us track the
changes we make to our code.

Once you've `created a GitHub account <https://github.com/join>`_, you can check out the `GitHub help site`_
for guides on the basics of using Git and GitHub.

.. seealso::

   `Mozilla Services on GitHub <https://github.com/mozilla-services/>`_
      Mozilla Services' organization account on GitHub.
   `Mozilla on GitHub <https://github.com/mozilla/>`_
      Mozilla's organization account on GitHub.

.. _GitHub: https://github.com/
.. _Git: https://git-scm.com/
.. _GitHub help site: https://help.github.com/


Bugzilla
--------

Bugzilla_ is the issue-tracking system that the entire Mozilla Project uses.
Many of our projects use Bugzilla to keep track of any planned
changes to or bugs in our projects.

As a new contributor, Bugzilla is a useful tool for finding known issues that
you can help fix or finding planned work you want to take on. In order to
assign a bug to yourself or to post a comment on a bug, you'll need to create
a Bugzilla account. An account also allows you to "CC" yourself on bugs that
you are interested in, so that you receive emails when those bugs are changed.

After you've been using Bugzilla for a while as a community member,
it's worthwhile applying for expanded permissions. The editbugs
permission allows you to assign bugs to yourself and resolve them, for
example. See the `Bugzilla Permissions Page`_ for details. Note that
new employees get this permission automatically; there's no need to ask for it.

.. note:: It's highly recommended to add your IRC nickname to your real name
   within Bugzilla to make it easy for others to auto-complete your name.

   The standard format is to follow your real name with your IRC name,
   preceeded by a colon, surrounded by square brackets. For example:
   ``Cave Johnson [:withthelemons]``.

.. _Bugzilla: https://bugzilla.mozilla.org/
.. _`Bugzilla Permissions Page`: https://bugzilla.mozilla.org/page.cgi?id=get_permissions.html

Limited Access Accounts
=======================
Our team also uses a number of services which are accessible only with special accounts and/or permissions. If you're under an `NDA <https://wiki.mozilla.org/NDA>`_ you may ask your mentor or manager for access.

fx-test-pubkeys
---------------
Used to keep our public keys, which we use for access control/authentication in our AWS' EC2 environments/instances.  Please follow the instructions at https://github.com/mozilla-services/fx-test-pubkeys to generate and upload yours.

Amazon Web Services (AWS)
-------------------------
AWS is currently used for much of our server and infrastructure testing. In the future it will likely hold a lot more of our test automation.

You will very likely, at some point (sooner, rather than later) need a Mozilla-privileged AWS account.  Please follow these `instructions on Mana <https://mana.mozilla.org/wiki/display/SVCOPS/Requesting+A+Dev+IAM+account+from+Cloud+Operations>`_ to get one.

LastPass
--------
We use LastPass to securely share miscellaneous credentials (usernames/passwords/API keys).  Please follow the instructions  https://mana.mozilla.org/wiki/display/TestEngineering/LastPass to request and use an account with your Mozilla email address.

Jenkins
-------
Jenkins is used for running our test automation. It is in the process of being moved into AWS.

TestRail
--------
`TestRail <https://wiki.mozilla.org/TestEngineering/Testrail>`_ is being set up for use as a test case manager. In the future it will be more accessible and visible to community members.
