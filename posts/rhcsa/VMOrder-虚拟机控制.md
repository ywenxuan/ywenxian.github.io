# 虚拟机控制

## 相关介绍：

**RHCE8中有基于KVM的虚拟机（VMNAME）：**

​     **classroom、bastion、workstation、servera、serverb。**

命令行中对**rht-vmctl**的使用介绍：

```
Usage: rht-vmctl [-y|--yes] VMCMD VMNAME [DATETIME]
       rht-vmctl [-i|--inquire] VMCMD VMNAME [DATETIME]
       rht-vmctl -h|--help
where VMCMD is one of:
    view       查看控制                                                 台- launches console viewer of VMNAME
    start      开机- obtain and start up VMNAME
    stop       关机- stop a running VMNAME
    restart    重启- if running, stop then start VMNAME
    poweroff   强制断电- if running, force stop VMNAME
    reset      重置- poweroff, return to saved or original state, start VMNAME
    save       - stop, save image, start VMNAME (to DATETIME)
    restore    - poweroff, restore to save (to DATETIME), start VMNAME
    listsaves  - list the saves of VMNAME
    status     查看状态 - display libvirt status of VMNAME                         
    get        - if not here, obtain VMNAME from server
    remove     - remove VMNAME from system
    fullreset  完全重置（重新下载并安装） - poweroff, reobtain from server, start VMNAME (bad save/image)

  -i|--inquire 询问 - confirm each VMNAME first
  -y|--yes     不询问 - confirm nothing, just do it

  VMNAME of "all" processes all VMs available in the course

```

**rht-vmctl VMCMD VMNAME:**

| 简单介绍： |                      |
| :--------: | :------------------- |
|    rht     | RedHat Train         |
|   vmctl    | VMware Control       |
|   VMCMD    | 命令                 |
|   VMNAME   | 虚拟机名称           |
|   -i/-y    | 可选（是否询问执行） |
|            |                      |

## 相关命令：

| rht-vmctl status VMNAME           | 查看VMNAME状态                                               |
| --------------------------------- | ------------------------------------------------------------ |
| rht-vmctl status all              | 查看除classroom外其他虚拟机状态 / 查看所有**（不包括classroom）** |
| rht-vmctl status classroom        | 查看classroom虚拟机状态    【classroom比较特殊，需要单独查看】 |
| **rht-vmctl start VMNAME**        | **开启VMNAME（先开启classroom）**                            |
| rht-vmctl start classroom         | 开启classroom                                                |
| rht-vmctl start all               | 开启所有（除classroom外）                                    |
| **rht-vmview view VMNAME**        | **查看VMNAME的控制窗口**                                     |
| rht-vmview view servera           | 查看servera的控制窗口                                        |
| **rht-vmctl stop VMNAME**         | **关闭VMNAME**                                               |
| rht-vmctl stop servera            | 关闭servera（状态由RUNNING变为DEFINED，无法查看控制窗口）    |
| **rht-vmctl poweroff VMNAME**     | **强制断电VMNAME**                                           |
| rht-vmctl poweroff servera        | 强制断电servera（默认询问）                                  |
| rht-vmctl poweroff all            | 强制断电所有虚拟机                                           |
| rht-vmctl poweroff servera **-q** | 强制断电servera，**不询问**                                  |
| rht-vmctl poweroff servera **-y** | 强制断电servera，**不询问**                                  |
| rht-vmctl poweroff all **-i**     | 强制断电所有虚拟机，**逐条询问**                             |
| **rht-vmctl reset VMNAME**        | 重置虚拟机(硬盘中文件重新安装)                               |
| rht-vmctl reset servera           | 重置servera                                                  |
| **rht-vmctl fullreset VMNAME**    | 完全重置（重新下载安装）                                     |
| 图形化界面：virt-manager          |                                                              |

# 