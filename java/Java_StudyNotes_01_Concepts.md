# Java 学习笔记——导论

### 计算机基础

#### 人机交互

人如何操作计算机的一门学问

现在的电脑的操作方式叫做图形化界面操作系统，也就是现在的文件图标点击即可进入的操作方法，在这种操作系统出现之前，始终都是使用我们之前见到的全黑命令窗口来进行各类操作，那种操作方式就叫做命令行方式。

我们之所以在各类影视作品中看到很多计算机工作者明明有图形化界面却还是使用命令行操作的主要原因就是：相比于命令行操作，图形化界面操作系统有两大缺席：消耗内存，运行速度慢，这会导致编译工作效率的降低

在Windows中也保留了命令行系统，即 CMD操作

#### CMD

打开CMD: Win + R   输入  cmd 确认，弹出的界面就是CMD界面。

一些CMD的常见命令：

``` CMD
盘符名称 + 冒号： “盘符切换”
E:回车，切换到E盘

dir：“查看当前路径下的内容（单级）”

cd ：“进入单级目录”

cd 目录一\目录二\... ：“进入多级目录”

cd ..："回退"

cd \:“直接回车到该盘的根目录”

cls：“清屏”

Exit：“退出”
```

但是有一个问题，例如qq.exe是一个经常需要使用的一个文件，但是每次使用都需要多次进入各级文件，非常麻烦。

这个问题是可以解决的，我们首先将这个这个文件的路径直接记录下来，在随后的使用就可以直接调用这个路径。例如在c:>直接寻找qq.exe是找不到的，但是在c的子目录下无法找到之后，系统会在你“储存”的路径中寻找。这个时候，我们将被储存的qq.exe称之为全局环境变量。

配置全局Path环境变量：

打开此电脑文件夹，右键属性，在弹出窗口中点击”高级系统设置“，跳转的窗口中会有“环境变量“选项。（Win11 中操作不同，建议直接在设置里面搜索”环境变量“就行）配置环境变量时会有两种选项，用户变量和系统变量，用户变量是只针对用户的，如果一个电脑中有多个用户则不共享。系统变量则是在这个电脑范围都生效。

因此，我们将需要记录的路径记录在系统变量的”Path“中。如图：

<img src="../resourse/image/屏幕截图 2023-07-31 173045.png" style="zoom:33%;" />

上述就是系统变量中的”Path“,在输入后，系统会先在系统变量中寻找你试图运行的程序，然后再在当前路径中寻找。请注意：系统变量路径的优先级大于当前路径，例如在当前路径和系统路径下有一个同名文件，输入该名称后会优先运行系统路径下的文件。而系统文件之间遵循从上到下运行的顺序，越上面优先级越高。（**系统路径（上）>系统路径（下）>当前路径**）

小结：CMD是一种命令行系统，牺牲可读性换取高效率。如果想要在任何位置都打开一个文件，就把他设置在系统变量中。



### Java 导论：

#### java是什么

java 是一种计算机语言。在目前，Java是国际市场上市场占有率最高，最热门的计算机语言。

#### Java 学习的方法和导览

Java在学习初期不应过分追求Java语言的深度而应该首先追求广度。先将Java实际运用起来再不断加深。

Java在入门阶段可能会接触的内容;

1. Java基础语法
2. 面向对象（核心）
3. API
4. 字符串
5. 集合
6. 拼图游戏（综合实践）

#### 如何理解”编译“

Java在操作系统中是无法直接运行的，因为操作系统本身并不能直接理解Java语言的含义。因此要让操作系统理解Java需要一个翻译的过程，这个翻译的过程就是编译。也就是翻译文件。所以我们可以看到，运行文件并不是在开发工具中的.c/.java之类的文件，而是一个可运行文件（例如.exe），这个.exe文件就是编译器翻译好之后组成的，给电脑看的文件（Java是生成字节码文件（.class文件），然后在java虚拟机（JVM）上运行）

更加专业的说，"编译"是指将一种高级编程语言（比如Java）编写的源代码转换成可执行的机器语言代码的过程。编译器是一种软件工具，它负责将源代码翻译成计算机能够理解和执行的指令集。编译过程包括词法分析、语法分析、语义分析、优化和代码生成等步骤，最终生成可执行文件或库。编译器的主要目标是将高级语言代码转化为机器语言，以便计算机可以直接执行。这种转换过程通常在开发过程中的预处理阶段或者在运行程序之前进行

因此运行代码是必须要使用编译器（Compiler），常见的有GNU Compiler Collection。IDEA一类的开发工具本身并不是一个编译器，但这些开发工具都整合了对应的编译器

在Java官网上安装的的JDK本质上就是一个Java开发工具包（Java Development Kit，JDK）。JDK是Java编程语言的软件开发工具，它包含了Java编译器（javac）和其他必要的工具和库。

没有开发软件的辅助的情况下，我们需要使用java.exe和javac.exe两个文件来运行Java文件，具体命令为： 路径>

javac Helloworld.java    生成Helloworld.class文件。  路径>java helloworld  在命令行中运行该程序。



#### ”Hello Wrold！“

我们现在可以在java中尝试第一个代码：

```java
poblic class hellowrold{
    public static void main (String[] args){
        System.out.println("Hello World!");
    }
}
效果：在工作台输出Hello World!
```

尽管非常简陋，但是我们已经可以看到 Java语言的一部分风格，Java是一门较为严谨的语言，但又没有cpp那样过于繁杂的安全性保证，较为均衡，难度适中

#### Java 常见问题

bug,评价为没出过bug不长记性

#### 环境变量

我们在上述   <u>计算机基础-CMD</u> 中记录过Path环境变量的配置，而  <u>如何理解”编译“</u> 章节也有 路径>

javac Helloworld.java 这样的操作，这就说明：javac也是一个路径被记录在全局环境变量的文件。

计算机基础-CMD 的图片中我们也可以清晰的看到这一点。也就是那个javapath/路径，而java和javac都在javapath路径下

这个环境变量是JDK自动设置的，但我们也可以手动配置（不推荐）。

Java帮助我们配置的仅包含了4个文件：java  javac  javaw  jshell

#### Notepad ++

就是一个高级记事本，会有行号，关键词高亮显示等功能，适用于各种语言的编程，但说得好我选择IDEA

#### Java 发展历史（选）

Java是在1991年由SUN公司的James Gosling（Java之父）及其团队所研发的一种编程语言，第一个版本耗时18个月，最开始命名为Oak（一种橡树）。Java现在广泛应用于各种大型互联网应用，其设计的最初动机主要是平台独立（即体系结构中立）语言的需要，可以嵌入到各种消费类电子设备（家用电器等），但市场反应不佳。

随着1990年代互联网的发展，SUN公司看到了Oak在互联网上的应用场景，在1995年更名为Java（印度尼西亚爪哇岛的英文名称，因盛产咖啡而闻名），随着互联网的崛起，Java逐渐称为重要的Web应用开发语言。Java的发展可以主要看JavaWeb的发展，Java也见证了互联网的发展过程。

发展至今，Java不仅是一门编程语言，还是一个由一系列计算机软件和规范组成的技术体系，Java 是几乎所有类型的网络应用程序的基础，也是开发和提供嵌入式和移动应用程序、游戏、基于 Web 的内容和企业软件的全球标准。

从笔记本电脑到数据中心，从游戏控制台到科学超级计算机，从手机到互联网，Java 无处不在！

- 97% 的企业桌面运行 Java
- 美国有 89% 的桌面（或计算机）运行 Java
- 全球有 900 万 Java 开发人员
- 开发人员的头号选择
- 排名第一的部署平台
- 有 30 亿部移动电话运行 Java
- 100% 的蓝光盘播放器附带了 Java
- 有 50 亿张 Java 卡在使用
- 1.25 亿台 TV 设备运行 Java
- 前 5 个原始设备制造商均提供了 Java ME

数据来源：[https://www.java.com/zh_CN/about/](https://link.zhihu.com/?target=https%3A//www.java.com/zh_CN/about/) 

说到Java自然离不开JDK、JVM、JRE，三者有什么关系。

- JDK（Java Development Kit）Java开发工具包，包含Java语言、Java虚拟机、Java类库，是支持Java程序开发的最小环境。
- JVM（Java Virtual Machine）Java虚拟机，运行于各种操作系统Linux，Windows，Solaris等之上，执行编译好的Java字节码class文件。
- JRE（Java Runtime Environment）Java运行时环境，包含JavaSE中核心类库API和Java虚拟机，简单理解为JVM+核心类库API。



#### Java 的作用

Java的应用非常广，Java有三大平台

1. Java SE 

	Java语言的标准版，应用于桌面应用的开发，是其他两个版本的基础。（所谓的桌面应用意为：用户只要打开程序，程序的界面就会让用户在最短的时间内找到他们所需要的功能，同时主动带领用户完成他们的工作并得到最好的体验），例如，我们Windows中自带的计算器就是一个简单的桌面应用

	但是Java 在这个领域没有优势，这个领域优势最大的语言是c 和 cpp。Java 在这个领域属于”可以做，但是不适合“的一个语言。如果使用Java，会导致播放一些长动画时产生卡顿。

	但是我们还是要写Java SE,因为这是另外两个版本的基础，我们要在Java SE 中学习Java的基本思想，为以后的Java EE开发打基础

2. Java ME

	java 语言的小型版，用于嵌入式电子设备或者移动设备，但现在已经几乎退出历史舞台

3. Java EE

	Java语言的企业版，用于web方向的网站开发，在这个领域是当之无愧的第一。是一个安全的软件，漏洞少，安全性非常高。



Java的应用方向:

1. 桌面应用开发，如各种税务管理软件，IDEA，Pycharm等等
2. 企业级应用开发，如微服务，springcloud。这个领域需要高并发的特性，企业级别的访问量只有java EE和golang可以承担(golang的并发处理更强，但还没有被广泛运用)
3. 移动应用开发，如鸿蒙，Android，医疗设备。
4. 科学计算，由于Java本身严谨安全的特性，Java也可以用于构建 matlab一类的科学计算软件，数学的建模一类就需要matlab 的协助。
5. 大数据开发,如hadoop。
6. 游戏开发，比如minecrafe-java就是用java 开发的

总之，Java总是设计的生活的各个方面

#### Java的流行原因

一个语言的流行程度一般由四个方面决定：用户量，适用面，与时俱进，自身特点。在这四个方面，Java都有一定的优势。

在用户量上，Java可以说是最多人使用的编程语言；适用面也相当的广。在此基础上，java还基本保持着半年一更新的频率，始终保持着旺盛的生命力。

java也有着其独有的，受欢迎的特点；

1. 面向对象： 简单来说，Java的面向对象就是说java可以根据你的要求（一般是一个模板），创建一个符合要求的对象。
2. 安全性：Java代码非常严谨，写出来的代码漏洞少，不会出现太多恶性bug
3. 多线程：简单理解就是可以顺利的在同一时间进行多个线程的操作
4. 简单应用：逻辑严谨，易于应用
5. 开源：在下载java后，Java会直接开放源代码，这让全世界的用户都可以维护java,让java 成为一个可以不断自发修复的语言
6. 跨平台： Java在各种操作系统上都可以运行，可以”一次编译，到处运行“，可以大大节约成本

#### 高级语言的编译运行方式：（待补充）

高级语言的编译运行方式的是相通的，分为编程，编译，运行三个大步骤

1. 程序员写好.java/.c/.py的代码文件
2. 编译器将.java等进行翻译，翻译成二进制语言供机器运行
3. 让机器执行编译后的指令

在翻译这个部分，不同的设备，不同的系统可能会在机器语言理解的方面有着问题，因此他们需要的“翻译文件“就不相同。例如c语言，.c文件在编译时会产生一个”翻译文件“（例如.obj），这个.obj可能能在Windows上运行，而不能在IOS上运行，因为相同的机器语言命令可能时两个系统产生不同的应答，在这种情况下，文件就要重新编程；因此，c语言不是跨平台的。这种类型的语言叫做 编译型语言。

而不同的是，python就是一个解释型语言。与编译型语言不同，解释型语言在翻译时是按行解释的。因此解释性语言必须将源码交给设备本地，再由编译器翻译，因此任何设备都可以正常运行解释型语言的代码。所以我们说py是跨平台的。由于这样的语言需要源码，因此这种语言也是天生带有开源属性的。

还有一类是java这样的混合型，它是逐行解释的，但不是在计算机的本地进行解释，而是在java自带的虚拟机（JVM）中进行解释。

#### JDK 和 JRE

JDK（Java Development Kit –Java开发工具包）和JRE（Java Runtime Environment — Java运行环境）是Java开发中常用的两个术语。 

 JDK是Java开发工具包，它提供了开发、编译、调试和运行Java程序所需的工具和资源。JDK包括了Java编译器（javac）、Java虚拟机（JVM）、Java类库以及其他用于开发Java应用程序的工具和资源。  

JRE是Java运行时环境，它是在计算机上运行Java应用程序所必需的。JRE包括了Java虚拟机（JVM）和Java类库，但不包含用于开发Java程序的编译器和其他开发工具。 

JDK适用于开发人员，提供了开发和调试Java程序所需的全部工具和资源。而JRE适用于普通用户，只需要运行Java程序而无需进行开发

>  JVM  ( java virtual machine java虚拟机)，是一个真正运行java代码的地方。java运行的必备工具