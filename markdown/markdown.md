<!--
 @Description : Markdown Guide - 介绍 Markdown 使用语法以及使用规范。
 @Author      : jiyou.Fool
 @Update      : jiyou.Fool (2016.06.15)
-->

# Markdown Guide
---

Markdown 的目标是实现易写易读，同时 Markdown 兼容部分 HTML 标签。Markdown 可以自动转换特殊字符。

### 目录
---

+ ##### [Markdown 语法](#grammar)
+ ##### [Markdown 约定](#conventions)

<a name="grammar"></a>
### Markdown 语法
---

<a name="block"></a>
##### 1.区块元素  

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
##### 2.区段元素

+ 链接

  ```
  [text](http://link.com 'title')
  ```

  当一个链接会被多次使用时，可以利用 ` 参考式 ` 。参考式可以在当前文档下任何地方定义。

  ```
  [id]: http://link.com 'title'
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
### Markdown 约定
---
<a name="common"></a>
##### 1.通用约定

+ 数字、英文与中文相邻需要用空格隔开。
+ 层次关系注意使用缩进。
+ 标题、

<a name="notes"></a>
##### 2.文件注释

所有 Markdown 文件必须添加类似以下注释，包含说明、作者、更新信息。   

```
<!--
 @Description : Markdown Guide - 介绍 Markdown 使用语法以及使用规范。
 @Author      : jiyou.Fool
 @Update      : jiyou.Fool (2016.06.15)
-->
```

> Snippets:

```
# Markdown注释
    'notes - markdown'
        'prefix':'m-notes'
        'body':"""
        <!--
         @Description : ${1:name} - ${2:description}
         @Author      : ${3:jiyou.Fool}
         @Update      : ${4:jiyou.Fool} (${5:2016.06.15})
        -->
        $6
        """
```

<a name="title"></a>
##### 2.标题

Markdown 文件标题选择使用以下三种,标题下分割线固定使用 ` --- ` ,并且一级，三级标题下留一行空白。

```
# 一级标题
### 二级标题
##### 三级标题
```

> Snippets:   

```
# Markdown标题
    'h1 - markdown':
        'prefix':'m-h1'
        'body':"""
        # ${1:title}
        ---

        $2
        """
    'h3 - markdown':
        'prefix':'m-h3'
        'body':"""
        ### ${1:title}
        ---

        $2
        """
    'h5 - markdown':
        'prefix':'m-h5'
        'body':"""
        ##### ${1:title}

        $2
        """
```



<!-- To Be Continue -->
