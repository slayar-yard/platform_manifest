Cyclone
==============

Getting Started
---------------

To get started with Android, you'll need to get
familiar with [Git and Repo](http://source.android.com/source/using-repo.html).

To initialize your local repository using the Cyclone trees, use a command like this:

```bash
repo init -u https://github.com/Project-Cyclone/platform_manifest.git -b r
```
Then to sync up:
```bash
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
```

Building the source
---------------

The source at cyclone is well configured for building.

```bash
#cache
export USE_CCACHE=1 && export USE_CCACHE_EXEC=$(command -v ccache) && ccache -M 150G && export ANDROID_JACK_VM_ARGS="-Xmx15g -Dfile.encoding=UTF-8 -XX:+TieredCompilation" 

#building
. build/envsetup.sh
lunch cyclone_device-userdebug && make bacon -j$(nproc --all)
```

- Will be supporting Smart build System also 
