### BFC-Block-Format-Context: 块级格式上下文

### 一个块格式化上下文由以下之一创建：
* 根元素或其它包含它的元素
* 浮动 (元素的`[float](https://developer.mozilla.org/zh-CN/docs/Web/CSS/float) 不是none`)
* 绝对定位的元素 (元素具有 position 为 absolute 或 fixed)
* 内联块 inline-blocks (元素具有 display: inline-block)
* 表格单元格 (元素具有 display: table-cell，HTML表格单元格默认属性)
* 表格标题 (元素具有 display: table-caption, HTML表格标题默认属性)
* 块元素具有overflow ，且值不是 visible
* display: flow-root
