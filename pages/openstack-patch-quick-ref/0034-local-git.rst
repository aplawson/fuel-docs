Local git repository method
---------------------------

First, you will need to fetch repository data `using git <http://git-scm.com/book/en/Git-Basics-Getting-a-Git-Repository>`_.

Check git format-patch help for details::

  $ git format-patch -h
  usage: git format-patch [options] [<since> | <revision range>]

      -n, --numbered        use [PATCH n/m] even with a single patch
      -N, --no-numbered     use [PATCH] even with multiple patches
      -s, --signoff         add Signed-off-by:
      --stdout              print patches to standard out
      --cover-letter        generate a cover letter
      --numbered-files      use simple number sequence for output file names
      --suffix <sfx>        use <sfx> instead of '.patch'
      --start-number <n>    start numbering patches at <n> instead of 1

Suppose you want to generate a patch from the last 10 commits. Use the following
command starting from most recent commit in your local repo::

  $ git format-patch -10 HEAD --stdout > 0001-last-10-commits.patch
  A sample patch follows:
  +++ contex.py   2014-01-07 12:26:14.793787101 +0000
  --- /usr/share/pyshared/nova/context.py	2013-10-17 14:15:04.000000000 +0000
  @@ -21,6 +21,7 @@

   import copy
   import uuid
  +import time

   from nova import exception
   from nova.openstack.common.gettextutils import _
  +++ baserpc.py  2014-01-07 12:29:57.513881636 +0000
  --- /usr/share/pyshared/nova/baserpc.py	2013-10-17 14:15:04.000000000 +0000
  @@ -40,6 +40,7 @@

           1.0 - Initial version.
           1.1 - Add get_backdoor_port
  +        1.2 - New version
       """
