# Krzysztof Burghardt's OpenWRT packages feed

## Description

This is an OpenWrt package feed containing packages maintained by
Krzysztof Burghardt.

## Usage

To use these packages, add the following line to the feeds.conf
in the OpenWrt buildroot:

```
src-git burghardt https://github.com/burghardt/openwrt-feed.git
```

To install all package definitions, run:

```
./scripts/feeds update burghardt
./scripts/feeds install -a -p burghardt
```

New packages should now appear in menuconfig.

### Step-by-step guide for rahhid

#### Download and extract SDK
```
wget https://downloads.openwrt.org/releases/19.07.3/targets/mvebu/cortexa9/openwrt-sdk-19.07.3-mvebu-cortexa9_gcc-7.5.0_musl_eabi.Linux-x86_64.tar.xz
tar xf openwrt-sdk-19.07.3-mvebu-cortexa9_gcc-7.5.0_musl_eabi.Linux-x86_64.tar.xz
cd openwrt-sdk-19.07.3-mvebu-cortexa9_gcc-7.5.0_musl_eabi.Linux-x86_64/
```

#### Setup feeds and build package
```
cp feeds.conf.default feeds.conf
echo 'src-git burghardt https://github.com/burghardt/openwrt-feed.git' >> feeds.conf
./scripts/feeds update -a
./scripts/feeds install -a -p burghardt
make package/rahhid/compile
```

Binary package is located in directory `bin/packages/arm_cortex-a9_vfpv3-d16/burghardt` and named `rahhid_11812e3f1e0c81b9ab0f9cf8b03177d3b172c4a6-1_arm_cortex-a9_vfpv3-d16.ipk`.
