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
