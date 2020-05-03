## Markdown语法简要规则

### 标题

```markdown
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
```

### 列表

```
[comment]: <> (无序列表)
- 内容
- 内容
- 内容
[comment]: <> (有序列表)
1. 步骤1
2. 步骤2
3. 步骤3
```

[comment]: <> "无序列表"

- 内容
- 内容
- 内容

[comment]: <> "有序列表"

1. 步骤1
2. 步骤2
3. 步骤3

!> 在Typora中，列表最后一行换行后会无法删除缩进，此时可以通过快捷键 <kbr>Ctrl</kbr> + <kbr>[</kbr> 回到首位。

### 引用

```
> 子曾经曰过：
```

>  子曾经曰过：

### 粗体 斜体 删除线

```
*斜体*
**粗体**
~~删除线~~
```

*粗体*
**斜体**
~~删除线~~

### 分割线

```
---
***
```

---
***

### 目录

```
[Toc]
```

!> 目录在Docsify中不编译也不渲染

### 代码

#### 多行代码

```markdown
​```C++
#include<iostream>
​```
```

```C++
#include<iostream>
```

#### 行内代码

```
利用`sort()`方法
```

利用`sort()`方法

### 图片与链接

图片为`![]()`

链接为`[]()`

```
![logo](https://docsify.js.org/_media/icon.svg ':size=WIDTHxHEIGHT')

[Docsify](https://docsify.js.org/#/)
```

![logo](Markdown.assets/icon-1588434876054.svg ':size=WIDTHxHEIGHT')

[Docsify](https://docsify.js.org/#/)

地址也可以为相对地址，如：

```
![image-20200502235750107](Markdown.assets/image-20200502235750107.png)
```



![image-20200502235750107](Markdown.assets/image-20200502235750107.png)

> 使用Typora，在偏好设置>图像中，勾选”优先选择相对路径“之后，在.md文档内粘贴可以自动补充路径。

---



## 文档助手

[Docsify文档](/https://docsify.js.org/#/zh-cn/helpers)

除了基本语法外，Docsify拓展了一些Markdown语法

### 强调内容

适用于一些非常重要的，可能引发错误的提示。

语法为`!> 内容`。

```Markdown
!> 非法调用会导致程序崩溃
```



!> 非法调用会导致程序崩溃

### 普通提示

一些小Tips，TODO内容。

```markdown
?> 这里也可以采用分治的思想
```

?> 这里也可以采用分治的思想

### 图片处理

#### 缩放

```
![logo](https://docsify.js.org/_media/icon.svg ':size=WIDTHxHEIGHT')
![logo](https://docsify.js.org/_media/icon.svg ':size=50x100')
![logo](https://docsify.js.org/_media/icon.svg ':size=100')

<!-- 支持按百分比缩放 -->

![logo](https://docsify.js.org/_media/icon.svg ':size=10%')
```
![logo](https://docsify.js.org/_media/icon.svg ':size=WIDTHxHEIGHT')
![logo](https://docsify.js.org/_media/icon.svg ':size=50x100') 
![logo](https://docsify.js.org/_media/icon.svg ':size=100')
![logo](https://docsify.js.org/_media/icon.svg ':size=10%')