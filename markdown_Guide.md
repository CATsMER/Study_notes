# Markdown

轻文本标记语言



### 一、标题

1. 使用井号的数量决定标题的文本大小



### 二、换行

1. 使用”Enter”键直接换行，或者使用unix 换行命令

2. 分割线

	使用”—“或者“***”

	```markdown
	---或者***
	```

	---



### 三、文本样式

1. **粗体** ：** 文本 **
2. *斜体* ： * 文本 *
3. ~~删除线~~ ： ~~ 文本 ~~
4. <u>下划线</u> :  <u> 文本 </u>
5. ==高亮==： == 文本 ==



### 四、代码块

1.  代码块创建：

	```markdown
	使用 “  ```编译语言名字（回车）    ”
	的步骤创建代码块
	```

	例子：

	```c++
	#include <stdio.h>
	
	int main()
	{
	    printf("hello world");
	    return 0;
	}
	```

	

### 五、数学计算式/matlab格式

1. 数学计算式：
	$$
	\frac{\partial f}{\partial x}=2\sqrt{a}x
	$$

	```markdown
	$$
	(任何需要的matlab格式的计算式)
	\frac{\partial f}{\partial x}=2\sqrt{a}x
	$$
	```



### 六、列表

1. 有序列表：

	```markdown
	1.
	2. 
	3. 
	```

2. 无序列表：

	```markdown
	-
	-
	-
	```

3. 待确认列表：

	```markdown
	- [x]
	- [x]
	- [](x代表这个待确认文本被勾选了)
	```

	



### 七、引用

1. 文本引用格式

	> 世界上只有一种英雄主义：在了解了生活的真面目后，依然选择热爱它——罗素 罗兰

   ```markdown
   > 引用的具体文本
   ```

2. 图片的链接引用：

	![个人头像](../../../../Pictures/Camera Roll/头像.png)

```markdown
![个人头像](../../../../Pictures/Camera Roll/头像.png)
```



3. 超链接文本：

	[我的个人主页](C:\Users\CATsMER\Desktop\MOCD常用工具\个人博客项目\Team_Blog\lzm\index)

	[我的个人主页2][id]

	```markdown
	3. [我的个人主页](C:\Users\CATsMER\Desktop\MOCD常用工具\个人博客项目\Team_Blog\lzm\index)
	
		[我的个人主页2][id]
	    使用id的方法访问一个页面
	
		[id]:C:\Users\CATsMER\Desktop\MOCD常用工具\个人博客项目\Team_Blog\lzm\index”个人主页”
	
	```

	[id]:C:\Users\CATsMER\Desktop\MOCD常用工具\个人博客项目\Team_Blog\lzm\index”个人主页”

4. 锚点：

	[大标题](#markdown学习)

```markdown 
[大标题](#markdown学习)  跳转到对应的锚点
```









