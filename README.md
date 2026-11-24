# expressiveos_ota

Over-the-air update information for denson9874's ExpressiveOS builds: cheetah (Pixel 7 Pro),
husky (Pixel 8 Pro), cubs (Pixel 11), grizzly (Pixel 11 Pro), kodiak (Pixel 11 Pro XL), and
yogi (Pixel 11 Pro Fold).

ExpressiveOS is its own ROM: its builds are signed with ExpressiveOS-only keys, and this repo
belongs to ExpressiveOS alone. Moving between ExpressiveOS and any other ROM always needs a clean
install.

An ExpressiveOS build's Updater reads the files here, on `main`:

- `builds/<device>.json`: the latest build, in the Updater's format. The download is the signed
  A/B OTA package, uploaded to
  [SourceForge](https://sourceforge.net/projects/denson9874-s-user-builds/files/expressiveos/)
  and served through the OTA mirror. `{"response": []}` means no build is published yet, and the
  Updater reports that there are no updates.
- `changelogs/<device>.txt`: what changed in that build.
- `builds/v2/<device>.json` and `changelogs/v2/<device>.txt`: the isolated feed for ExpressiveOS 2.0
  (pure-AOSP) builds, keeping 2.0 OTAs separate from 1.x (`builds/` and `changelogs/`).
- `devices/images/<device>.webp`: the phone's picture, shown by Settings > About phone.

The release step updates both after the OTA package has been uploaded. The Updater only installs
packages signed with ExpressiveOS's own release key.

First installs need a computer: unlock the bootloader and flash the fastboot zip. After that,
updates arrive over the air.
