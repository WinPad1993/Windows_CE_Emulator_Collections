<div align="center">
  
  # Windows CE Emulator Collections
  基于 Windows PE 的 Windows CE Emulator 合集<br /><br />
  English readme is here:https://github.com/WinPad1993/Windows_CE_Emulator_Collections/blob/main/README_EN-US.md
  
</div>


## 什么是CE Emulator Collections<br />
微软公司开发Windows CE 1.0至Windows CE 3.0时，为便于开发者在自己的电脑上直接测试他们所编写的WinCE Apps，在部分Windows CE（或CE内核的操作系统，如Windows Pocket PC 2000等）的SDK中附带了可以在Windows NT上运行的Shell模拟器，然而随着Windows NT family的不断开发，Windows对这些模拟器兼容性也会越来越差（如在Windows 11 中，已无法启动这些版本SDK的安装程序），甚至完全失去了对模拟器的支持（如Windows Pocket PC 2000 模拟器）。于是为便于这些模拟器的运行，借助Windows PE，制作了这个合集。<br />

## 如何使用
由于本镜像基于Windows PE（Windows 2000,FLP内核），故可以直接将其挂载到虚拟机中，选择菜单会在开机完成后自动启动，只需根据菜单上的提示输入数字，以启动你想要的模拟器。
**注意：该镜像要求虚拟机内存达到700MB，并且不需要硬盘镜像！** <br />
### CEEC 配置须知 – 成功模拟环境配置建议

**由 HAWEEN CHEN 撰写**  
*2026年4月9日*

首先，非常感谢 **ONEW STUDIO** 提供的 **CEEC（Windows CE 模拟器合集）** 项目。对于在现代 PC 硬件上探索与保留 Windows CE 环境而言，这是一个非常出色的创举。

在近期的部署过程中，我遇到了一些配置上的障碍，并已自行尝试解决。特此留下这条评论记录相关发现，希望能帮助其他使用者避免同样的问题。

#### 🔧 配置提示与故障排查

**1. 虚拟机平台兼容性：建议使用 VirtualBox 而非 VMware**
由于 CEEC 预安装环境（PE）阶段在显示驱动与鼠标集成方面存在特定问题，**不建议使用 VMware Workstation/Player** 来部署本项目。我在测试中遇到了明显的鼠标指针偏移及图形闪烁现象。将虚拟机平台更换为 **Oracle VirtualBox** 即可彻底解决上述输入与显示问题。

**2. 虚拟光驱控制器设置（关键项）**
此设置是导致 *"Path Not Found"（找不到路径）* 错误的最常见原因。为 CEEC 配置虚拟机设置时：

- ❌ **切勿**使用 **ICH6**、**SATA** 或 **AHCI** 控制器来挂载虚拟光驱。
- ✅ **必须**使用 **IDE** 控制器来连接光驱设备。

若未能将光驱设置为 IDE 模式，模拟器将**无法**定位系统路径，从而导致启动进程立即中断。

**3. 引导程序盘符限制（需挂载至 D:\ 盘符）**
由于当前引导程序版本（0.4.5 或更低版本）存在硬编码限制，CEEC 环境要求其内容存储卷（无论是 RAMDisk 还是 ISO 镜像文件）必须挂载到 **`D:\`** 盘符。若该存储介质被分配了其他盘符或未能成功连接，引导程序将无法找到所需组件，模拟过程将无法启动。

- **如需稳定运行体验**：强烈建议在会话期间**始终不要卸载或弹出**虚拟光驱。
- **仅作快速体验测试**：作为备选方案，你*可以*尝试在 **Windows 2000 或 Windows XP** 虚拟机环境甚至物理机上运行旧版 CE（1.0 - 2.0）及部分老旧模拟器二进制文件，且**无需安装任何 SDK 及 VB2005 组件**。但请注意，该替代方案的运行体验及硬件兼容性远不如 CEEC 原生环境。

---

CEEC 是深入探索 Windows CE 历史的宝贵资源。尽管 PE 驱动环境方面仍存在一些细微问题，但我非常期待该项目的后续发展。再接再厉！

**HAWEEN CHEN**


## 集成列表
绿色:已集成且能够较为正常地工作。<br />
蓝色:已集成但具有问题。<br />
黄色:因技术原因未集成。<br />
红色:因资源缺失原因未集成。<br />
黑色：很有可能永远不会加入。<br />
<br />
![111-1](https://github.com/user-attachments/assets/edbebe4b-7c06-4902-9161-f9b9f92320f9)
<br />


## 特别鸣谢

1.ONEW Studio的全体成员<br />

<table>
  <tr>
    <td align="center"><a href="https://space.bilibili.com/484165196"><img src="https://github.com/Inter1006/Extensions/blob/main/1720663857759dcbe7c89c6455282b29bc8695211ad7924a0.jpg" width="150px;" alt=""/><br /><sub><b>351<br />351Workshop</b></sub></a><br /></td>
    <td align="center"><a href="https://space.bilibili.com/1756824708"><img src="https://github.com/Inter1006/PenPointOS_Vbox/blob/Readme_Files/b_fa517952f054ca8c99a234cc1b50b50b.jpg" width="150px;" alt=""/><br /><sub><b>Inter1006<br />INTER_INIT</b></sub></a><br /></td>
    <td align="center"><a href="https://space.bilibili.com/410046866"><img src="https://github.com/Inter1006/Extensions/blob/main/1720663903084330ee6855a3795b453f2ab6ded4863c9b08a.jpg" width="150px;" alt=""/><br /><sub><b>GoldApple<br />不务正业的金苹果</b></sub></a><br /></td>
    <td align="center"><a href="https://space.bilibili.com/648710692"><img src="https://avatars.githubusercontent.com/u/109840619?s=400&u=8c905a3d85482006220ae0074e8c36e3fc5729eb&v=4" width="150px;" alt=""/><br /><sub><b>WinPad(御坂)<br />MisakaMikoto1122</b></sub></a><br /></td>
    <td align="center"><a href="https://space.bilibili.com/2057331843"><img src="https://github.com/Inter1006/Extensions/blob/main/17206639278647b179c13f807cbc2bf27b899725d34fc5c79.jpg" width="150px;" alt=""/><br /><sub><b>DZY<br />DZY20070614</b></sub></a><br /></td>
    <td align="center"><a href="https://space.bilibili.com/437201853"><img src="https://github.com/Inter1006/Extensions/blob/main/1720663947047a3c221d7c72c685e35b27b3fe6d41b6f8f93.jpg" width="150px;" alt=""/><br /><sub><b>Zesa<br />LinuxMEMZ</b></sub></a><br /></td>
  </tr>
  
</table>
<br />
ONEW Studio QQ交流群：981893945 欢迎来玩<br /><br />

## 其他

所有的Windows CE Emulator均从微软分发的SDK中提取。

## 友情链接

WindowsNT351的CE Collections：https://github.com/WindowsNT351/CE-Collections <br />
Inter的Penpoint模拟器：https://github.com/Inter1006/PenPointOS_Vbox/tree/main <br />
Axium. 钰的樱之谷MC服务器：https://www.sakuravalley.xyz <br />




