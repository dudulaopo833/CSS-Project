# CSS-Float 
* float设计目的是为了实现文字环绕，因为盒模型，所以需要破坏来实现文字环绕 　   
* float对自身有包裹性（砖头化），对父元素有破坏性(即不在遵循流体布局，而是悬浮在了流体布局上，可能导致父元素没有高度了，宽度还是保持以前的宽度)
* float的框可以向左向右移动， 直到它的外边缘碰到包含框或另一个浮动框的边框为止，所以如果两个元素都是float：left， 那么这两个元素又像流体布局那样顺序排版
* float有砖头化(加了之后display会变成block)，和去空格化(换行符不占任何实质位置，但是nbsp会)，所以经常被滥用成砌砖头布局（固定高度和宽度），但是这个有一个致命的缺点就是去除了一块砖头，就整体都乱了
* 清楚浮动带来的影响，用clear，clear属性规定元素的哪一侧不允许其他浮动元素！所以可以在div上加一个clear：both来实现, 这个div的margin-bottom会和下一个元素的margin-top重叠！
* 清除float带来的影响，上门的方法会多了很多div，也可以用以下方法来实现：　　   
> Way1: 
  >> .clearfix:after{content:""; display: block; height: 0; overflow: hidden; clear: both;} --> IE8 +        
  >> .clearfix{*zoom:1} --> IE6/7//*号只有IE支持 
  
> Way2: 
  >> .clearfix:after{content:""; display: table; clear: both;} --> IE8 +     
  >> .clearfix{*zoom:1} --> IE6/7     
* 最好是应用在流体布局中，不要砌砖头 --> TBC 
> 效果一： 一个父元素，包含一个图片和其他都是文字的div或者p(display：block)，其中图片有float样式，那么图片后面的其他文字的div/p就会环绕图片排列       
> 效果二： 一个父元素，有两个图片div，再说一个文字div，两个图片的float分别是left和right，文字的text-align是center，那么就实现了左右图片，中间文字效果。 图片一定要在文字之前，要不然文字后面的图片都是换行显示了
```
<div class="test-box">
	<img style="float:left" src="http://img.mukewang.com/53d60af3000171a002560191.jpg"/>
	<img style="float:right" src="http://img.mukewang.com/53d60af3000171a002560191.jpg"/>
	<p style="text-align: center">一直有这么一个美丽的误会，说我是张含韵的忠实粉丝，因为左边这种张含韵萝莉时候的照片频繁出现在我的文章中。</p>
	<p>一直有这么一个美丽的误会，说我是张含韵的忠实粉丝，因为左边这种张含韵萝莉时候的照片频繁出现在我的文章中。</p>
</div>
```
> 效果三： 图片左侧固定，右侧是流体布局
```
.mib_head_a { width: 56px; float: left; }   
/* 下面这个是流体布局写法 */
.mib_feed_flow { margin-left: 76px; }
```
> 效果四： 图片右侧固定，左侧流体布局
```
Way1： 
/* 下面这个是右浮动，改变DOM位置的流体布局写法 */
.mib_head_r { width: 56px; float: right; }
.mib_feed_flow { margin-right: 76px; }
Way2：
/* 下面这个是左浮动，不改变DOM位置的流体布局写法 */
.mib_full_float { width: 100%; float: left; }
.mib_head_l { width: 56px; float: left; margin-left: -56px;} // margin-left:-56px 使得在同一行显示，如果不设置，那么会跑到第二行，因为上一行100%宽度
```
> 效果五：图片左侧，右侧流体布局； 但是左侧大小改变，右侧自适应
```
.mib_head_a { float: left; margin-right: 20px; }
/* 下面这个是固定布局写法 */
.mib_cell { display: table-cell/row; *display: inline-block; width: 2000px; *width: auto; }
```
* 两个块级元素是垂直布局的，用float就可以让他们在一行显示（如果两个加起来的宽度不大于父级元素！）
