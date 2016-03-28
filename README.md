# openwrt-minidlna with dsd support

This is a custom version of [minidlna][1] with dsd support.

base on [minidlna][1] 1.1.5

## How to build

prepare for OpenWrt SDK

```bash
# take mvebu(linksys wrt1900ac) for example
wget https://downloads.openwrt.org/chaos_calmer/15.05/mvebu/generic/OpenWrt-SDK-15.05-mvebu_gcc-4.8-linaro_uClibc-0.9.33.2_eabi.Linux-x86_64.tar.bz2
tar -xf OpenWrt-SDK-15.05-mvebu_gcc-4.8-linaro_uClibc-0.9.33.2_eabi.Linux-x86_64.tar.bz2
cd OpenWrt-SDK-15.05-mvebu_gcc-4.8-linaro_uClibc-0.9.33.2_eabi.Linux-x86_64
```

add feeds for dependencies

```
./scripts/feeds update -a
./scripts/feeds install libexif libjpeg libsqlite3 libffmpeg libid3tag libflac libvorbis 
```

clone this repository into package/minidlna

```
git clone https://github.com/harmy/openwrt-minidlna.git package/minidlna
```

Compile

```
# -j8可根据你的VM的CPU数量调整，有助于加快编译速度
make package/minidlna/compile V=99 -j8
```

## credit

[jmaggard][2]

[takeshich][3]



# 带有dsd支持的openwrt-minidlna

这是[minidlna][1]在openwrt上的一个增强版本，主要增加dsd文件支持

基于[minidlna][1] 1.1.5

## 如何编译

先准备OpenWrt SDK

```bash
# 以mvebu(linksys wrt1900ac)为例
wget https://downloads.openwrt.org/chaos_calmer/15.05/mvebu/generic/OpenWrt-SDK-15.05-mvebu_gcc-4.8-linaro_uClibc-0.9.33.2_eabi.Linux-x86_64.tar.bz2
tar -xf OpenWrt-SDK-15.05-mvebu_gcc-4.8-linaro_uClibc-0.9.33.2_eabi.Linux-x86_64.tar.bz2
cd OpenWrt-SDK-15.05-mvebu_gcc-4.8-linaro_uClibc-0.9.33.2_eabi.Linux-x86_64
```

接下来添加依赖库的feed

```
./scripts/feeds update -a
./scripts/feeds install libexif libjpeg libsqlite3 libffmpeg libid3tag libflac libvorbis 
```

克隆本项目到package目录下

```
git clone https://github.com/harmy/openwrt-minidlna.git package/minidlna
```

开始编译

```
# -j8可根据你的VM的CPU数量调整，有助于加快编译速度
make package/minidlna/compile V=99 -j8
```

## 感谢

[jmaggard][2]

[takeshich][3]



[1]: https://sourceforge.net/projects/minidlna/
[2]: https://sourceforge.net/p/minidlna/git/ci/master/tree/
[3]: https://sourceforge.net/u/takeshich/minidlna/ci/master/tree/
