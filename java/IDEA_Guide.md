# IDEA 使用指南：

*前言*

*IDEA 是目前业内公认最好java编辑工具之一，包含了大量的插件，快捷语法，同时可以实现快速的自动保存，*



### IDEA的设置和插件

**IDEA设置**

1. 外观：对于IDEA界面的各种改动都可以在外观的部分进行设置，大到主题的更换，小到特定语法的颜色显示都可以进行更改
2. 自动导包：在设置中可以设置输入scanner，进行键盘录入后自动导包
3. 自动提示：可以让IDEA在代码设置中让IDEA的自动报错

**推荐使用的插件**

插件太多会导致卡顿，1-9为基础插件，10~为进阶插件。

1. chinese simplified 

  中文插件

2. translation

  翻译插件，可以在编写项目的过程中灵活的进行右键翻译操作，在国内需要指定国内的翻译工具 

3.  bito

	一个基于GPT-4的插件，可以查找错误，分析代码，实现代码，直接编写甚至是日常问答，使用时不需要OpenAI账号，但需要创建一个workspace账号。

4. copilot

  著名的AI编译工具，和上述的bite功能类似，可以根据用户的需要直接进行代码的编写。

5. key promoter X

  快捷键提示工具，每次使用鼠标进行操作，这个插件都会提示可以使用什么插件进行代替。有助于快速熟悉快捷键操作，提高编写效率。

6. rainbow brackets

  彩虹括号插件，通过将不同级的括号用颜色区分来提高代码的可读性

7.  tabnine AI code completion

	增强IDEA原有的智能输入，可以提升效率，且有类似电脑输入法的记忆适应功能

8.  SequenceDiagram

	可以根据目前已有的代码写出时序图，可以快速地分析代码，代码之间的调用顺序一目了然，也可以将其导出为图片格式。对于理解别人的代码和代码之间的分享有着巨大的帮助 

9. LeetCode Editor

​       下载后会在屏幕右侧边栏中出现LeetCode功能，使用这个功能可以刷代码题目，帮助代码进阶，每个题目都   有非常详尽的解题思路

10. restful tool  

	目前最高效易用的管理接口插件，支持在线调用

11.  CheckStyle-IDEA

	规范编写的代码，使其保持公司的规范需要，一般来说使用现成的Google规范，但也可以公司内部编写一个规范文件，（又处于养成良好习惯，想更加贴合国内规范的可以使用阿里巴巴规范 Alibaba Java Coding Guidelines插件）

12.  MyBatisX

	对Java知名数据访问框架Mybatis的拓展，有许多功能，如美化图标，自动跳转。最为实用的是代码生成，可以省去重复工作

13.  Maven Helper

	一个用于处理Maven 冲突的插件，辅助排除冲突

14. .ignore

	一个帮助快速创建.gitignore文件的辅助工具





### IDEA 的项目结构

IDEA 的项目结构总共分为四个类型，分别为**project class module package(项目 类 模块 包)**

以微信作为例子：

微信的整体就是一个project，

<img src="../resourse/image/2e9954b6d5146e46d9263aaab9ff966.jpg" style="zoom:50%;" />

在微信的下方分别有四个相对独立，分别作用的功能（上图），这四个就可以称之为module，因此在一个完整的project中，包含着一个或者多个的module

在“微信（消息）”模块中，我们可以看到模块包含着大量的package ，package实质上就是文件夹，用于存放相同功能的代码（资料）。例如，消息中会有文字，图片，动画等，这些功能都需要代码来实现，因此将这些代码分别放在文字，图片，动画 的文件夹中，方便管理。

因IDEA中大小包含关系是    projct(项目) > module(模块) > package(包) > class(类)



### IDEA 项目的基本创建



##### project

由于在IDEA中最大的是project ,因此在主界面优先创建project

<img src="../resourse/image/屏幕截图 2023-07-26 105203.png" style="zoom:25%;" />

在学习初期不需要使用项目生成器，因此我们直接选择空项目并命名创建这个项目。 

##### module:

在进入项目页面后，优先开始创建module ，在  文件  –>  项目结构  –>  java类型  ->  创建    来进行这个module的创建一般来说在一个project 中会有很多不同的模板，这些模板需要明确的名字用来分析。

##### package

在创建完module 后需要创建package.

所谓的package就是一个文件夹，在创建出module之后可以在里面看到一个名为“src(资源)”的文件夹，我们的package就需要在这里面实现。

创建package 是有创建规范的，一般来说是<u>“公司网址的反写，省去www.部分，再加上package的名称”</u>。 例如，当前社团当前的对外网址是 www.mocd.cc，则创建package为  “cc.mocd.demo” 。 这样的创建方法在实际上是创建多级包的一种语法，意思为创建一个 …> src > cc > mocd > demo 样式的层层包裹的多级包。多级包名称之间用点隔开

##### class

class的创建是创建在package中的,通过右键创建时，右键你需要创建class的位置，然后 新建-> java class -> 输入名字（选择class）     进行创建（注意最好不要在src中创建class），主要的代码就是在class中进行编写的

依照此方法创建时，整个代码包含了完整的结构（project module package class ）并且层层包裹，创建之后就可以进行java代码本身的编写了。

注意文件名和类名要保持一致！（即文件名和public class 后的名称保持一致）

### IDEA的便捷语法

在IDEA中配置了很多不同的java语法，这类语法可以节约输入的时间。

1. psvm

	这个语法可以快速创建程序main 函数 “poblic static void main (string[ ]  args) {}  ”，实际上就是首字母缩写

2. sout

	这个语法可以快速创建print函数“ System.out.println(); ”

3.  



### IDEA常用快捷键：

在IDEA中双击shift 然后查找”key reference“即可查看快捷键大全，此处为



| 操作                       | 功能                                                |
| -------------------------- | --------------------------------------------------- |
| shift+shift                | 快捷搜索                                            |
| Ctrl + X                   | 删除当前行                                          |
| Ctrl +D                    | 复制当前行                                          |
| Alt+Insert(或右键Generate) | 生成代码(如get,set方法,构造函数等)                  |
| Ctrl+Alt+T                 | 生成try catch （或者 Alt+enter选择）                |
| CTRL+ALT+T                 | 把选中的代码放在 TRY{} IF{} ELSE{} 里               |
| Ctr+shift+U                | 实现大小写之间的转化                                |
| ALT+回车                   | 导入包,自动修正                                     |
| CTRL+ALT+L                 | 格式化代码                                          |
| CTRL+ALT+I                 | 自动缩进                                            |
| CTRL+E                     | 最近更改的代码                                      |
| fori                       | 生成for (int i = 0; i < ; i++) {}                   |
| Alt + <–左右–>键           | 实现窗口左右更换（多窗口）                          |
| Ctrl + 鼠标点击            | 快速找到成员变量的出处                              |
| Shift+F6                   | 重构/重命名 (包、类、方法、变量、甚至注释等)        |
| CTRL+Q                     | 查看当前方法的声明                                  |
| Ctrl+Alt+V                 | 自动创建变量（new 对象();之后选择按快捷键）         |
| Ctrl+O                     | 重写方法                                            |
| Ctrl+I                     | 实现方法                                            |
| ALT+/                      | 代码提示                                            |
| Ctrl+Shift+R               | 在当前项目中替换指定内容                            |
| Ctrl+E                     | 最近编辑的文件列表                                  |
| Ctrl+P                     | 显示方法参数信息                                    |
| Ctrl+Shift+Insert          | 查看历史复制记录，idea可以保留历史复制的 100 条记录 |

#### 查找

| 快捷键                 | 介绍                         |
| ---------------------- | ---------------------------- |
| Ctrl + F               | 在当前文件进行文本查找       |
| Ctrl + R               | 在当前文件进行文本替换       |
| Shift + Ctrl + F       | 在项目进行文本查找           |
| Shift + Ctrl + R       | 在项目进行文本替换           |
| Shift + Shift          | 快速搜索                     |
| Ctrl + N               | 查找class                    |
| Ctrl + Shift + N       | 查找文件                     |
| Ctrl + Shift + Alt + N | 查找symbol（查找某个方法名） |

#### 跳转切换

| 快捷键           | 介绍                  |
| ---------------- | --------------------- |
| Ctrl + E         | 最近文件              |
| Ctrl + Tab       | 切换文件              |
| Ctrl + Alt + ←/→ | 跳转历史光标所在处    |
| Alt + ←/→ 方向键 | 切换子tab             |
| Ctrl + G         | go to（跳转指定行号） |

#### 编码相关

| 快捷键                      | 介绍                                                         |
| --------------------------- | ------------------------------------------------------------ |
| Ctrl + W                    | 快速选中                                                     |
| (Shift + Ctrl) + Alt + J    | 快速选中同文本                                               |
| Ctrl + C/Ctrl + X/Ctrl + D  | 快速复制或剪切                                               |
| 多行选中 Tab / Shift + Tab  | tab                                                          |
| Ctrl + Y                    | 删除整行                                                     |
| 滚轮点击变量/方法/类        | 快速进入变量/方法/类的定义处                                 |
| Shift + 点击Tab             | 快速关闭tab                                                  |
| Ctrl + Z 、Ctrl + Shift + Z | 后悔药，撤销/取消撤销                                        |
| Ctrl + Shift + enter        | 自动收尾，代码自动补全                                       |
| Alt + enter                 | IntelliJ IDEA 根据光标所在问题，提供快速修复选择，光标放在的位置不同提示的结果也不同 |
| Alt + ↑/↓                   | 方法快速跳转                                                 |
| F2                          | 跳转到下一个高亮错误 或 警告位置                             |
| Alt + Insert                | 代码自动生成，如生成对象的 set / get 方法，构造函数，toString() 等 |
| Ctrl + Shift + L            | 格式化代码                                                   |
| Shift + F6                  | 快速修改方法名、变量名、文件名、类名等                       |
| Ctrl + F6                   | 快速修改方法签名                                             |

#### 代码阅读相关

| 快捷键                     | 介绍                               |
| -------------------------- | ---------------------------------- |
| Ctrl + P                   | 方法参数提示显示                   |
| Ctrl + Shift + i           | 就可以在当前类里再弹出一个窗口出来 |
| Alt + F7                   | 可以列出变量在哪些地方被使用了     |
| 光标在子类接口名，Ctrl + u | 跳到父类接口                       |
| Alt + F1 + 1， esc         |                                    |
| (Shift) + Ctrl + +/-       | 代码块折叠                         |
| Ctrl + Shift + ←/→         | 移动窗口分割线                     |
| Ctrl + (Alt) + B           | 跳转方法定义/实现                  |
| Ctrl + H                   | 类的层级关系                       |
| Ctrl + F12                 | Show Members 类成员快速显示        |

#### 版本管理相关

| 快捷键       | 介绍             |
| ------------ | ---------------- |
| Ctrl + D     | Show Diff        |
| (Shift) + F7 | （上）下一处修改 |

#### 控制台语句 System.out 相关：

| 生成控制台的相关快捷键 | 描述                                                         |
| ---------------------- | ------------------------------------------------------------ |
| sout + Tab键           | 生成System.out.println();，输出到控制台语句并换行。          |
| souf + Tab键           | 生成System.out.printf("");,输出一个格式化字符串到控制台。    |
| soutm + Tab键          | 生成System.out.println("类名.方法名");，输出当前 类和方法名 到控制台。 |
| soutp + Tab键          | 生成System.out.println(所有方法参数名+值);，输出当前 方法的参数名和值 到控制台。 |



### IDEA 的常见操作

（ ）



### IDEA 的基本原则：

1. IDEA中一个窗口只会显示一个project，也就是说，打开两个project时它必定是以两个窗口的形式显示的，保证了不会出现混淆；
2. 创建任何内容的时候，保证你的目录中不要出现中文。
3. IDEA中并没有工作空间的概念
4. 部署web工程始终部署在module下的web文件夹中
5. 代码可读性放在第一位
6. 代码中不要出现莫名其妙的数字或者类型名
7. 

