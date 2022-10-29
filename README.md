dragonshield-LOS-18.1-WIP_kernel
================================

**This Manifest will build either Dragon or Dragonshield (Pixel-C)**

---

## **WARNING:** We are using The WIP Testing Kernel in this Repo:

To initialize your local repository use a command like this:

````bash
repo init -u https://github.com/LineageOS/manifests -b lineage-18.1
````

Then you need to clone the local_manifest:

# **WIP-4.9 Kernel**

```
cd .repo
git clone https://github.com/DevPixel-C/manifests-followmsi.git -b dragonshield-LOS-18.1-WIP_Kernel TMP
cd TMP
mv ./local_manifests ../
cd ../../
```

# **Original-4.9 Kernel**

```
cd .repo
git clone https://github.com/DevPixel-C/manifests-followmsi.git -b dragon-lineage-18.1 TMP
cd TMP
mv ./local_manifests ../
cd ../../
```

````bash
git clone https://github.com/DevPixel-C/manifests-followmsi.git
git checkout origin/dragon-lineage-18.1
````

Pls copy the "local_manifests" folder into your "./repo" folder inside your build tree.
Like below ...

````bash
~/root-of-your-build-tree/.repo$ ll
total 76
drwxrwxr-x  8 DevPixel-C DevPixel-C  4096 Feb 28 20:35 ./
drwxrwxr-x 31 DevPixel-C DevPixel-C  4096 Mar  1 09:21 ../
drwxrwxr-x  2 DevPixel-C DevPixel-C  4096 Mar  3 18:47 local_manifests/
drwxrwxr-x  3 DevPixel-C DevPixel-C  4096 Feb 28 20:33 manifests/
drwxrwxr-x 10 DevPixel-C DevPixel-C  4096 Feb 28 20:34 manifests.git/
lrwxrwxrwx  1 DevPixel-C DevPixel-C    21 Feb 28 20:33 manifest.xml -> manifests/default.xml
-rw-rw-r--  1 DevPixel-C DevPixel-C 11508 Feb 28 23:02 project.list
drwxrwxr-x 18 DevPixel-C DevPixel-C  4096 Feb 28 21:49 project-objects/
drwxrwxr-x 31 DevPixel-C DevPixel-C  4096 Feb 28 22:01 projects/
drwxrwxr-x  7 DevPixel-C DevPixel-C  4096 Feb 28 18:02 repo/
-rw-rw-r--  1 DevPixel-C DevPixel-C 29667 Feb 28 23:02 .repo_fetchtimes.json
````

Then to sync up:

````bash
repo sync --force-sync

repo sync --force-sync --no-clone-bundle -j10
````

Finally to build:

````bash
source build/envsetup.sh

brunch dragon

brunch dragonshield

**Extra:**
Recovery partition: mka recoveryimage
Boot image ramdisk: mka bootimage
Vendor_boot image ramdisk: mka vendorbootimage
````

