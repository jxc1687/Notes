### HTML 基本结构

```html
<!DOCTYPE html>
<html lang="zh-CN">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>网页标题</title>
  </head>
  <body>
    <h1>这是一个标题</h1>
    <p>这是一个段落</p>
  </body>
</html>
```

### `<!DOCTYPE html>`声明

- `<!DOCTYPE html>`是 HTML5 的**文档类型声明**
- 它指示浏览器按照 HTML5 的标准解析文档, 使用"标准模式"渲染页面, 确保跨浏览器兼容性

### `<html>`标签

- 根元素(root element), 包含整个网页的所有内容
- 属性`lang`指定网页语言, 如`lang="zh-CN"`表示中文(简体), 如`lang="en-US"`表示英文(美国)

### `<head>`标签

- 包含网页的元信息`<meta>`和标题`<title>`, 不会显示在页面上
- `<meta>`标签属性`charset`指定网页字符集, 如`charset="UTF-8"`表示使用 UTF-8 编码
- `<meta>`标签属性`name`和`content`是成对出现的, 用于设置网页的元信息, 如`name="viewport"`表示视窗(用户能看到的网页区域), `content="width=device-width, initial-scale=1.0"`表示视窗宽度为设备宽度, 初始缩放比例为 1.0
- `<title>`标签用于设置网页标题, 显示在浏览器标签上

### `<body>`标签

- 包含网页的可见内容, 如标题`<h1>`和段落`<p>`, 会显示在页面上

### 元素(element)

- `<标签名 属性="值">内容</标签名>`
- 标签名不区分大小写, 但是推荐使用小写, 如`<p>`
- 存在自闭合标签, 如`<img>`和`<input>`
- 元素可以有多个属性, 属性之间用空格分隔, 如`<a href="https://example.com" target="_blank">链接文本</a>`
- 属性的值建议用引号包围

### 语义化(Semantic HTML)

语义化是指用 HTML 标签来表达内容的含义和结构, 而不仅仅是外观

#### 语义化示例对比:

```html
<!-- 非语义化写法 -->
<div class="header">网站标题</div>
<div class="nav">导航菜单</div>
<div class="content">文章内容</div>
<div class="footer">页脚</div>

<!-- 语义化写法 -->
<header>网站标题</header>
<nav>导航菜单</nav>
<main>
  <article>文章内容</article>
</main>
<footer>页脚</footer>
```

#### 语义化优点

- SEO 优化: 搜索引擎更好理解页面结构
- 可维护性: 更容易阅读和理解代码
- 可访问性: 更容易被屏幕阅读器等辅助技术理解
- 设备兼容: 更容易在不同设备上显示与交互

### `<form>`标签

表单`<form>`用于收集用户输入的数据, 是网页交互的重要部分

#### `<form>`主容器

```html
<form action="/submit" method="post">
  <!-- 表单内容 -->
</form>
```

主要属性:

- `action`: 数据提交的 URL
- `method`: 数据提交方式, 如`get`或`post`

#### 主要输入控件

```html
<!-- 文本输入 -->
<input type="text" name="username" placeholder="请输入用户名" />

<!-- 密码 -->
<input type="password" name="password" />

<!-- 邮箱 -->
<input type="email" name="email" />

<!-- 数字 -->
<input type="number" name="age" min="1" max="100" />

<!-- 单选按钮 -->
<input type="radio" name="gender" value="male" id="male" />
<label for="male">男</label>
<input type="radio" name="gender" value="female" id="female" />
<label for="female">女</label>

<!-- 复选按钮 -->
<p>兴趣爱好：</p>
<input type="checkbox" name="hobbies" value="reading" id="read" />
<label for="read">阅读</label>

<input type="checkbox" name="hobbies" value="music" id="music" />
<label for="music">音乐</label>

<input type="checkbox" name="hobbies" value="sports" id="sports" checked />
<label for="sports">运动</label>

<!-- 多行文本 -->
<textarea name="message" rows="5" cols="50" placeholder="请输入留言"></textarea>

<!-- 下拉框 -->
<select name="city" required>
  <option value="">请选择城市</option>
  <option value="beijing">北京</option>
  <option value="shanghai">上海</option>
  <option value="guangzhou">广州</option>
</select>

<!-- 文件上传 -->
<input type="file" accept="image/*" />
<input type="file" accept=".jpg,.jpeg,.png,.gif" />
<input type="file" accept="image/jpeg,image/png" />

<!-- 隐藏字段 -->
<input type="hidden" name="user_id" value="12345" />

<!-- 按钮 -->
<button type="button">普通操作</button>
<button type="submit">提交表单</button>
<button type="reset">重置表单</button>
```

#### `enctype`属性

1. application/x-www-form-urlencoded(默认)
2. multipart/form-data(文件上传必需)

```html
<form method="post" enctype="multipart/form-data">
  <input type="text" name="title" value="我的照片" />
  <input type="file" name="photo" />
  <button type="submit">上传</button>
</form>
```

3. text/plain(纯文本, 很少使用)

### `<table>`标签

`<table>`标签用于创建表格, 是网页中展示结构化数据的重要元素

主要标签:

- `<table>`: 表格容器
- `<tr>`: 表格行(table row)
- `<th>`: 表头单元格(table header)
- `<td>`: 数据单元格(table data)

语义化标签:

- `<thead>`: 表格头部
- `<tbody>`: 表格主体
- `<tfoot>`: 表格底部

其他标签:

- `<caption>`: 表格标题, 必须放在`<table>`内第一行
- `<colgroup>`: 对表格列分组, 方便统一设置列的样式, 必须放在`<caption>`之后(如有)

常用属性:

- `colspan`: 合并列
- `rowspan`: 合并行

```html
<table>
  <caption>
    2024年销售数据统计
  </caption>
  <thead>
    <tr>
      <th>月份</th>
      <th>销售额</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1月</td>
      <td>50000</td>
    </tr>
  </tbody>
</table>
```
