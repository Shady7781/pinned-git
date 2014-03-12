# pinned-git

Do you trust all 160 parties in `/etc/ssl/certs` to identify only the real GitHub as github.com?  If not, you probably want to pin some SSL certificates, to make sure no men in the middle have modified your git clone in transit.  git doesn't support this, but **pinned-git** will automatically pin the right certificate for the domain you're cloning from.  **pinned-git** supports pinning for the domains listed below.  If there is no pin for the domain being cloned from, it will proceed anyway without a pin.

**pinned-git** protects `git clone` and subsequent fetches in the cloned repo, assuming that you keep the `[http] sslcainfo = ` option in the clone's `~/.git/config`.

Because `sslcainfo = ` is set to an absolute path, you should install **pinned-git** to a location that will not change.

This is pre-alpha software.  It works only on Debian and Ubuntu, where git uses a curl linked to GnuTLS.  OpenSSL expects to find CAs in the CA bundle, but we put site certificates there.  Also, pinning functionality would be better to implement in curl instead.


## Pinned domain list

* https://github.com/
* https://bitbucket.org/
* https://code.google.com/
* https://git.gitorious.org/
* https://git.kernel.org/
* https://kernel.googlesource.com/
* https://chromium.googlesource.com/
* https://android.googlesource.com/
* https://git.overlays.gentoo.org/
* https://alioth.debian.org/
* https://git.eclipse.org/
* https://git.gnome.org/
* https://gitlab.com/
