# ebf_6ull_uboot

## 开发环境

**ubuntu18.04**

**安装独立编译工具链**

arm-none-eabi-gcc：v6.3.1

```bash
 sudo apt-get install gcc-arm-none-eabi
```

**测试arm-none-eabi-gcc安装是否成功**

```bash
arm-none-eabi-gcc -v
```

**如果你的系统是64位的**

如果出现`No such file or directory`问题，可以用以下命令解决
```bash
sudo apt-get install lib32ncurses5 lib32tinfo5 libc6-i386
```
---

## 编译过程

**清除编译信息**

```bash
make ARCH=arm clean
```

## 设置配置选项

选择一个与野火开发板版本一致的配置即可!!

> 注意：SD卡版本是适用于SD卡的uboot

**nand版本**

```bash
make ARCH=arm mx6ull_14x14_evk_nand_defconfig
```

**#emmc版本**

```bash
make ARCH=arm mx6ull_14x14_evk_emmc_defconfig
```

**sd卡版本**

```bash
make ARCH=arm mx6ull_14x14_evk_defconfig
```

**开始编译**
```bash
make -j4 ARCH=arm CROSS_COMPILE=arm-none-eabi-
```

## 编译生成的uboot输出路径

生成`u-boot.imx`文件

```bash
ebf_6ull_uboot/u-boot.imx
```

---

## 其他信息

**内核版本**

来源官方 `imx_v2016.03_4.1.15_2.0.0_ga` 分支

uboot官方源码：[http://git.freescale.com/git/cgit.cgi/imx/uboot-imx.git/](http://git.freescale.com/git/cgit.cgi/imx/uboot-imx.git/)

```bash
# Clone 
git://git.freescale.com/imx/uboot-imx.git

http://git.freescale.com/git/cgit.cgi/imx/uboot-imx.git
```










