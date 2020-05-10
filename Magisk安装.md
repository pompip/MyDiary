# 如何安装 Magisk

## TWRP中刷入

    在电脑上配置好 adb 环境 并解开 Bootloader 锁后，如果你的设备有来自 TWRP 的官方支持，  
    只需在打开 USB 调试后将手机与电脑相连，然后打开电脑端的命令行窗口：

1. 执行 adb reboot bootloader 进入 Bootloader 界面
2. 执行 `fastboot boot TWRP.img`进入临时 TWRP 
3. 或者刷入永久recovery `fastboot flash recovery twrp_sagit.img`
4. 在 TWRP 中刷入你下载的 Magisk.zip 安装包

## 没有官方 TWRP 支持的设备

1. 从你的刷机包中提取当前固件的 boot.img 文件，将它传入到安装了 Magisk Manager 的手机中
2. 进入 Magisk Manager —— 安装（install）—— install —— 修补 boot 镜像文件
3. 然后选择传入的 boot.img 文件进行生成，并将生成后的 Patchedboot.img 传输到电脑上。
4. 打开命令行窗口执行 adb reboot bootloader 进入 Bootloader 界面
5. 执行 fastboot flash boot Patchedboot.img 来加载生成后的 boot 分区文件获取临时 root
6. (这个步骤可能不需要)此时进入系统，你会发现你已经成功安装了 Magisk（如果显示没有安装则为获取失败，请检查操作过程重新尝试），但这还不够，我们还得进入 Magisk Manager，选择安装（install）——install——Direct Install（直接安装）才能将临时 root 转换为永久 root。

### 可以从手机中，提取boot.img

输入临时twrp，启动fastboot reboot recovery，然后用adb连接执行

```shell
adb shell
su
cd /dev/block/platform/msm_sdcc.1/by-name
ls -l boot
```

    boot 是个系统符号软链接，上面命令的执行结果就是boot分区所在位置，我的是/dev/block/mmcblk0p19

```shell
dd if=/dev/block/mmcblk0p19 of=/sdcard/boot.img
```

这样就放到了sdcard，使用adb pull拿出来即可。

## 卸载 Magisk

> 最为彻底的方式就是在 Magisk Manager 中点击「卸载」、「完全卸载」，应用会自动下载刷完 uninstall.zip 卸载包、自动卸载它自己、自动重启。如果你无法进入系统，在 TWRP 中手动刷入 uninstall.zip 卸载包即可.

[原文](https://sspai.com/post/53043)