# Aosp Extended For Poco X3 NFC

To initialize a shallow clone, which will save even more space & time, use a command like this:

```bash
repo init --depth=1 --no-repo-verify -u https://github.com/projectarcana-aosp/manifest -b 12.x -g default,-mips,-darwin,-notdefault
mkdir .repo/local_manifests
curl -L -o .repo/local_manifests/aex_surya.xml -O -L https://raw.githubusercontent.com/venoomdev/local_manifests/12.x/aex_surya.xml
```
  
Then to sync up:
----------------

```bash
repo sync -c --no-clone-bundle --no-tags --optimized-fetch --prune --force-sync -j4
```
Finally to build:
-----------------

```bash
. build/envsetup.sh
lunch aosp_surya-userdebug
time make bacon -j16
