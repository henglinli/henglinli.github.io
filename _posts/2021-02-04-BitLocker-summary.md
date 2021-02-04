续https://www.v2ex.com/append/topic/535796

关于TPM PCRs[<sup>[1]</sup>](https://docs.microsoft.com/zh-cn/windows/security/information-protection/tpm/switch-pcr-banks-on-tpm-2-0-devices) [<sup>[2]</sup>](https://ladyitris.wordpress.com/bitlocker-using-tpm/)：
* 配置修改UEFI BIOS后就会触发BitLocker恢复模式，触发的条件就按照PCRs分类的。

目前状态：
* sgx禁用，之前以为BitLocker会用到它。
* DMA内核保护无法开启。因为msinfo显示PCR7设定无法联结，即使在组策略中开启也不行。
* 没有设定BitLoker启动PIN和启动密钥，只有一个加密的C盘。
* 目前用的是自签名的systemd boot（启动项名为Linux Boot Manager）链载（chainload）bootmgfw的方式启动Windows的。
名为Windows Boot Manager的启动项已删除，并没有再遇到的Windows还原Windows Boot Manager启动项的情况（完全搞不懂...)，
甚至Windows启动恢复功能也无法还原。

其他注意事项：
+ 删除了Windows保留分区无法开启BitLocker（我干过...）；开启BitLocker不需要恢复分区，甚至不需要安全启动。
+ 无法开启Bitlocker的一个可能原因是U盘没有取出(PCR2?)，即使在BIOS中关闭了USB设备引导。
+ 插上U盘启动Windows会触发BitLocker恢复模式（我遇到过...)。
+ 由\EFI\Microsoft\Boot\bootmgfw.efi引导变成\EFI\Boot\bootx64.efi也会触发BitLocker恢复模式，即使他们是同一个bootmgfw (PCR4?)。
+ 切换UEFI启动项不会触发BitLocker恢复模式。即如由OpenCore启动到MacOS后，再由bootmgfw启动到Windows时不会触发BitLocker恢复模式。
但是[HaC-Mini](https://github.com/osy/HaC-Mini)默认开启OpenCore启动项保护
[BootProtect ](https://github.com/dortania/OpenCore-Multiboot/blob/master/oc/bootstrap.md#removing-bootstrap-entry-from-bios)，
每次启动将OpenCore移到首位。这种情况如果触发了BitLocker恢复模式，关闭OpenCore启动保护即可。
