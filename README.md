<!--
SPDX-FileCopyrightText: The LineageOS Project
SPDX-License-Identifier: Apache-2.0
-->

# android_vendor_lineage-priv_keys

A template for signing LineageOS 20.0 & above builds.

## Usage

1. Clone this repo to `vendor/lineage-priv/keys` (on your synced ROM rootdir)
```bash
git clone https://github.com/suchit-7x/android_vendor_lineage-priv_keys.git vendor/lineage-priv/keys
```

2. Go to `vendor/lineage-priv/keys` directory.
```bash
cd vendor/lineage-priv/keys
```

3. Run it:
```bash
./keys.sh
```

It will generate the certificates in `vendor/lineage-priv/keys`.

# Testing

Included `check_keys.py` script checks whether all apk/apex/capex files in the build out are signed with keys within its directory. Be aware that some targets are **expected** to be signed with vendor key, for example `com.android.apex.cts.shim.v1_prebuilt`.

```
$ ./check_keys.py ~/lineage/out/target/product/spring
/home/suchit/lineage/out/target/product/spring/obj/ETC/com.android.apex.cts.shim.v1_prebuilt_intermediates/com.android.apex.cts.shim.apex is signed with an unknown key!
```