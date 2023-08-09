习惯了Linux的同学在使用命令行操作文件时，直接右键点击在终端中打开就可以了，用起来十分方便快捷。回到Windows系统中，在指定文件夹中打开cmd命令行需要好几步步骤。这里我们可以直接设置在Windows中右键打开cmd命令行，具体操作如下。

1. Win+r 打开运行窗口，输入 "regedit"进入到系统注册表，服务。

<img src="https://pic1.zhimg.com/80/v2-33748ebcc8f7d9dfd8a1e847aefd5ba0_1440w.webp" title="" alt="" width="442">

2. 打开路径"**HKEY_CLASSES_ROOT** --> **Directory**-->**Background**-->**shell**"

<img src="https://pic3.zhimg.com/80/v2-6bbceaf96435063228be846e41b553e2_1440w.webp" title="" alt="" width="255">

<img src="https://pic1.zhimg.com/80/v2-bddf010d46c9638ee83000a3ca701538_1440w.webp" title="" alt="" width="288">

3. 在shell文件夹下右键新建"项"，就是新建一个文件夹命名为"OpenCMD"，这个名称可以随便取。同时在OpenCMD下面再新建一个项命名为 command的文件夹，如下。

<img src="https://pic3.zhimg.com/80/v2-6e02c5c26928e375c3de35214399ab9e_1440w.webp" title="" alt="" width="308">

4.在OpenCMD文件夹中修改默认，数据数据为“在此处打开cmd命令窗口”

<img src="file:///C:/Users/54690/AppData/Roaming/marktext/images/2023-08-09-20-37-45-image.png" title="" alt="" width="730">

然后，右键新建“字符串值”，数值名称修改为“Icon”，数值数据改为“cmd.exe”

<img src="https://pic2.zhimg.com/80/v2-d0f926a03a55b8f62c775d2f1d4171cd_1440w.webp" title="" alt="" width="577">

6. 最后修改刚才新建文件夹command里面的数据属性

将默认的数值数据修改为 cmd.exe，最后确定就OK了。

<img src="file:///C:/Users/54690/AppData/Roaming/marktext/images/2023-08-09-20-29-16-image.png" title="" alt="" width="770">

7. 最后效果如下：

![](C:\Users\54690\AppData\Roaming\marktext\images\2023-08-09-20-28-45-image.png)
