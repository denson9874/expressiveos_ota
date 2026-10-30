# expressiveos_ota

Over-the-air update information for denson9874's ExpressiveOS builds: cheetah (Pixel 7 Pro),
husky (Pixel 8 Pro), kodiak (Pixel 11 Pro XL), grizzly (Pixel 11 Pro), cubs (Pixel 11) and
yogi (Pixel 11 Pro Fold).

ExpressiveOS is its own ROM, built on Evolution X: its builds are signed with ExpressiveOS-only
keys, and this repo is separate from the Evolution X and DerpFest ones. Moving between
ExpressiveOS and another ROM, Evolution X included, always needs a clean install.

Each phone's device tree in an ExpressiveOS build points its Updater here, at the files on `main`:

- `builds/<device>.json`: the latest build, in the Updater's format. The download is the signed
  A/B OTA package, uploaded to
  [SourceForge](https://sourceforge.net/projects/denson9874-s-user-builds/files/expressiveos/)
  and served through the OTA mirror. `{"response": []}` means no build is published yet, and the
  Updater reports that there are no updates.
- `changelogs/<device>.txt`: what changed in that build.

The release step updates both after the OTA package has been uploaded. The Updater only installs
packages signed with ExpressiveOS's own release key. All six phones share that key, so an entry
must only ever name its own phone's package.

First installs need a computer: unlock the bootloader and flash the fastboot zip. After that,
updates arrive over the air.
