======================
Continuous Integration
======================

Production
----------
Our **production** Jenkins instance is available at
https://qa-master.fxtest.jenkins.stage.mozaws.net/ and access is restricted according to
this `documentation <https://mana.mozilla.org/wiki/display/TestEngineering/qa-master.fxtest.jenkins.stage.mozaws.net>`_.

Sandbox, aka "Dev Jenkins"
-------
Our **sandbox** Jenkins instance is available at
https://qa-preprod-master.fxtest.jenkins.stage.mozaws.net/ and requires a connection to
the `Mozilla VPN`_. See the `documentation <https://mana.mozilla.org/wiki/display/TestEngineering/qa-preprod-master.fxtest.jenkins.stage.mozaws.net>`_
for further information regarding this instance.

Plugin Updates
``````````````
1. Whomever is able to respond and take action first, files a bug in Cloud Services | FXTest-Infra, cc:ing the rest of the core Jenkins/infra team, assigning the bug to themselves, and checking the “Security” checkbox at the bottom of the bug.  Include the Jenkins advisory text, with a link (like https://jenkins.io/security/advisory/2017-04-26/), the name of and link to the affected plugin(s), as well as the version to which you’ve upgraded Jenkins dev.  Please use `this Bugzilla template <https://bugzilla.mozilla.org/enter_bug.cgi?assigned_to=nobody%40mozilla.org&bug_file_loc=http%3A%2F%2F&bug_ignored=0&bug_severity=critical&bug_status=NEW&cc=ckolos%40mozilla.com&cc=oremj%40mozilla.com&cc=kthiessen%40mozilla.com&cc=stephen.donner%40gmail.com&cc=dave.hunt%40gmail.com&cf_blocking_fennec=---&cf_fx_iteration=---&cf_fx_points=---&cf_status_firefox55=---&cf_status_firefox56=---&cf_status_firefox57=---&cf_status_firefox_esr52=---&cf_tracking_firefox55=---&cf_tracking_firefox56=---&cf_tracking_firefox57=---&cf_tracking_firefox_esr52=---&cf_tracking_firefox_relnote=---&component=FXTest-infra&contenttypemethod=autodetect&contenttypeselection=text%2Fplain&defined_groups=1&flag_type-37=X&flag_type-4=X&flag_type-5=X&flag_type-607=X&flag_type-708=X&flag_type-721=X&flag_type-737=X&flag_type-781=X&flag_type-787=X&flag_type-800=X&flag_type-803=X&flag_type-846=X&flag_type-864=X&flag_type-914=X&flag_type-916=X&form_name=enter_bug&groups=cloud-services-security&maketemplate=Remember%20values%20as%20bookmarkable%20template&op_sys=Unspecified&priority=--&product=Cloud%20Services&qa_contact=rpappalardo%40mozilla.com&rep_platform=Unspecified&target_milestone=---&version=unspecified>`_, to file.
2. After filing, it's time to upgrade the plugin(s):
3. Update Jenkins dev:
  * Log in to the Jenkins dev instance
  * Click on “Manage Jenkins” on the left
  * Click on “Prepare for Shutdown”
  * Click on “Manage Plugins”
  * Click the “Check Now” button
  * Click the checkbox(es) next to the affected plugin(s), and click the “Download now and install after restart” button
  * Also select the checkbox to “Restart Jenkins when installation is complete and no jobs are running”
  * Under “Build Queue”, click the “cancel” link to allow Jenkins to safely restart
  * Run the sanity.pipeline job, vet the results, looking for new, related failures
  * Once the upgrades have completed on dev, resolve the Bugzilla bug as fixed
4. Kick off the "run all builds" test job
5. Carefully vet the results
6. If all goes well, follow the instructions for updating plugins on production Jenkins

Plugin Addition
```````````````
1. Coordinate with and give peers a heads-up that you’re installing a new plugin on dev (and why)
2. Install the plugin
3. Restart Jenkins
4. Run the ``sanity.pipeline`` job, and try to ensure there are no new, related failures
5. Once you’re comfortable with the results, do the following:
6. File a bug using `this Bugzilla template <https://bugzilla.mozilla.org/enter_bug.cgi?assigned_to=nobody%40mozilla.org&bug_file_loc=http%3A%2F%2F&bug_ignored=0&bug_severity=critical&bug_status=NEW&cc=ckolos%40mozilla.com&cc=oremj%40mozilla.com&cc=kthiessen%40mozilla.com&cc=stephen.donner%40gmail.com&cc=dave.hunt%40gmail.com&cf_blocking_fennec=---&cf_fx_iteration=---&cf_fx_points=---&cf_status_firefox55=---&cf_status_firefox56=---&cf_status_firefox57=---&cf_status_firefox_esr52=---&cf_tracking_firefox55=---&cf_tracking_firefox56=---&cf_tracking_firefox57=---&cf_tracking_firefox_esr52=---&cf_tracking_firefox_relnote=---&component=FXTest-infra&contenttypemethod=autodetect&contenttypeselection=text%2Fplain&defined_groups=1&flag_type-37=X&flag_type-4=X&flag_type-5=X&flag_type-607=X&flag_type-708=X&flag_type-721=X&flag_type-737=X&flag_type-781=X&flag_type-787=X&flag_type-800=X&flag_type-803=X&flag_type-846=X&flag_type-864=X&flag_type-914=X&flag_type-916=X&form_name=enter_bug&groups=cloud-services-security&maketemplate=Remember%20values%20as%20bookmarkable%20template&op_sys=Unspecified&priority=--&product=Cloud%20Services&qa_contact=rpappalardo%40mozilla.com&rep_platform=Unspecified&target_milestone=---&version=unspecified>`_, requesting the plugin(s) installation. Include the following info:
  * the plugin name(s), version(s), link(s) on https://plugins.jenkins.io/
  * mention that it’s been successfully tested on the dev instance.
7. Once Ops installs the plugin on Prod, make sure to:
  * test affected job(s), and
  * ping back in the Production-update bug with the appropriate resolution/verification data

.. _Mozilla VPN: https://mana.mozilla.org/wiki/display/IT/Mozilla+VPN

Ops-QA Pipeline
---------------
**The current flow for a project integrated into the Cloud Ops deploy pipeline is as follows:**

1. A tagged or pushed build from dev deploys to staging
2. Cloud Ops' deploy-pipeline script calls ``qaTest("kinto", "stage")``, which remotely runs the project's corresponding staging ("**stage**") test job, e.g. ``kinto.stage``, in our Jenkins instance
3. If our tests pass (returning exit code/return status of "0"), and after manual confirmation from Ops, the build gets promoted and pushed to production

**Getting a project's tests into the deploy pipeline:**

1. A suggestion is to have your project build and run tests in Jenkins, from a Docker image
2. Create a Jenkins job with the following syntax: **project.test_env** (e.g. **kinto.stage**), using the ``Pipeline from SCM`` option, and pointing to the Jenkinsfile
3. Once your project runs and passes in Jenkins:
4. File a bug (example: `bug 1384404 <https://bugzilla.mozilla.org/show_bug.cgi?id=1384404>`_), in the most-appropriate component for your project, under the Cloud Services product, requesting Ops enable your jobs in their pipeline
5. Next, from Ops' side, there is a `qaTest.groovy file <https://github.com/mozilla-services/cloudops-deployment/blob/c6a09fa1a62d1cddf3a3b560e92aca55a497d0d4/libs/pipeline/vars/qaTest.groovy#L13>`_ which calls `run_jenkins_job <https://github.com/mozilla-services/cloudops-deployment/blob/9626ef442346913733b2f14e11d490750d481411/bin/run_jenkins_job>`_, which, in turn, authenticates with QA (prod) Jenkins, and will run /job/${project}.${envName}

Build notifications
-------------------

Notifications can differ between projects, however typically whenever a build fails a notification is sent to the `fte-ci <https://groups.google.com/a/mozilla.com/forum/#!forum/fte-ci>`_ group. When the result of a build changes, a notification is sent to the #fx-test-alerts IRC channel on irc.mozilla.org.
