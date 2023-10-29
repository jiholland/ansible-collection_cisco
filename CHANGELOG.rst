=======================
Test.Test Release Notes
=======================

.. contents:: Topics


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
