Git and GitHub
==============

The sections below describe some Firefox Test Engineering best practices for
using Git and GitHub. For more general information on Git here is a link to
`Good Resources`_ for Learning Git and GitHub.

.. _Good Resources: https://help.github.com/articles/good-resources-for-learning-git-and-github/

Issues
------
You can find an issue to work on by going to the
`Firefox Test Engineering Dashboard`_. Any unclaimed Issue is available to you
to work on. You can find out more about our process in the :doc:`../guide/index`.

.. _Firefox Test Engineering Dashboard: https://mozilla.github.io/fxtest-dashboard/#/issues

Commit Messages
---------------

See `Tim Pope's blog post on Git commit messages
<http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html>`_.

Rebasing Commits
----------------

While projects vary in their opinions on whether merge commits should be
avoided or not, it is generally a good idea to rebase a feature branch before
submitting a pull request.

Rebasing allows you to alter a series of commits, changing the history of your
repository. Typically you rebase a branch to:

- Combine smaller commits made during development into larger, logical commits
  that are easier to understand and review, or split up larger commits into
  smaller commits for the same purpose.
- Alter commit messages of previous commits.
- Move a branch to be based on the latest commit of the branch you want to
  merge into and resolve any conflicts that occur.

If you're not familiar with rebasing, you can start with this `short
guide`_ on how to use the ``git rebase`` command.

.. _short guide: https://help.github.com/articles/using-git-rebase

These changes all make the code review process as well as the merging process
easier, and are recommended for all pull requests.

.. warning:: Rebasing code that has already been pushed to a public or shared
             repository makes it very difficult for others to update their
             local repositories. Only rebase branches that you are absolutely
             sure no one else is using, such as feature branches on your
             personal fork.

Owners and the Mozilla GitHub Organization
------------------------------------------
See the `GitHub page on wiki.mozilla.org <https://wiki.mozilla.org/Github>`_
for information on the Mozilla organization on GitHub or anything that requires
owner access for the organization.
