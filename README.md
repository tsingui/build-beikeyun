# build-beikeyun

[![Build Status](https://travis-ci.com/hanwckf/build-beikeyun.svg?branch=master)](https://travis-ci.com/hanwckf/build-beikeyun)
[![release](https://img.shields.io/github/release/hanwckf/build-beikeyun.svg)](https://github.com/hanwckf/build-beikeyun/releases)

### scripts for build beikeyun firmware

- armbian
  - default root password: 1234
- LibreELEC
  - default root password: libreelec
- Lakka
  - default root password: root
- alpine
  - default root password: admin
- archlinuxarm
  - default root password: admin
  - run `pacman-key --init && pacman-key --populate archlinuxarm` to init keyring
- 使用build-beikeyun生成贝壳云固件
- 安装依赖工具
  - apt install mtools u-boot-tools jq html-xml-utils util-linux p7zip-full squashfs-tools bsdtar axel
- 如果要构建alpine和archlinuxarm，还需要安装qemu-user-static和binfmt-support

- 克隆构建脚本
  - git clone https://github.com/hanwckf/build-beikeyun.git && cd build-beikeyun
- 生成固件
  - make build_armbian=y build_libreelec=y build
- 生成的固件在output目录
  - 使用./flash.sh [img_file]向maskrom模式下的贝壳云刷入固件（需要rkdeveloptool）
