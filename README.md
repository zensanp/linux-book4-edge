## About

Linux & DTS to allow booting on the X1E80100 Samsung Galaxy Book4 Edge, derived from [vamanea/linux-magicbook](https://github.com/vamanea/linux-magicbook), as these devices seem to share some similarities. Essentials working, but some things remain untested.

Thread: https://bugs.launchpad.net/ubuntu-concept/+bug/2084591

(Note: This is the 14" tmp branch. 16" dts can be found [here](https://github.com/zensanp/linux-book4-edge/tree/x1e80100-book4e-6.19-playground))

## Status
Supported features:
- [x] Keyboard - needs udev [quirk](https://bugs.launchpad.net/ubuntu-concept/+bug/2084591/comments/87)
   - [x] Keyboard backlight - via OpenBSD's [samsabi](https://cvsweb.openbsd.org/log/src/sys/dev/i2c/samsabi.c,v?sort=File)
- [x] Touchpad
- [x] USB type-c
  - [ ] USB hotplug (limited, at least on the 14")
  - [ ] DP Altmode
- [x] UFS storage
- [x] HDMI port on the right side
- [x] Built-in display - initially fixed using the following [patch](https://bugs.launchpad.net/ubuntu-concept/+bug/2084591/comments/99)
- [x] GPU - needs firmware + updated Mesa (tested on 25.3.3). [Enable](https://github.com/zensanp/linux-book4-edge/blob/49323f22adcc3d54c47c985622bdab90f1663aab/arch/arm64/boot/dts/qcom/x1e80100-samsung-galaxy-book4-edge.dts#L839) only after updating, or black screen after boot.
- [x] Touchscreen - needs included [workaround](https://github.com/zensanp/linux-book4-edge/issues/7#issuecomment-5517366291)
- [x] Wifi - needs firmware. 14" version also needs a patched board-2.bin as discussed [here](https://github.com/zensanp/linux-book4-edge/issues/3)
- [x] BT - needs firmware + MAC address must be set [manually](https://github.com/zensanp/linux-book4-edge/issues/5) for device.
- [x] ADSP and CDSP - need firmware
  - [x] Battery indicator - needs separate [driver](https://github.com/zensanp/linux-book4-edge/issues/4)
- [ ] Audio - untested (no HW protection. Proceed at own risk.)
- [x] Sleep - Does it work? [Yes]. Does it save power? [Not really].
- [ ] Webcam + Mic
