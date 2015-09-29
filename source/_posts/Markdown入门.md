title: Markdown入门
date: 2015-09-28 23:16:11
categories: 「标记语言」
tags: [文本编辑,Markdown]
---
### 一、 Markdown简介
Markdown是一种用来写作的轻量级「标记语言」，它用简洁的语法代替排版，使我们专心于码字。Markdown的目标是实现「易读易写」。
### 二、 使用Markdown的优点
* 专注于你的文字内容而不是排版样式
* 纯文本内容，兼容所有的文本编辑器与文字处理软件
* 本身的.md文件方便生成HTML、PDF格式文件
* 上手容易，使用方便

### 三、 Markdown文档
* [John Gruber的Markdown语法说明](http://daringfireball.net/projects/markdown/syntax)
* [MardDown-语法说明(中文)](http://www.markdown.cn/)

### 四、 Markdown基础语法
#### 1. 标题
```markdown
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
```
预览效果：
># 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题


#### 2. 列表
无序列表
```markdown
* 1
* 2
* 3
```
* 1
* 2
* 3

有序列表
```markdown
1. 1
2. 2
3. 3
```
1. 1
2. 2
3. 3

#### 3. 引用
```markdown
> 这是引用
```
> 这是引用

#### 4. 粗体与斜体
```markdown
**粗体**
*斜体*
```
**粗体**
*斜体*

#### 5. 链接与图片
```markdown
[Baidu](http://www.baidu.com)
![Baidu icon](https://www.baidu.com/img/bdlogo.png)
```

链接
[Baidu](http://www.baidu.com)

图片
![Baidu icon](https://www.baidu.com/img/bdlogo.png)


#### 6. 分隔线
```markdown
***
```
***
#### 7. 代码区段
```markdown
`int a=0;`
```
`int a=0;`
#### 8. 代码高亮
```markdown
```java
public static void main(string[] args){
	System.out.prinln("Hello world!");
}
` ` `
```

```java
public static void main(string[] args){
	System.out.prinln("Hello world!");
}
```
#### 9. 表格
```markdown
| 星期一 | 星期二 | 星期三 |
|---|:---|:---|
|C | C++ | Java |
|C# | OC | PHP |

星期一 | 星期二 | 星期三
---|---|---
C | C++ | Java
C# | OC | PHP
```
| 星期一 | 星期二 | 星期三 |
|---|:---|:---|
|C | C++ | Java |
|C# | OC | PHP |

星期一 | 星期二 | 星期三
---|---|---
C | C++ | Java
C# | OC | PHP

### 五、 小结
Markdown的宗旨是专注于内容，以上的markdown语法简单应用已经能够满足大部分的需求，特殊的可以查看文档。