# Build RisingOS 14

## Prerequisites
- refer to [AOSP](https://source.android.com/docs/setup/start/requirements)

## Build
1. Initialise repo with LineageOS-based source code. e.g.
    ```
    repo init -u https://github.com/LineageOS/android -b lineage-21 --git-lfs --depth=1
    ```

2. Clone [local_manifests](https://github.com/Project-Anfangx/local_manifests)
    ```
    git clone https://github.com/Project-Anfangx/local_manifests -b fourteen .repo/local_manifests
    ```

3. Sync
    ```
    repo sync -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
    ```

4. Build
    ```
    source build/envsetup.sh
    lunch lineage_anfangx-ap2a-user
    mka bacon
    ```
    Compiling source can take anywhere from 30 mins - 4hrs depending on how powerful your hardware is,
    After successful build, you can find your flashable rom zip at ```out/target/product/anfangx/```
