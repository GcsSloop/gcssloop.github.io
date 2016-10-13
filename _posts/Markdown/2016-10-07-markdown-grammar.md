---
layout: post
category: Markdown
title: Markdown实用技巧－基础语法
tags: Markdown
keywords: GcsSloop, gcssloop
excerpt: 自从接触了 Markdown 之后，就一直用 Markdown 作为自己的主要书写工具，不论是平时做一些简单的纪录，还是用来写博客，写文档都是非常方便。
---




## Markdown 基础语法

为保证语法兼容性，本文只介绍基础语法，扩展语法等其它内容，会在后续的文章中单独介绍。

**注意：所有的标记符号均使用英文，中文无效。**


### 段落和换行

在 Markdown 中段落由一行或者多行文本组成，相邻的两行文字会被视为同一段落，如果存在空行( Markdown 对空行的定义是看起来是空行就是空行，即使空行中存在 空格 TAB 会车 不可见字符，同样会被视为空行)则被视为不同段落。

Markdown支持段内换行，如果你想进行段落内换行可以在上一行结尾插入两个以上的空格后再回车。

<table>
    <tr>
      <th>Markdown</th>
      <th>预览</th>
    </tr>
    <tr>
      <td>
      第一行<br/>
      相邻被视为同一段落。
      </td>
      <td>
        <p>
        第一行 相邻被视为同一段落。
        </p>
      </td>
    </tr>
    <tr>
      <td>
      第一行[空格][空格]<br/>
      上一行结尾存在两个空格，段内换行
      </td>
      <td>
        <p>
        第一行<br/>
        上一行结尾存在两个空格，段内换行。
        </p>
      </td>
    </tr>
    <tr>
      <td>
      第一行<br/>
      <br/>
      两行之间存在空行，视为不同段落。
      </td>
      <td>
        <p>
        第一行
        </p>
        <p>
        两行之间存在空行，视为不同段落。
        </p>
      </td>
    </tr>
</table>

******

### 标题

Markdown 支持多种标题格式。

利用 = （最高阶标题）和 - （第二阶标题）可以定义一级标题和二级标题，(任何数量的 = 和 - 都可以有效果) 但个人不推荐使用：

<table>
    <tr>
      <th>Markdown</th>
      <th>预览</th>
    </tr>
    <tr>
      <td>一级标题<br/>====</td>
      <td><h1>一级标题</h1></td>
    </tr>
    <tr>
      <td>二级标题<br/>----</td>
      <td><h2>二级标题</h2></td>
    </tr>
</table>

通过在行首插入 1 到 6 个 # ，来定义对应的 1 到 6 阶 标题，个人推荐使用这种，例如：

<table>
    <tr>
      <th>Markdown</th>
      <th>预览</th>
    </tr>
  <tr>
    <td># 一级标题</td>
    <td><h1>一级标题</h1></td>
  </tr>
  <tr>
    <td>## 二级标题</td>
    <td><h2>二级标题</h2></td>
  </tr>
  <tr>
    <td>### 三级标题</td>
    <td><h3>三级标题</h3></td>
  </tr>
  <tr>
    <td>#### 四级标题</td>
    <td><h4>四级标题</h4></td>
  </tr>
  <tr>
    <td>##### 五级标题</td>
    <td><h5>五级标题</h5></td>
  </tr>
  <tr>
    <td>###### 六级标题</td>
    <td><h6>六级标题</h6></td>
  </tr>
</table>

******

### 强调

> 删除线的 `~` 符号一般位于键盘左上角位置。

<table>
    <tr>
      <th>Markdown</th>
      <th>预览</th>
    </tr>
    <tr>
      <td>*倾斜*</td>
      <td>
        <i>倾斜</i>
      </td>
    </tr>
    <tr>
      <td>**粗体**</td>
      <td><b>粗体</b></td>
    </tr>
    <tr>
      <td>~~删除线~~</td>
      <td><s>删除线</s></td>
    </tr>
    <tr>
      <td>
        &gt; 引用
      </td>
      <td>
        <blockquote>引用</blockquote>
      </td>
    </tr>
</table>

******

### 链接和图片

<table>
    <tr>
      <th width="200">Markdown</th>
      <th width="200">预览</th>
    </tr>
  <tr>
    <td>[GcsSloop](http://www.gcssloop.com)</td>
    <td><a href="http://www.gcssloop.com" target="_blank">GcsSloop</a></td>
  </tr>
  <tr class="alternate">
    <td>[GcsSloop@gmail.com](GcsSloop@gmail.com)</td>
    <td><a href="mailto:GcsSloop@gmail.com">GcsSloop@gmail.com</a></td>
  </tr>
  <tr class="alternate">
    <td>![GcsSloop Blog](http://www.gcssloop.com/assets/siteinfo/friends/gcssloop.jpg)</td>
    <td><img src="http://www.gcssloop.com/assets/siteinfo/friends/gcssloop.jpg" alt="GcsSloop Blog" /></td>
  </tr>
</table>

******

### 列表

<table>
    <tr>
      <th>Markdown</th>
      <th>预览</th>
    </tr>
  <tr>
    <td>
      * 项目<br />
      * 项目<br />
      * 项目<br />
      &nbsp;&nbsp;* 子项目</span><br />
      &nbsp;&nbsp;* 子项目<br />
      * 项目
    </td>
    <td>
      <ul>
        <li>项目</li>
        <li>项目</li>
        <li>项目
          <ul>
            <li>子项目</li>
            <li>子项目</li>
          </ul>
        </li>
        <li>项目</li>
      </ul>
    </td>

  </tr>
  <tr class="alternate">
    <td>
      1. 项目<br />
      2. 项目<br />
      3. 项目<br />
      &nbsp;&nbsp;1. 子项目</span><br />
      &nbsp;&nbsp;2. 子项目<br />
      4. 项目
    </td>
    <td>
      <ol>
        <li>项目</li>
        <li>项目</li>
        <li>项目
          <ol>
            <li>子项目</li>
            <li>子项目</li>
          </ol>
        </li>
        <li>项目</li>
      </ol>
    </td>
  </tr>
</table>


### 下划线和特殊符号

<table>
    <tr>
      <th>Markdown</th>
      <th>预览</th>
    </tr>
  <tr>
    <td>
      在一行中用三个以上的星号、减号、下划线来建立一个分隔线<br />
      ---
    </td>
    <td>
      <hr />
    </td>
  </tr>
  <tr class="alternate">
    <td>可以利用反斜杠(转义字符)来插入一些在语法中有特殊意义的符号<br />
        \*Hi\*
    </td>
    <td>*Hi*</td>
  </tr>
</table>


<h2>表格</h2>

<p>Markdown：</p>

<pre><code>| First Header  | Second Header |
| ------------- | ------------- |
| Row 1 Cell 1  | Row 1 Cell 2  |
| Row 2 Cell 1  | Row 2 Cell 2  |
</code></pre>


<p>预览：</p>

<table>
<thead>
<tr>
<th> First Header  </th>
<th> Second Header </th>
</tr>
</thead>
<tbody>
<tr>
<td> Row 1 Cell 1  </td>
<td> Row 1 Cell 2  </td>
</tr>
<tr>
<td> Row 2 Cell 1  </td>
<td> Row 2 Cell 2  </td>
</tr>
</tbody>
</table>
