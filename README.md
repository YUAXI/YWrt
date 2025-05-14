<h1 align="center">YWrt</h1>



<p align="center">
  <strong>YWrt 是一个为科学上网精心定制的路由系统，基于 ImmortalWrt 二次编译。</strong><br>
  简洁 · 稳定 · 高效
</p>


<p align="center">
  <img src="https://img.shields.io/badge/platform-OpenWrt-informational?style=flat-square" alt="Platform">
  <img src="https://img.shields.io/github/license/YUAXI/YWrt?style=flat-square" alt="License">
  <img src="https://img.shields.io/github/stars/YUAXI/YWrt?style=flat-square" alt="Stars">
</p>


---

## ✨ 项目亮点

- **预装插件**：OpenClash、PassWall、HomeProxy、OpenVpn。
- **特色**：剔除冗余插件，只保留关键组件。

---



### ⚠️tips:

1.[Releases](https://github.com/YUAXI/YWrt/releases)中有编译好的x86镜像文件，如果你也是x86且没有太多需求推荐直接下载。

2.推荐使用Ubuntu、Debain进行编译，本人使用的是Ubuntu-24.04.2-server。

3.国内用户编译前需备好梯子，代理模式最好开全局，否则将有很大概率导致编译失败。



## 🚀 开始编译

### 1. 安装依赖

**Debian/Ubuntu ：**

```bash
sudo apt update -y
sudo apt full-upgrade -y
sudo apt install -y ack antlr3 asciidoc autoconf automake autopoint binutils bison build-essential \
  bzip2 ccache clang cmake cpio curl device-tree-compiler ecj fastjar flex gawk gettext gcc-multilib \
  g++-multilib git gnutls-dev gperf haveged help2man intltool lib32gcc-s1 libc6-dev-i386 libelf-dev \
  libglib2.0-dev libgmp3-dev libltdl-dev libmpc-dev libmpfr-dev libncurses-dev libpython3-dev \
  libreadline-dev libssl-dev libtool libyaml-dev libz-dev lld llvm lrzsz mkisofs msmtp nano \
  ninja-build p7zip p7zip-full patch pkgconf python3 python3-pip python3-ply python3-docutils \
  python3-pyelftools qemu-utils re2c rsync scons squashfs-tools subversion swig texinfo uglifyjs \
  upx-ucl unzip vim wget xmlto xxd zlib1g-dev zstd
```

### 2. 克隆源码

执行 `git clone https://github.com/YUAXI/YWrt.git` 克隆仓库
执行 `cd Ywrt`  进入文件夹
执行 `./scripts/feeds update -a` 获取最新软件包
执行 `./scripts/feeds install -a` 将软件安装到package/feeds/ 目录中
执行 `make menuconfig` 配置固件
执行 `make download -j$(nproc) V=s` 下载所需依赖
执行 `make -j$(nproc) V=s` 开始编译

### 3.获取固件

生成固件存放路径: `bin/targets`

