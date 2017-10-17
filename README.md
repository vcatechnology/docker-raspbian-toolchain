# Raspbian Docker Tool Chain Image

[![][layers]][microbadger] [![][version]][microbadger] [![][license]][microbadger] [![][commit]][github]

This container derives from [vcatechnology/raspbian-ci][parent] so that the image has the latest
[Raspbian][project] packages. It then installs the some useful packages for building projects with the
[VCA Tool Chain][vca-tool-chain].

Available on Docker Hub as [vcatechnology/raspbian-toolchain][docker-hub]

## `sudo`

The Docker image creates a user account 'build-server' with `sudo` permissions. The `sudo` password
is disabled to allow non-interactive sudo calls.

## Emulation

This Docker image can be ran on an x86_64 host. To do this, the
capability to run ARM executables transparently must be enabled. On Linux the easiest
way to do this is to install the `binfmt-support` package:

```
packagemanager install binfmt-support qemu-user-static binfmt-qemu-static
systemctl enable --now binfmt-support
```

[parent]: https://hub.docker.com/r/vcatechnology/raspbian-ci/ "Parent"
[docker-hub]: https://hub.docker.com/r/vcatechnology/raspbian-toolchain/ "Docker Hub"
[project]: https://www.raspbian.org/ "Project"
[github]: https://github.com/vcatechnology/docker-arch "GitHub"
[microbadger]: http://microbadger.com/images/vcatechnology/raspbian-toolchain "Microbadger"
[layers]: https://images.microbadger.com/badges/image/vcatechnology/raspbian-toolchain.svg "Image Layers"
[version]: https://images.microbadger.com/badges/version/vcatechnology/raspbian-toolchain.svg "Image Version"
[license]: https://images.microbadger.com/badges/license/vcatechnology/raspbian-toolchain.svg "Image License"
[commit]: https://images.microbadger.com/badges/commit/vcatechnology/raspbian-toolchain.svg "Image Commit"
[vca-tool-chain]: https://gitlab.vcatechnology.com/tool-chain/tool-chain "VCA Tool Chain"
