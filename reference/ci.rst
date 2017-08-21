Continuous Integration
======================

Production
----------
Our production Jenkins instance is available at
https://fx-test-jenkins.stage.mozaws.net and access is restricted according to
this `documentation <https://mana.mozilla.org/wiki/display/TestEngineering/fx-test-jenkins.stage.mozaws.net>`_.

Sandbox, aka "Dev Jenkins"
-------
Our sandbox Jenkins instance is available at
https://fx-test-jenkins-dev.stage.mozaws.net:8443 and requires a connection to
the `Mozilla VPN`_. See the `documentation <https://mana.mozilla.org/wiki/display/TestEngineering/fx-test-jenkins-dev.stage.mozaws.net>`_
for further information regarding this instance.

Plugin Updates
``````````````
1.Whomever is able to respond and take action first, files a bug in Cloud Services | FXTest-Infra, cc:ing the rest of the core Jenkins/infra team, assigning the bug to themselves, and checking the “Security” checkbox at the bottom of the bug.  Include the Jenkins advisory text, with a link (like https://jenkins.io/security/advisory/2017-04-26/), the name of and link to the affected plugin(s), as well as the version to which you’ve upgraded Jenkins dev.  Please use `this Bugzilla template <https://bugzilla.mozilla.org/enter_bug.cgi?assigned_to=nobody%40mozilla.org&bug_file_loc=http%3A%2F%2F&bug_ignored=0&bug_severity=critical&bug_status=NEW&cc=ckolos%40mozilla.com&cc=oremj%40mozilla.com&cc=kthiessen%40mozilla.com&cc=stephen.donner%40gmail.com&cc=dave.hunt%40gmail.com&cf_blocking_fennec=---&cf_fx_iteration=---&cf_fx_points=---&cf_status_firefox55=---&cf_status_firefox56=---&cf_status_firefox57=---&cf_status_firefox_esr52=---&cf_tracking_firefox55=---&cf_tracking_firefox56=---&cf_tracking_firefox57=---&cf_tracking_firefox_esr52=---&cf_tracking_firefox_relnote=---&component=FXTest-infra&contenttypemethod=autodetect&contenttypeselection=text%2Fplain&defined_groups=1&flag_type-37=X&flag_type-4=X&flag_type-5=X&flag_type-607=X&flag_type-708=X&flag_type-721=X&flag_type-737=X&flag_type-781=X&flag_type-787=X&flag_type-800=X&flag_type-803=X&flag_type-846=X&flag_type-864=X&flag_type-914=X&flag_type-916=X&form_name=enter_bug&groups=cloud-services-security&maketemplate=Remember%20values%20as%20bookmarkable%20template&op_sys=Unspecified&priority=--&product=Cloud%20Services&qa_contact=rpappalardo%40mozilla.com&rep_platform=Unspecified&target_milestone=---&version=unspecified>`_, to file, and assign to yourself, if you're able to perform the upgrade.
2.After filing, it's time to upgrade the plugin(s):
3.Update Jenkins dev:
*Log in to the Jenkins dev instance
*Click on “Manage Jenkins” on the left
*Click on “Prepare for Shutdown”
*Click on “Manage Plugins”
*Click the “Check Now” button
*Click the checkbox(es) next to the affected plugin(s), and click the “Download now and install after restart” button
*Also select the checkbox to “Restart Jenkins when installation is complete and no jobs are running”
*Under “Build Queue”, click the “cancel” link to allow Jenkins to safely restart
*Run the sanity.pipeline job, vet the results, looking for new, related failures
*Once the upgrades have completed on dev, resolve the Bugzilla bug as fixed
4.Kick off the "run all builds" test job
5.Carefully vet the results
6.If all goes well, follow the instructions for updating plugins on production Jenkins


.. _Mozilla VPN: https://mana.mozilla.org/wiki/display/IT/Mozilla+VPN
