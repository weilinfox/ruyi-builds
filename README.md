# ruyi-builds

发行版支持范围

| 发行版 | x86\_64 | aarch64 | riscv64 |
| :--: | :--: | :--: | :--: |
| Debian Trixie | x | x | x |
| Ubuntu Jammy | x | x | x |
| Ubuntu Noble | x | x | x |
| Fedora 39 | x | x |  |
| Fedora 40 | x | x | x |
| Fedora 41 | x | x |  |
| openEuler 24.03 | x | x | x |

Archlinux 请使用 AUR 或 Arch Linux CN 社区源

支持 deb/rpm 软件包的其他发行版请参考 [ruyi-bin-builds](https://github.com/weilinfox/ruyi-bin-builds)

## Debian/RedHat 系添加本源

### Debian/Ubuntu

根据发行版类型在 ``/etc/apt/sources.list`` 中添加

+ Debian trixie ``deb [trusted=yes] https://github.com/weilinfox/ruyi-builds/raw/master/debian/ trixie main``
+ Ubuntu jammy ``deb [trusted=yes] https://github.com/weilinfox/ruyi-builds/raw/master/ubuntu/ jammy main``
+ Ubuntu noble ``deb [trusted=yes] https://github.com/weilinfox/ruyi-builds/raw/master/ubuntu/ noble main``

保存后运行

```bash
sudo apt-get update
sudo apt-get install ruyi
```

### Fedora

建立 ``/etc/yum.repos.d/ruyi.repo`` 配置并键入如下内容

```
[ruyi]
name=ruyi
baseurl=https://github.com/weilinfox/ruyi-builds/raw/master/fedora/$releasever/
enabled=1
gpgcheck=0
```

保存后运行

```bash
sudo dnf update
sudo dnf install ruyi
```

## openEuler

当前只支持 openEuler 24.03 LTS

建立 ``/etc/yum.repos.d/ruyi.repo`` 配置并键入如下内容

```
[ruyi]
name=ruyi
baseurl=https://github.com/weilinfox/ruyi-builds/raw/master/openeuler/2403/
enabled=1
gpgcheck=0
```

保存后运行

```bash
sudo dnf update
sudo dnf install ruyi
```

## Archlinux

使用 AUR 安装，经过测试的架构如下

+ aarch64
+ armv7h
+ loong64
+ riscv64
+ x86\_64
+ x86\_64\_v3

```bash
yay -S ruyi
```

使用 Arch Linux CN 社区源安装，支持 x86\_64 和 aarch64 两个架构

在 ``/etc/pacman.conf`` 中添加任意 archlinuxcn 源，这里以山东科技大学开源软件镜像站为例。
在一个镜像同步失败时 pacman 会 fallback 到下一个镜像，可以配置多个镜像作为备份。

```
[archlinuxcn]
Server = https://mirrors.sdust.edu.cn/archlinuxcn/$arch
Server = https://mirror.iscas.ac.cn/archlinuxcn/$arch
```

```bash
sudo pacman -Syuu
sudo pacman -S ruyi
```

