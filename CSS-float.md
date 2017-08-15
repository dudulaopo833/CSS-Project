# CSS-Float 
* float设计目的是为了实现文字环绕，因为盒模型，所以需要破坏来实现文字环绕 　   
* float对自身有包裹性（砖头化），对父元素有破坏性(即不在遵循流体布局，而是悬浮在了流体布局上，可能导致父元素没有高度了，宽度还是保持以前的宽度)
* float的框可以向左向右移动， 直到它的外边缘碰到包含框或另一个浮动框的边框为止，所以如果两个元素都是float：left， 那么这两个元素又像流体布局那样顺序排版
* float有砖头化(display:block)，和去空格化，所以经常被滥用成砌砖头布局（固定高度和宽度），但是这个有一个致命的缺点就是去除了一块砖头，就整体都乱了
* 清楚浮动带来的影响，用clear，clear属性规定元素的哪一侧不允许其他浮动元素！所以可以在div上加一个clear：both来实现
* 清除float带来的影响，上门的方法会多了很多div，也可以用以下方法来实现：　　   
> Way1: 
  >> .clearfix:after{content:""; display: block; height: 0; overflow: hidden; clear: both;} --> IE8 +        
  >> .clearfix{*zoom:1} --> IE6/7      
  
> Way2: 
  >> .clearfix:after{content:""; display: table; clear: both;} --> IE8 +     
  >> .clearfix{*zoom:1} --> IE6/7     
* 最好是应用在流体布局中，不要砌砖头 --> TBC > 兼容性：--> TBC
* 两个块级元素是垂直布局的，用float就可以让他们在一行显示（如果两个加起来的宽度不大于父级元素！）
