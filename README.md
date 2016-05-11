# package-deb

package-deb is an atbin packager that builds `deb`s.

# Usage

See [documentation](http://anarchytools.org/docs/package-deb.html)

# AT internal release process

To get AT tools in our official repos, do the following:

1.  Run CI
2.  Download a deb package built from CI
3.  Upload deb package to packagecloud.io via web

Ask @drewcrawford for packagecloud.io access

# Maintainer notes

package-deb is self-hosting; it does not require AT to build.  This is primarily because we want to use it to package atbuild itself, so it cannot depend on atbuild to work.

package-deb requires a large number of Debian tools as dependencies, but using them is considered preferable to manually emitting a package file directly.

For these reasons, it's written in shell, largely glues together Debian tools, and there is no compile step.  It's a manually-mananged [`atbin`](http://anarchytools.org/docs/atbin.html) format.  

As a result, package-deb is used to package itself, which is basically the test of its correctness.



