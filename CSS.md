### 基础选择器(basic selectors)

#### element selector

```css
p {
  color: red;
}
```

#### class selector

```css
.highlight {
  background-color: yellow;
}
```

#### id selector

```css
#header {
  position: fixed;
}
```

#### universal selector

```css
* {
  margin: 0;
  padding: 0;
}
```

### 组合选择器(combinators)

#### descendant combinator

```css
div p {
  color: red; /* 无论嵌套层级有多深 */
}
```

#### child combinator

```css
ol > li {
  border-top: 5px solid red; /* 只影响下一层级 */
}
```

#### next-sibling combinator

```css
h1 + p {
  font-weight: bold; /* 只影响同一层级的后一个元素 */
}
```

#### subsequent-sibling combinator

```css
h1 ~ p {
  font-weight: bold; /* 影响同一层级的所有后续元素 */
}
```

### 属性选择器(attribute selectors)

- `[attr]`: 选择所有有 attr 属性的元素
- `[attr=value]`: 选择所有有 attr 属性, 且值为 value 的元素
- `[attr~=value]`: 选择所有有 attr 属性, 且存在值为 value 的元素

```html
<ul>
  <li>Item 1</li>
  <li class="a">Item 2</li>
  <li class="a b">Item 3</li>
  <li class="ab">Item 4</li>
</ul>
```

```css
li[class] {
  font-size: 120%; /* 会选中Item 2, 3, 4 */
}

li[class="a"] {
  background-color: yellow; /* 会选中Item 2 */
}

li[class~="a"] {
  color: red; /* 会选中Item 2, 3 */
}
```

- `[attr^=value]`: 选择所有有 attr 属性, 且值以 value 开头的元素
- `[attr$=value]`: 选择所有有 attr 属性, 且值以 value 结尾的元素
- `[attr*=value]`: 选择所有有 attr 属性, 且值包含 value 的元素

```html
<ul>
  <li class="a">Item 1</li>
  <li class="ab">Item 2</li>
  <li class="bca">Item 3</li>
  <li class="bcabc">Item 4</li>
</ul>
```

```css
li[class^="a"] {
  font-size: 120%; /* 会选中Item 1, 2 */
}

li[class$="a"] {
  background-color: yellow; /* 会选中Item 1,3 */
}

li[class*="a"] {
  color: red; /* 会选中Item 1,2,3,4 */
}
```

### 伪类选择器(pseudo-class)

常见的伪类包括:

- `:hover`: 鼠标悬停在元素上时
- `:active`: 元素被激活时
- `:focus`: 元素获得焦点时
- `:first-child`: 元素是父元素的第一个子元素时
- `:last-child`: 元素是父元素的最后一个子元素时
- `:nth-child(n)`: 元素是父元素的第 n 个子元素时

### 伪元素选择器(pseudo-element)

常见的伪元素包括:

- `::before`: 在元素之前插入内容
- `::after`: 在元素之后插入内容
- `::first-line`: 元素的第一行
- `::first-letter`: 元素的第一个字母
- `::selection`: 用户选中的内容

### 盒子模型(box model)

盒子模型定义了 HTML 元素在页面上占据空间的方式, 包含四个部分:

1. Content: 元素的实际内容区域, 如文本, 图片
2. Padding: 内容与边框之间的区域
3. Border: 边框
4. Margin: 元素与相邻元素之间的区域

CSS3 引入了`box-sizing`属性, 允许更改计算方式:

- `content-box`: 默认值, 宽高只计算 content 区域
- `border-box`: 宽高计算区域包含 content, padding 和 border

推荐全局设置

```css
* {
  box-sizing: border-box;
}
```
