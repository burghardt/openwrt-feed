# Burghardt's packages feed

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
