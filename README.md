# LineageOS For Poco X3 NFC

To initialize a shallow clone, which will save even more space & time, use a command like this:

```bash
repo init -u git://github.com/LineageOS/android.git -b lineage-19.0
mkdir .repo/local_manifests
curl -L -o .repo/local_manifests/lineage_surya.xml -O -L https://raw.githubusercontent.com/xiaomeme-surya/local_manifests/lineage-19.0/lineage_surya.xml
```
  
Then to sync up:
----------------

```bash
repo sync --force-sync --optimized-fetch --no-tags --no-clone-bundle --prune -j8
```
Finally to build:
-----------------

```bash
. build/envsetup.sh
lunch lineage_surya-userdebug
time make bacon -j16
