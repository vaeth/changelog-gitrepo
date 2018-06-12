
changelog-gitrepo - Create ChangeLog data for gentoo repositories from git

Author: Martin Väth <martin@mvath.de>

The license of this project is GNU Public License v2.

For git repositories, ChangeLog files usually do not exist in Gentoo
repositories, since essentially these just copy the git commit messages.

This project outputs a ChangeLog for a specified package (or directory)
in a specified local git repository, using the git commit data.

Note that a similar effect but for all packages may be achieved by

`egencache --update-changelogs`

However, the latter command actually creates all ChangeLog files and not only
outputs selected ones to stdout. Also, the output format looks similar but
is not identical (e.g. changelog-gitrepo filters some more lines).

Usage:

- `changelog-gitrepo category/package::repo`
- `changelog-gitrepo eclass::repo

If `::repo` is omitted, it defaults to `::gentoo`.
If eix is installed, `category/` can be omitted.

For installation just copy the content of bin/ into your $PATH.
There is also an ebuild in the mv overlay
(available by `app-select/eselect-repository` or `app-portage/layman`).
