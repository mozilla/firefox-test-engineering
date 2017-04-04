Test Results in Treeherder
==========================
`Treeherder <https://wiki.mozilla.org/EngineeringProductivity/Projects/Treeherder>`_
is Mozilla's reporting dashboard for checkins, builds, and test results. Our
automated test results are published to Treeherder via
`Pulse <https://wiki.mozilla.org/Auto-tools/Projects/Pulse>`_.

Submitting from Jenkins
~~~~~~~~~~~~~~~~~~~~~~~
To submit results from Jenkins you will need to write your job as a
`declarative pipeline <https://jenkins.io/doc/book/pipeline/>`_ using our
fxtest `shared library <https://github.com/mozilla/fxtest-jenkins-pipeline>`_.
See `the documentation <https://github.com/mozilla/fxtest-jenkins-pipeline#submittotreeherder>`_
for more information.

Viewing results in Treeherder
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
To view the results for a particular project, open
`Treeherder <https://treeherder.mozilla.org/>`_ and select the appropriate
repository from the menu. Most of our projects will be found within the
'qa automation tests' group. You will then see a resultset for each commit to
that repository, and any associated test jobs will be displayed. Click a job to
find the test logs and report. The
`Treeherder User Guide <https://treeherder.mozilla.org/userguide.html>`_ may
also be useful.
