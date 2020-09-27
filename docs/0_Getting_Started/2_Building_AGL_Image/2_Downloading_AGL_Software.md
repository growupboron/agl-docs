---
edit_link: ''
title: Downloading AGL Software
origin_url: >-
  https://raw.githubusercontent.com/automotive-grade-linux/docs-sources/master/docs/getting-started/image-workflow-download-sw.md
---

<!-- WARNING: This file is generated by fetch_docs.js using /home/boron/Documents/AGL/docs-webtemplate/site/_data/tocs/getting_started/master/image-development-workflow-getting-started-book.yml -->

https://download.automotivelinux.org/
    sstate-mirror/
        -> binary cache (speeds up the build for CI)
    agl/
        -> snapshots == nightly builds (dev-master, stable-otherwise)
        -> upload == CI (automatically builds in dev PRs)
        -> release == stable/released versions
        -> mirror == sources (dependencies for the raw build)
        -> archive == (~release but old)
        -> <//apps == application builds archive>

https://download.automotivelinux.org/AGL/release/jellyfish/9.99.4/ 
-> qemu(arm,arm64(*emulation for raspi4*))-> ONLY emulation, 
-> x86-64 -> emulation + hardware
        (https://download.automotivelinux.org/AGL/release/jellyfish/9.99.4/qemux86-64/deploy/images/qemux86-64/)
        -> file system image - qemu emulation (marginally diff, partioned image) (https://download.automotivelinux.org/AGL/release/jellyfish/9.99.4/qemux86-64/deploy/images/qemux86-64/agl-demo-platform-crosssdk-qemux86-64.ext4.xz)
        -> SD card for normal PC (https://download.automotivelinux.org/AGL/release/jellyfish/9.99.4/qemux86-64/deploy/images/qemux86-64/agl-demo-platform-crosssdk-qemux86-64.wic.xz)
        -> virtual box / vbox (https://download.automotivelinux.org/AGL/release/jellyfish/9.99.4/qemux86-64/deploy/images/qemux86-64/agl-demo-platform-crosssdk-qemux86-64.wic.vmdk.xz)
->nogfx (binary graphics driver, can't host, no display-demo, ok for ci, boots up rensas in headless)
    ivi -> not demo (nogfx)
->raspi4 (https://download.automotivelinux.org/AGL/release/jellyfish/9.99.4/raspberrypi4/deploy/images/raspberrypi4-64/)
    -> bootable image to SD (https://download.automotivelinux.org/AGL/release/jellyfish/9.99.4/raspberrypi4/deploy/images/raspberrypi4-64/agl-demo-platform-crosssdk-raspberrypi4-64-20200912184922.rootfs.wic.xz)
    sources (https://download.automotivelinux.org/AGL/release/jellyfish/9.99.4/raspberrypi4/deploy/sources/)
    sdk -  (https://download.automotivelinux.org/AGL/release/jellyfish/9.99.4/raspberrypi4/deploy/sdk/)
     sh self extracting cross toolchain (w/o yocto)   (https://download.automotivelinux.org/AGL/release/jellyfish/9.99.4/raspberrypi4/deploy/sdk/poky-agl-glibc-x86_64-agl-demo-platform-crosssdk-aarch64-raspberrypi4-64-toolchain-9.99.4.sh)
        

https://wiki.automotivelinux.org/agl-distro/source-code -> in principle correct, a bit outdate/cluttered
