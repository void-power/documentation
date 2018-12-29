# Void Linux ppc64

This is the Void Linux porting project for 64-bit PowerPC/POWER systems. Keep in mind that **it is unofficial at this point**.

## Rationale

Void currently has no support for ppc64. Since ppc64 is becoming more relevant again with high systems such as Raptor Talos 2, it is desirable to have support for it in the distribution; this project's aim is to become a staging area for all porting work before it makes it upstream in Void Linux.

Until there are official builds, the project will continue to provide certain non-mergeable modifications into the repositories for smoothest user experience, such as builds of `xbps` packages with the default repo location pointing to the unofficial one in order to avoid having to manually configure things.

## Supported targets

This project primarily aims to support modern, high performance systems, without a particular focus on old hardware. That does not mean it is unsupported, however. There are three targets the project aims to support.

- Little endian glibc (`ppc64le`)
- Little endian musl (`ppc64le-musl`)
- Big endian musl (`ppc64-musl`)

The first two, being little endian, are only meant to work on POWER8 and higher, and are the primary targets, because of smoothest software support (least likely to encounter issues getting it to build or run). Big endian `musl` target should work on all POWER4 and newer systems, such as PowerPC G5/970 present on Power Macs. 32-bit PowerPC is out of scope of the project, and is already being done elsewhere.

## Project stages

We are currently still in stage 1.

### Stage 1

This is the state where no platform specific work is held in upstream Void Linux repositories and therefore all changes are downstream in `void-ppc64`. The goal is to move on as soon as possible.

At this point, the project maintains an unofficial binary repository and eventually ISO and rootfs builds. The unofficial repository is fully working and best covers the `ppc64le` target but others are also being built.

### Stage 2

At this point, changes will start making it into upstream `void-packages` and potentially other repositories. At this point, Void still won't provide any official packages. This project will act as a staging area for new changes, which will get submitted into upstream as soon as they reach mergeable status.

This project will still provide a binary repository of packages, snapshots etc. for anyone's use.

### Stage 3

At this point Void Linux should start providing binary packages, which is the ultimate goal; it is yet unsure what path will be taken as cross-compilation is often impossible or results in missing features. It is unsure when the upstream project will do this, so `void-ppc64` is ready to provide continuously updated binary builds indefinitely, built on native hardware rather than through the means of cross-compilation (which means fully featured packages). The project will continue acting as a staging area for new commits to make it upstream.

The binary repository will transform into an overlay repository containing testing packages.

## Package/build mirrors

The main project binary location is https://ftp.octaforge.org/void-ppc64/.

- xbps repository (`ppc64le`): https://ftp.octaforge.org/void-ppc64/current
- xbps repository (`ppc64le-musl`, `ppc64-musl`): https://ftp.octaforge.org/void-ppc64/musl
- static xbps for both endians: https://ftp.octaforge.org/void-ppc64/static
- rsync for mirroring: `rsync://octaforge.org/void-ppc64`

### Mirrors

Since my server space is not free, mirrors are always appreciated! Let me know if you set up a mirror. Use `rsync`, the URL is provided above.

Current list:

- http://mirrors.servercentral.com/voidlinux-ppc64/ (provided by `zdykstra` from Void/Talos community, also hosts a Void mirror)