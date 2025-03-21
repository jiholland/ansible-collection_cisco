=======================
Test.Test Release Notes
=======================

.. contents:: Topics

v25.3.0
=======

Minor Changes
-------------

- all roles - bump min_ansible_version to 2.16
- software role - do not remove ip ssh bulk
- software role - remove no boot manual

v24.11.1
========

Bugfixes
--------

- software role - added throttle
- software role - ios tftp upload

v24.11.0
========

Minor Changes
-------------

- software role - Check mode for installing software.

Bugfixes
--------

- software role - Remove inactive software condition bugfix.

v24.6.0
=======

Minor Changes
-------------

- playbooks - added playbooks
- software role - check-mode for image upload
- software role - no check-mode for installation assert
- software role - replaced handler for ip ssh bulk-mode with always in block

v24.4.2
=======

Minor Changes
-------------

- software role - removed old tasks files.

v24.4.1
=======

Minor Changes
-------------

- software role - improve arg_spec
- software role - move some defaults to vars
- software role - use scp instead of tftp for file transfer

v24.4.0
=======

Minor Changes
-------------

- all roles - use quotes for user-side strings such as descriptions, names, and messages

Bugfixes
--------

- backup role - check_mode for handler

v24.3.0
=======

Minor Changes
-------------

- all roles - minor improvements
- backup role - check mode

v24.2.2
=======

Minor Changes
-------------

- various bugfixes and improvements

v24.2.1
=======

Minor Changes
-------------

- all roles - added arg spec in meta for required arguments

v24.2.0
=======

Minor Changes
-------------

- software_upgrade role - defaults and use module for nxos installation
- tacacs role - vrf fix for nxos

v24.0.1
=======

Minor Changes
-------------

- all roles - prefix internal variables with double underscore

v24.0.0
=======

Minor Changes
-------------

- all roles - update doc
- interface_description - cleanup templates
- tacacs - cleanup templates

v23.0.5
=======

Minor Changes
-------------

- software - Added support for vrf on catalyst when uploading image.

v23.0.4
=======

Minor Changes
-------------

- software - Made changes to default timeouts.
- software - Moved nexus issu install into separate task.
- software - Replaced meta with wait_for in install rescue task.

v23.0.3
=======

Minor Changes
-------------

- backup - removed condition when including tasks
- galaxy - added tags
- interface_description - removed condition when including tasks
- tacacs - removed condition when including tasks

v23.0.2
=======

Minor Changes
-------------

- backup - set example in readme to use stragegy linear because of run_once.
- meta - bump ansible to 2.15
- software - set example in readme to use stragegy linear because of run_once.

Bugfixes
--------

- backup - removed debug task.
- backup - use chdir not args in handler.
- software - typo in task name.

v23.0.1
=======

Minor Changes
-------------

- backup - use cmd, not free-form, for handler.
- tacacs - readme.me fixed typo.

v23.0.0
=======

