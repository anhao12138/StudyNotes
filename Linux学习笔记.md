### Linux 学习笔记
---
UNIX是一个交互式的系统，用于同时处理多个进程和多个用户同时在线，Linux是由UNIX发展而来的,UNIX 是由程序员设计，它的主要服务对象也是程序员。Linux 继承了 UNIX 的设计目标。从智能手机到汽车，超级计算机和家用电器，从家用台式机到企业服务器，Linux 操作系统无处不在
大多数程序员都喜欢让系统尽量简单，优雅并具有一致性。举个例子，从最底层的角度来讲，一个文件应该只是一个字节集合。为了实现顺序存取、随机存取、按键存取、远程存取只能是妨碍你的工作。相同的，如果命令
`ls A `
这句话的意思是只用列出以a开头的所有文件，那么命令
`rm A*`
意思是他会移除所有A开头的文件而不是只删除文件名A*的文件。这个特性也是最小吃惊原则（principle of least surprise）
_最小吃惊原则一般常用于用户界面和软件设计。它的原型是：该功能或者特征应该符合用户的预期，不应该使用户感到惊讶和震惊。_
---
## Linux 系统是一种金字塔模型的系统
如图所示：
![金字塔模型](https://www.hualigs.cn/image/60b4d9daa72bb.jpg)
---
应用程序发起系统调用把参数放在寄存器中(有时候放在栈中)，并发出 trap 系统陷入指令切换用户态至内核态。因为不能直接在 C 中编写 trap 指令，因此 C 提供了一个库，库中的函数对应着系统调用。有些函数是使用汇编编写的，但是能够从 C 中调用。每个函数首先把参数放在合适的位置然后执行系统调用指令。因此如果你想要执行 read 系统调用的话，C 程序会调用 read 函数库来执行。这里顺便提一下，是由 POSIX 指定的库接口而不是系统调用接口。也就是说，POSIX 会告诉一个标准系统应该提供哪些库过程，它们的参数是什么，它们必须做什么以及它们必须返回什么结果。

除了操作系统和系统调用库外，Linux 操作系统还要提供一些标准程序，比如文本编辑器、编译器、文件操作工具等。直接和用户打交道的是上面这些应用程序。因此我们可以说 Linux 具有三种不同的接口：系统调用接口、库函数接口和应用程序接口

## Linux组成部分
事实上，Linux操做系统可以由下面几部分构成
---
+ _引导程序（Bootloader）_:引导程序是管理计算机启动过程的软件，对于大多数用户而言，只是弹出一个屏幕，但是其实内部操作做了很多事情
+ _内核（kernel）_:内核是操作系统的核心，负责管理CPU，内存和外围设备等。
+ _初始化系统（Init System）_ :这是一个引导用户空间并且负责控制守护程序的子程序。以但引导加载程序移交了畜视引导，他就是用于管理引导过程的初始化系统。
+ _后台进程（Daemon）_： 后台进程就是在后台运行的程序，比如打印，声音，调度等等，他们可以在引导过程中启动，也可以在登录以后启动。
+ _图形服务器（Graphical server）_：这是在监视器上显示图形的子程序。通常将其成为X服务器或者X 。
+ _桌面环境_:这是用户与之交际交互的部分，有很多桌面环境可供旋转，每个桌面环境都包含内置应用程序，比如文件管理器，web浏览器，游戏等等。
+ _应用程序（Applications）_ ：桌面环境不提供完整的应用程序，就像Windows和macOS一样，Linux提供了成千上万个可以找到并且安装的高质量软件
  
## Shell
尽管 Linux 应用程序提供了 GUI ，但是大部分程序员仍偏好于使用命令行(command-line interface)，称为shell。用户通常在 GUI 中启动一个 shell 窗口然后就在 shell 窗口下进行工作
shell 命令行使用速度快、功能更强大、而且易于扩展、并且不会带来肢体重复性劳损(RSI)。