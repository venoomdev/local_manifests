# AospExtended For Poco X3 NFC

To initialize a shallow clone, which will save even more space & time, use a command like this:

```bash
repo init --depth=1 -u git://github.com/AospExtended/manifest.git -b 12.x
mkdir .repo/local_manifests
curl -L -o .repo/local_manifests/aex_surya.xml -O -L https://raw.githubusercontent.com/xiaomeme-surya/local_manifests/12.x/aex_surya.xml
```
  
Then to sync up:
----------------

```bash
repo sync -c -j8 --force-sync --no-clone-bundle --no-tags
```
Finally to build:
-----------------

```bash
. build/envsetup.sh
lunch aosp_surya-userdebug
time make aex -j16
