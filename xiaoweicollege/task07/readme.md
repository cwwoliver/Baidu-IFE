* [任务七：实现常见的技术产品官网的页面架构及样式布局](https://cwwoliver.github.io/Baidu-IFE/xiaoweicollege/task07/task07.html)

设计稿是有一定宽度的，这个宽度为页面的最小宽度，也就是说，当浏览器窗口宽度小于设计稿宽度时，允许出现横向滚动条，页面内容宽度保持不变，但是当浏览器窗口宽度大于设计稿宽度时，页面部分内容的宽度应该保持和浏览器窗口宽度一致，具体哪些部分题目不做具体指明，看看大家的判断如何。

---

<p>笔记：</p>
<p>1.backgroud-size：100% 100%; CSS3新属性，本案采用的是img标签。</p>
<p>2.样式letter-spaceing设置的间距会出现在所有字母/字的后方，所以无法居中对齐。可以设置text-indent或不将最后一个字包含在内再进行居中对齐。</p>
<p>3.text-align：justify无法对只有一行的文字进行两边对齐。</p>
<p>4.appearance:none; -moz-appearance:none; -webkit-appearance:none;清除select默认样式</p>
<p>5.width：100%;text-align:center;脱标后文本居中</p>
<p>6.position:absolute;top:0;left:50%;margin-left:-元素宽度的一半px;定位后盒子居中</p>
