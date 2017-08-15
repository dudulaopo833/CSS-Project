# CSS-Float 
* float设计目的是为了实现文字环绕，因为盒模型，所以需要破坏来实现文字环绕 　   
* float对自身有包裹性（砖头化），对父元素有破坏性(即不在遵循流体布局，而是悬浮在了流体布局上)
* 如果两个元素都是float：left， 那么这两个元素又像流体布局那样顺序排版
* float有砖头化(display:block)，和去空格化，所以经常被滥用成砌砖头布局（固定高度和宽度），但是这个有一个致命的缺点就是去除了一块砖头，就整体都乱了　  
* 清除float带来的影响，一般用以下方法来实现：　　   
> Way1: 
  >> .clearfix:after{content:""; display: block; height: 0; overflow: hidden; clear: both;} --> IE8 +        
  >> .clearfix{*zoom:1} --> IE6/7      
  
> Way2: 
  >> .clearfix:after{content:""; display: table; clear: both;} --> IE8 +     
  >> .clearfix{*zoom:1} --> IE6/7     
* 最好是应用在流体布局中，不要砌砖头 --> TBC > 兼容性：--> TBC
