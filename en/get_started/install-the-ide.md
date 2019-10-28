# Download

Go to the official website http://www.gowinsemi.com.cn/faq.aspx, you can see the software list below, select the version of the system suitable for the computer to download.

![1-1](../../assets/gowin_down.png)

# Installation

**Windows** User:

Double-click the downloaded exe installation file, select the installation language, installation location, click the next step to complete the installation.

Be sure to install the driver that prompts you to install when you complete the installation.

![2-1](../../assets/gowin_install.png)

Check the installation driver and click Finish, the driver will be installed.

**Linux** User:

TODO

# license

Gao Yunyun source software requires a license to use, the current software license is provided free of charge, you can apply in [official website] (http://www.gowinsemi.com.cn/faq_view.aspx)

However, the way to apply on the official website is cumbersome. In order to facilitate development, you can use Gaoyun software through the sipeed license server.

There are currently two ways to license.

**The first type: use the stand-alone version of the licence (requires modification of the mac)**

This method needs to modify the MAC address of the network card through the registry.

Press `ctrl+r` and type `regedit` in the pop-up window to open the registry.

First find this path under the registry `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Class\{4d36e972-e325-11ce-bfc1-08002be10318}`

Under this path, there are many sub-paths, starting from 0000, click to view details.

![3-1](../../assets/lic_file_1.png)

See `DriverDesc` which says the name of the network adapter.

In the win10 `network and Intel` settings, there is a `change adapter` option, you can see your own network adapter on the machine, just click one of the adapters.

![3-2](../../assets/lic_file_2.png)

Back in the registry, we need to add `NetworkAddress` like the red box in Figure 3-1 and change the value to `94C691A91EB6`

Add items can be in the blank space `Right-> New -> String`, as shown in the figure

![3-3](../../assets/lic_file_3.png)

Finally, type `ipconfig /all` in the system command line. You can see whether the modification takes effect in the command output.

![3-4](../../assets/lic_file_4.png)

It should be noted here that in the newer version of win10, it seems that the physical network card cannot be modified by modifying the registry. It may be necessary to add a virtual network card to modify it. The modified virtual network card of vmware is modified here.

Here you need to download two offline licences, [gowin](../../assets/files/gowin.lic) and [synplifypro](../../assets/files/gowin_Synplifypro.lic)

When you open the High Cloud IDE, in the license management that pops up, select your local gowin.lic path.

![3-5](../../assets/lic_file_5.png)

Then you need to add the path of the license of synplifypro to the system variable. The following is a brief introduction to an add method. In ` `The second: use the sipeed license server networking activation`, there is a more detailed introduction.

**Windows** User press win+r on the keyboard, enter `cmd` in the pop-up window, click OK to pop up the black command line window, enter the following command, `path_to_the_file` is your `gowin_Synplifypro.lic Path of `.

```
setx LM_LICENSE_FILE path_to_the_file
```

**Second: Network activation with license server using sipeed**

This method is simple to configure, but you can't use the software without a network.

After downloading the software, the software will prompt you for a licence. Fill in the server address `45.33.107.56` in the pop-up box, IDE port: 10559.

![3-6](../../assets/lic_remote_1.png)

The activation of the synopsys advanced function requires adding the environment variable `LM_LICENSE_FILE=27020@45.33.107.56` to the system.

**Windows** User presses win+r on the keyboard, enter `cmd` in the pop-up window, click OK to pop up the black command line window, enter the following command.

```
setx LM_LICENSE_FILE 27020@45.33.107.56
```

Windows can be added in addition to the command line. You can also add it by right-clicking Computer->Properties->Environment Variables and then adding it as shown below.

![3-7](../../assets/lic_remote_2.png)

**Linux** users need to add in `~/.bashrc`

```
Export LM_LICENSE_FILE 27020@45.33.107.56
```

After entering the IDE, click on `Synplify Pro` in Tools.

![3-8](../../assets/lic_remote_3.png)

Then the interface will pop up as shown below. At this time, you need to wait for a short time. After the license is initialized, you can use it.

![3-9](../../assets/lic_remote_4.png)

# Instructions

Refer to the official documentation [Gowin Source Software User Guide] (http://cdn.gowinsemi.com.cn/SUG100-1.8_Gowin%E4%BA%91%E6%BA%90%E8%BD%AF%E4%BB%B6%E7%94%A8%E6%88%B7%E6%8C%87%E5%8D%97.pdf), Chapter 5 Cloud Source Software Usage.

# Reference document

+ [Gowin Software Introduction and Installation](http://cdn.gowinsemi.com.cn/%E9%AB%98%E4%BA%91%E8%BD%AF%E4%BB%B6%E7%AE%80%E4%BB%8B%E5%92%8C%E5%AE%89%E8%A3%85.pdf)

