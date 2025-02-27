# Buildroot containers for image-builder

This branch contains buildroot containers for image-builder-cli
to allow `qemu-user` based crossbuilding.

See https://github.com/osbuild/images/pull/1263 for details how
it works. The requirements from a bootstrap buildroot container
are:
* python3 for the runners
* rpm so that the real buildroot rpms can get installed
* setfiles so that the selinux stage for the real buildroot can run

Currently this repo contains riscv because the upstream
`fedora-toolbox:41` container does not contain `setfiles` 
(policycoreutils) as part of the container. Once this is added
upstream this container (and hopefully the entire repo) can go
away again.
