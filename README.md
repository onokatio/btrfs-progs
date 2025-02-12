Btrfs-progs [![build status](https://travis-ci.org/kdave/btrfs-progs.svg?branch=devel)](https://travis-ci.org/kdave/btrfs-progs) [![coverity status](https://scan.coverity.com/projects/617/badge.svg)](https://scan.coverity.com/projects/btrfs-progs)
===========

Userspace utilities to manage btrfs filesystems.
License: GPLv2.

Btrfs is a copy on write (COW) filesystem for Linux aimed at implementing
advanced features while focusing on fault tolerance, repair and easy
administration.


This repository hosts following utilities:

* **btrfs** &mdash; the main administration tool ([manual page](https://btrfs.wiki.kernel.org/index.php/Manpage/btrfs))
* **mkfs.btrfs** &mdash; utility to create the filesystem ([manual page](https://btrfs.wiki.kernel.org/index.php/Manpage/mkfs.btrfs))
* all-in-one binary in the busybox style with mkfs.btrfs, btrfs-image and other tools built-in ([standalone tools](https://github.com/kdave/btrfs-progs/blob/master/Documentation/btrfs.asciidoc#standalone-tools))

The C and python 3 bindings are provided by a LGPL library **libbtrfsutil** see
[libbtrfsutil/README.md](libbtrfsutil/README.md) for more.

See [INSTALL](INSTALL) for build instructions and [tests/README.md](tests/README.md) for
testing information.

Release cycle
-------------

The major version releases are time-based and follow the cycle of the linux
kernel releases. The cycle usually takes 2 months. A minor version releases may
happen in the meantime if there are bug fixes or minor useful improvements
queued.

The release tags are signed with a GPG key ID `F2B4 1200 C54E FB30 380C  1756 C565 D5F9 D76D 583B`,
release tarballs are hosted at [kernel.org](https://www.kernel.org/pub/linux/kernel/people/kdave/btrfs-progs/).
See file [CHANGES](CHANGES) or [changelogs on wiki](https://btrfs.wiki.kernel.org/index.php/Changelog#By_version_.28btrfs-progs.29).

Reporting bugs
--------------

There are several ways, each has its own specifics and audience that can give
feedback or work on a fix. The following list is sorted in the order of
preference:

* [github issue tracker](https://github.com/kdave/btrfs-progs/issues)
* to the mailing list *linux-btrfs@vger.kernel.org* -- (not required to
  subscribe), beware that the mail might get overlooked in other traffic
* IRC (irc.freenode.net #btrfs) -- good for discussions eg. if a bug is already
  known, but reports could miss developers' attention
* [bugzilla.kernel.org](https://bugzilla.kernel.org) -- (requires
  registration), set the product to Filesystems and component Btrfs, please put
  'btrfs-progs' into the subject so it's clear that it's not a kernel bug
  report


Development
-----------

The patch submissions, development or general discussions take place at
*linux-btrfs@vger.kernel.org* mailinglist, subsciption is not required to post.

The GitHub pull requests will not be accepted directly, the preferred way is to
send patches to the mailinglist instead. You can link to a branch in any git
repository if the mails do not make it to the mailinglist or just for
convenience (makes it easier to test).

The development model of btrfs-progs shares a lot with the kernel model. The
github way is different in some ways. We, the upstream community, expect that
the patches meet some criteria (often lacking in github contributions):

* **one logical change per patch**: eg. not mixing bugfixes, cleanups, features
  etc., sometimes it's not clear and will be usually pointed out during reviews
* proper **subject line**: eg. prefix with _btrfs-progs: subpart, ..._ ,
  descriptive yet not too long, see `git log --oneline` for some inspiration
* proper **changelog**: the changelogs are often missing or lacking explanation _why_
  the change was made, or _how_ is something broken, _what_ are user-visible
  effects of the bug or the fix, _how_ does an improvement help or the intended
  _usecase_
* the **Signed-off-by** line: this documents who authored the change, you can read
  more about the
  [The Developer's Certificate of Origin (chapter 11)](https://www.kernel.org/doc/html/latest/process/submitting-patches.html#sign-your-work-the-developer-s-certificate-of-origin)
  * if you are not used to the signed-off style, your contributions won't be
    rejected just because of it's missing, the _Author:_ tag will be added as a
    substitute in order to allow contributions without much bothering with
    formalities

Documentation updates
---------------------

Documentation fixes or updates do not need much explanation so sticking to the
code rules in the previous section is not necessary. GitHub pull requests are
OK, patches could be sent to me directly and not required to be also in the
mailinglist. Pointing out typos via IRC also works, although might get
accidentally lost in the noise.

References
----------

* [wiki/Developer's FAQ](https://btrfs.wiki.kernel.org/index.php/Developer's_FAQ)
* [wiki/Getting started](https://btrfs.wiki.kernel.org/index.php/Getting_started)
* [wiki/TODO](https://btrfs.wiki.kernel.org/index.php/Project_ideas#Userspace_tools_projects)
* [Btrfs-progs changelogs](https://btrfs.wiki.kernel.org/index.php/Changelog#By_version_.28btrfs-progs.29)
* [wiki/FAQ](https://btrfs.wiki.kernel.org/index.php/FAQ)
* [Wiki with more information](https://btrfs.wiki.kernel.org)
