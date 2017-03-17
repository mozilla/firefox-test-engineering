Test Automation Process
=======================

While the details vary, there is a general framework for working on Firefox
Test Engineering test automation projects. This document attempts to describe that process.

Finding a Bug or GitHub Issue
-----------------------------

The first step is finding a good bug or GitHub Issue to work on.

- GitHub Issues are written when new tests need to be written, or changes need to be made to fix existing flaky or failing tests. They include a description of the steps and expected results. You can find a comprehensive list of open GitHub Issues for our team on the `Firefox Test Engineering Dashboard`_.

- Unclaimed Issues are open and available for anyone to work on. You will know if it is unclaimed by reading the comments and checking if it is already assigned to someone. Make sure to comment on the Issue when you find one that you plan to complete.

- Bugs are written when specific features, tests or fixes are to be implemented. Bugs that are marked as 'mentored' are a good place to start as you will have support while learning the project.

- Finding a mentored bug that fits your interests and skill set can be challenging. We recommend going to `Bugs Ahoy`_ to find mentored bugs, filtered by skills or areas of interest. Know that listed bugs will include all Mozilla projects, not just ones within the Firefox Test Engineering team.

- Commenting on a bug is generally a good way to indicate you will work on it. However, some teams prefer that you submit a pull request rather than a comment. Contact the bug author if you have questions.


.. _Firefox Test Engineering Dashboard: https://mozilla.github.io/fxtest-dashboard/#/issues
.. _Bugs Ahoy:  https://www.joshmatthews.net/bugsahoy/

Working on the Bug/Issue
------------------------
After claiming a Bug/Issue, you will submit your pull request with your work in a GitHub feature branch.

Any mentors or project owners assigned to it will review your work and give constructive feedback and instructions for any changes that need to be made.  After the pull request is completed to satisfaction it will be merged into the project code.

The Bug/Issue will be resolved and closed after a successful code merge.


Git and GitHub
^^^^^^^^^^^^^^

For projects using Git and GitHub, the process can be explained in more detail:

- On GitHub, ensure you have `forked the repository`_ for your project to your
  own account and have added it as a `remote`_ to your repository.
- Identify the main development branch for your project. This is usually the
  ``master`` branch.
- Make sure the current branch is the development branch, and create a new
  branch off of it for your feature.
- Start `running test automation`_ to get familiar with the project.
- Once your work is committed and ready for review, `push the branch`_ to your
  fork on GitHub and `submit a pull request`_.
- If the project uses Bugzilla for issue tracking, `create an attachment
  to your issue's bug pointing at the pull request`_. Otherwise, if
  you know who should review your change, add a comment to your pull request
  with their ``@Username`` in it and ask for a review.

.. seealso::

   :doc:`/reference/python-style`
      A useful styleguide for Python best practices.

   :doc:`/reference/git_github`
      A short list of tips and tricks for using GitHub.

   `GitHub Flow <https://guides.github.com/introduction/flow/>`_
      A process for branching, reviewing, and merging code that is very similar
      to the process above.

.. _forked the repository: https://help.github.com/articles/fork-a-repo
.. _remote: https://help.github.com/articles/about-remote-repositories
.. _push the branch: https://help.github.com/articles/pushing-to-a-remote
.. _submit a pull request: https://help.github.com/articles/using-pull-requests
.. _create an attachment to your issue's bug pointing at the pull request: https://globau.wordpress.com/2013/10/21/github-pull-requests-and-bugzilla/
.. _running test automation: https://developer.mozilla.org/en-US/docs/Mozilla/QA/Running_Web_QA_automated_tests


Mobile
------
Mobile platforms such as iOS and Android are also an important part of our testing process. Testing is done on mobile platforms, and there are also mobile-specific tests.

iOS
^^^
Currently we use Apple's XCUITest framework in Swift. The test can be written and executed on
Apple's XCode App, and you can see some of our `examples in the Firefox for iOS`_ repository. Some of the older
Tests are in `KIFTest framework`_, but since they use undocumented Apple APIs, and XCUITest framework has been
maturing, we are trying to create new tests in XCUITest framework.

You can learn more about basics of Swift and XCUITest from below websites:

- `Apple Developer Site`_.

- `Swift Language Reference`_.

- `UI Testing Cheat Sheet and Examples`_.

.. _examples in the Firefox for iOS: https://github.com/mozilla-mobile/firefox-ios/tree/master/XCUITests
.. _KIFTest framework: https://github.com/mozilla-mobile/firefox-ios/tree/master/UITests
.. _Apple Developer Site: https://developer.apple.com/library/content/documentation/DeveloperTools/Conceptual/testing_with_xcode/chapters/09-ui_testing.html#//apple_ref/doc/uid/TP40014132-CH13-SW1
.. _Swift Language Reference: https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/AboutTheLanguageReference.html
.. _UI Testing Cheat Sheet and Examples: http://masilotti.com/ui-testing-cheat-sheet/

Android
^^^^^^^
A few of our Android mobile test-automation projects (particularly those written with Selenium WebDriver) use
`Appium <http://appium.io/>`_.  For Firefox for Android testing automation that does not involve the testing
of GeckoView, there is a `proof-of-concept test environment`_ using Appium.

.. _proof-of-concept test environment: https://github.com/npark-mozilla/CG_Mobile_Test

Next steps
----------

At this point you should have all the information and tools you need to make
your first contribution to Mozilla! Once you've submitted your work and gotten
it merged, it's time to celebrate: you've earned it!

As you continue to contribute, you may want to check out the
:doc:`/reference/index` to find generally useful information for contributors
of all levels.

Good luck!
