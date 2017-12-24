### Way1: No need the width and height, use CSS3 transform:translate() to center the element;
```html
<div class="wrapper">
我不知道我的宽度和高是多少，我要实现水平垂直居中    
</div>
```
```css
.wrapper {
  padding: 20px;
  background:orange;
  color:#fff;
  border-radius: 5px;
  position:absolute; /*absolute position*/
  top:50%; /*make top and left 50% of the parent*/
  left:50%; /*make top and left 50% of the parent*/
  transform: translate(-50%,-50%); /*make element translate 50% of itself*/
}
```
