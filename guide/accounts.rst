Accounts
========

We use a few websites to manage our code and bugs, and while it is possible to
get by without signing up for these sites, it's *strongly* recommended that
you create accounts on these websites.

Github
------

Many A-team projects are hosted on Github_. Github provides hosting for our
source code, as well as tools we use for collaboration and code review. Github
is based on git_, a distributed version control system that lets us track the
changes we make to our code.

Once you've created a Github account, you can check out the `Github help site`_
for guides on the basics of using git and Github.

.. seealso::

   `Mozilla on Github <https://github.com/mozilla/>`_
      Mozilla's organization account on Github.

.. _Github: https://github.com/
.. _git: http://git-scm.com/
.. _Github help site: https://help.github.com/


Mercurial and Mozilla-Central
-----------------------------

Much of our other build & test code lives inside `mozilla-central`_,
a `mercurial`_ repository which also contains the source code to Firefox.

To be able to commit to this repository directly, you will need to
sign a contributor's and be vouched for by a module owner. You
probably don't need to worry about this initially: just clone the
repository manually, test your changes locally, and let other people
push your patches for you.

If you find that you're working on a lot of stuff within this
code base, you'll want to apply for `committer access`_ so you can push
code to try_ or an integration branch like mozilla-inbound.

.. _mozilla-central: https://developer.mozilla.org/en-US/docs/mozilla-central
.. _mercurial: http://mercurial.selenic.com
.. _`committer access`: https://www.mozilla.org/en-US/about/governance/policies/commit/
.. _try: https://wiki.mozilla.org/Build:TryServer

Bugzilla
--------

Bugzilla_ is the issue-tracking system that the entire Mozilla Project uses.
The vast majority of A-team projects use Bugzilla to keep track of any planned
changes or bugs with our websites.

As a new contributor, Bugzilla is a useful tool for finding known issues that
you can help fix or finding planned work you want to take on. In order to
assign a bug to yourself or to post a comment on a bug, you'll need to create
a Bugzilla account. An account also allows you to "CC" yourself on bugs that
you are interested in, so that you receive emails when those bugs are changed.

After you've been using Bugzilla for a while as a community member,
it's worthwhile applying for expanded permissions. The editbugs
permission allows you to assign bugs to yourself and resolve them, for
example. See the `Bugzilla Permissions Page`_ for details. Note that
new employees get this permission automatically, no need to ask for it.

.. note:: It's highly recommended to add your IRC nickname to your real name
   within Bugzilla to make it easy for others to auto-complete your name.

   The standard format is to follow your real name with your IRC name,
   preceeded by a colon, surrounded by square brackets. For example:
   ``Cave Johnson [:withthelemons]``.

.. _Bugzilla: https://bugzilla.mozilla.org/
.. _`Bugzilla Permissions Page`: https://bugzilla.mozilla.org/page.cgi?id=get_permissions.html
