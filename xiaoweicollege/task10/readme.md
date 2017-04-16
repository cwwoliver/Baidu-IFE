Flex布局基本概念
Markdown

弹性容器(Flex container)

通过设置 display 属性的值为 flex 或 inline-flex
来定义弹性容器。

弹性项目(Flex item)

弹性容器里子元素自动成为弹性项目，并且弹性项目的float、clear和vertical-align属性将失效。

轴(Axis)

主轴（main axis）
交叉轴（cross axis）
这个2个轴决定了容器里的项目整体布局效果。
Flex容器属性
flex-direction
flex-wrap
flex-flow
justify-content
align-items
align-content
flex-direction

flex-direction决定主轴方向，默认情况下，元素都是从左到右地分布在主轴上

4个取值：

flex-direction: row | row-reverse | column column-reverse;

row（默认值）：主轴为水平方向，起点在左端。
row-reverse：主轴为水平方向，起点在右端。
column：主轴为垂直方向，起点在上沿。
column-reverse：主轴为垂直方向，起点在下沿。
Markdown
Markdown

flex-wrap

是否可以换行（默认不换行），以及如果可以换行，如何排列

3个取值

flex-wrap: nowrap | wrap | wrap-reverse;
nowrap: 默认不换行
wrap: 可以多行，第一行在上方
wrap-reverse: 可以多行，第一行在下方
Markdown

flex-flow

flex-direction 和 flex-wrap 的简写,默认row nowrap

flex-flow: <flex-direction> || <flex-wrap>;
justify-content

决定项目在主轴上的对齐方式

5种取值：

justify-content: flex-start | flex-end | center | space-between | space-around;

flex-start: 左对齐（默认）
flex-end: 右对齐
center: 居中对齐
space-between: 两端对齐，项目之间的间距相等
space-around: 均匀对齐，每个项目两端的间距相等
Markdown

align-items

决定交叉轴的对齐方式

align-items: flex-start | flex-end | center | baseline | stretch;

flex-start: 交叉轴起点对齐
flex-end: 交叉轴终点对齐
center: 交叉轴居中对齐
baseline: 第一行文字的底部对齐
stretch: （默认）如果项目木有设置高度或者高度为auto,那么项目拉伸充满整个交叉轴空间
Markdown

注意：记住justify-content是沿着主轴的，align-items是沿着交叉轴的，而flex-direction是转换主轴的。这对整体移动元素很关键。

Markdown

align-content

定义多行轴线的对齐方式（如果只有一行，该属性不起作用）

align-content: flex-start | flex-end | center | space-between | space-around | stretch;

flex-start: 交叉轴起点对齐
flex-end: 交叉轴终点对齐
space-between: 交叉轴两端对齐，行之间间距相等
space-around: 交叉轴均匀对齐，行两端间距相等
stretch: 平均分配交叉轴空间，相邻行间距相等（默认，前提如果项目木有设置高度或者高度为auto）
注意：当项目的高度之和小于容器的高度并且项目高度固定时，会以交叉轴起点对齐并且项目之间间距相等，但不是flex-start对齐方式，如果此时设置flex-start是没有间距的。

这里项目设置了固定高度，所以stretch无效
Markdown

Flex项目属性
order
align-self
flex-grow
flex-shrink
flex-basis
order

根据order的值定义项目排列顺序。数值越小，排列越靠前，默认为0

Markdown

align-self

定义单个项目在交叉轴的对齐方式，可覆盖align-items属性
取值和align-items一样：

Markdown

flex-grow

定义项目放大比例，默认为0，当容器有剩余空间时不放大.
重点在于，每个方块的 flex-grow 和其他方块的是成比例的。

flex-grow: <number>; /* default 0 */
第3个项目flex-grow 为3,其他5个项目为1，共 5+3 = 8,第3个占比为3/8,其他为1/8.

Markdown

flex-shrink

定义项目缩小比例。默认为1，随着容器缩小而等比例缩小。
如果设置为0，项目将不缩小。
基本和flex-grow类似，不过一个是缩小，一个是放大。

flex-shrink: <number>; /* default 1 */
Markdown

flex-basis

定义项目占据的主轴空间（main size）,默认是auto.
还有就是它可能被其他flex属性所影响。

 flex-basis: <length> | auto; /* default auto */
下面这个 GIF 表示的是它和 width 属性是可以互换的。（但是不完全是这样）
Markdown

注意：flex-basis 和 width 不同的地方是，它是和 flex 坐标轴保持一致的，flex-basis是影响主轴上大小。

下面保持flex-basis不变，改变主轴方向
Markdown

这个时候改变height，而不是width，flex-basis 根据 flex-direction 的不同会影响到 width 或者 height。

flex

flex-grow, flex-shrink 和 flex-basis的简写，默认值为0 1 auto。后两个属性可选。

/*简写
auto (1 1 auto) 
none (0 0 auto)
*/
.square#one {
  flex: 2 1 300px;
}
.square#two {
  flex: 1 2 300px;
}
Markdown

最后注意：主轴和交叉轴需要特别注意方向，因为flex属性大部分是作用与轴上的,而方向不同就会导致不同布局效果。

参考链接
通过动图形象地为你介绍 flexbox 是如何工作的（一）
通过动图形象地为你介绍 Flexbox 是如何工作的（二）
Flex 布局教程：语法篇
flex基础布局详解
使用 CSS 弹性盒子
