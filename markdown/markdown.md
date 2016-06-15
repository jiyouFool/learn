<!--
 @Description : Markdown Guide - 介绍 Markdown 使用语法以及使用规范。
 @Author      : jiyou.Fool (jiyou.fool@gmail.com)
 @Update      : jiyou.Fool (2016.06.15)
-->

# Markdown Guide

Markdown 的目标是实现易写易读，同时 Markdown 兼容部分 HTML 标签。Markdown 可以自动转换特殊字符。

## 目录

1. [Markdown 语法](#grammar)
    + [区块元素](#block)
    + [区段元素](#inline)
2. [Markdown 约定](#conventions)
    + [通用约定](#common)
    + [文件注释](#init)
    + [标题](#title)
    + [目录](#catalogue)
    + [代码](#code)
    + [链接](#link)
    + [强调](#em)
    + [图片](#img)
    + [其他](#other)

<a name="grammar"></a>
## Markdown 语法

<a name="block"></a>
#### 1.区块元素  

+ 换行  
行尾使用两个以上空格，然后回车。

+ 标题   
Markdown 支持两种语法的标题。

  1.利用底线 ` = ` 或 ` - ` 。   

  ```
  最高等级标题
  ==========

  第二等级标题
  ----------
  ```  

  2.行首以 ` # ` 开始。

  ```
  # 这是H1
  ## 这是H2
  ### 这是H3
  ...
  ###### 这是H6
  ```

+ 引用   

  ```
  > 这里是引用的内容
  ```

+ 列表
无序列表可以用三种方式表达。

  1.利用 ` + ` 。

  ```
  + 无序列表
  ```

  2.利用 ` - ` 。

  ```
  - 无序列表
  ```

  3.利用 ` * ` 。

  ```
  * 无序列表
  ```

  有序列表用数字加点表达。

  ```
  1. 有序列表
  ```

  > 标记上使用的数字不影响输出的HTML。

+ 分割线
分割线可以用两种符号表达。

  1.利用三个以上 ` * ` 。

  ```
  ***
  ****
  * * *
  ```

  2.利用三个以上 ` - ` 。

  ```
  ---
  ----
  - - -
  ```
<a name="inline"></a>
#### 2.区段元素

+ 链接

  ```
  [text](http://link.com 'title')
  ```

  当一个链接会被多次使用时，可以利用 ` 参考式 ` 。参考式可以在当前文档下任何地方定义。
  > ` [] ` 中需要添加字符串作为id，这里没有加是避免被 Markdown 识别为 ` 参考式 ` 。

  ```
  []: http://link.com "title"
  ```

  使用 ` 参考式 ` 。

  ```
  [text][id]
  ```

+ 强调
强调可以使用两种符号表达。

  1.利用 ` * ` 。

  ```
  *强调内容*
  **强调内容**
  ```

  2.利用 ` _ ` 。

  ```
  _强调内容_
  __强调内容__
  ```

+ 代码
代码可以使用两种方式表达。

  1.利用 \` 包裹。   

  2.利用 \`\`\` 包裹。

+ 图片

  ```
  ![Alt text](http:imageLink.com 'title')
  ```

  > 图片参考式和链接参考式写法相同。

<a name="conventions"></a>
## Markdown 约定

<a name="common"></a>
#### 1.通用约定

+ 数字、英文与中文相邻需要用空格分隔。
+ 层次关系注意使用缩进。
+ 标题、块代码、图片、表格上下用空行分隔。

<a name="init"></a>
#### 2.文件初始化

Markdown 初始化定义文件描述以及结尾。

```
<!--
 @Description : name - description
 @Author      : jiyou.Fool (jiyou.fool@gmail.com)
 @Update      : jiyou.Fool (2016.06.15)
-->




<!-- To Be Continue -->
```

> Snippet:

```
# Markdown 初始化
    'notes - markdown':
        'prefix':'m-init'
        'body':"""
        <!--
         @Description : ${1:name} - ${2:description}
         @Author      : ${3:jiyou.Fool} (${4:jiyou.fool@gmail.com})
         @Update      : ${5:jiyou.Fool} (${6:2016.06.15})
        -->
        $7



        <!-- To Be Continue -->
        """
```

<a name="title"></a>
#### 3.标题

选择使用以下三种 Markdown 标题。

```
# H1
## H2
#### H4
```

> Snippet:

```
# Markdown 标题
    'h1 - markdown':
        'prefix':'m-h1'
        'body':"""
        # ${1:title}

        $2
        """
    'h2 - markdown':
        'prefix':'m-h2'
        'body':"""
        ## ${1:title}

        $2
        """
    'h4 - markdown':
        'prefix':'m-h4'
        'body':"""
        #### ${1:title}

        $2
        """
```

<a name="catalogue"></a>
#### 4.目录

一级目录使用有序列表，二级目录使用无序列表。

```
1. [title](#tag)
    + [title](#tag)
2. [title](#tag)
    + [title](#tag)
    + [title](#tag)
```

> Snippet:

```
'catalogue - markdown':
        'prefix':'m-c'
        'body':"""
        ${1:1}. [${2:title}](#${3:tag})
            $4
        """
    'catalogue-item - markdown':
        'prefix':'m-ci'
        'body':"""
        + [${1:title}](#${2:tag})
        $3
        """
    'catalogue-link - markdown':
        'prefix':'m-cl'
        'body':"""
        <a name="${1:tag}"></a>
        $2
        """
```

<a name="code"></a>
#### 5.代码

行内短代码与行内其他文本各留一个空格间距，代码内前后各留一个空格间距。代码块上下各留一行间距。

> Snippet: 实际上没有 \`\`\` 前的 ` \ ` 。

```
# Markdown 代码
    'shortcode - markdown':
        'prefix':'m-sc'
        'body':"""
        ` $1 ` $2
        """
    'code - markdown':
        'prefix':'m-cd'
        'body':"""

        \`\`\`
        $1
        \`\`\`

        $2
        """
```

<a name="link"></a>
#### 6.链接

链接使用无 title 链接。

```
[text](http://link.com)
```

> Snippet:

```
# Markdown 链接
    'a-link - markdown':
        'prefix':'m-a'
        'body':"""
        [${1:text}](${2:http://link.com}) $3
        """
    'a-depand - markdown':
        'prefix':'m-ad'
        'body':"""
        [${1:text}][${2:id}] $3
        """
```

重复的链接使用参考式。

> Snippet:

```
# Markdown 参考式
    'depand - markdown':
        'prefix':'m-d'
        'body':"""
        [${1:id}]: ${2:http://link.com} "${3:title}"
        $4
        """
```

<a name="em"></a>
#### 7.强调

```
**text**
*text*  
```

> Snippet:

```
# Markdown  强调
    'em - markdown':
        'prefix':'m-e'
        'body':"""
        **${1:text}** $2
        """
    'i - markdown':
        'prefix':'m-i'
        'body':"""
        *${1:text}* $2
        """
```

<a name="img"></a>
#### 8.图片

```
![Alt text](http:imageLink.com 'title')
```

> Snippet:

```
# Markdown 图片
    'img - markdown':
        'prefix':'m-img'
        'body':"""
        ![Alt ${1:text}](${2:http:imageLink.com} '${3:title}')
        $4
        """
```

<a name="other"></a>
#### 9.其他

+ 分割线，选择使用 ` --- `  。
+ Snippet标记。

  ```
  # Markdown Snippets
    'Snippet - markdown':
        'prefix':'m-sn'
        'body':"""
        > Snippet:
        $4
        """
  ```




























<!-- To Be Continue -->
