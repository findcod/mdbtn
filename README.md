# mdbtn.js
一个生成material-design的按钮效果的js插件

~~不要问我为什么没有预览图~~
好吧现在来这里看吧
http://iwyvi.github.io/mdbtn/

#简介
mdbtn使用canvas绘制按钮按下后的波纹效果

按钮在按下时波纹展开速度较慢，且展开后不消失；松开或者离开按钮则波纹速度会加快，同时在覆盖完空间后自行消失

#基本使用方法
导入`mdbtn.js`

将需要用到效果的部分添加`mdbtn`的class

在body最后加入`mdbtn.init();`

在元素上添加`data-color=""`可以为元素设置按下后的波纹颜色（可以使用十六进制颜色或者rgb颜色）

#接口和参数
`mdbtn.init(elements,option)`

elements(string):可选，用于设置添加效果的类名（默认为mdbtn）

option(object):可选，用于配置mdbtn的属性（属性配置见下面的卡片）

`mdbtn.setOption(option)`

option(object):必选，用于配置mdbtn的属性（属性配置见下面的卡片）

`mdbtn.addElements(elements)`

elements(string):必选，添加class为elements的所有元素

#一些问题的说明
因为是js初学者，所以肯定存在许多bug，代码写的也比较乱

每个mdbtn元素都会强制加上`overflow:hidden`和`position:relative`，如果有其他css请再在外面套一层

~~当元素未指定width和height时加入圆角，可能会使里层canvas超出圆角显示（我并不知道为什么），然后似乎将元素设置为`display:inline-block`可以解决~~
这一部分以强行给canvas设置圆角解决
 
**~~然后目前还发现有click事件在firefox下有问题（其他浏览器似乎都没有），目前只能用mouseup来暂时解决~~**
**目前又在js里面加了Firefox检测，如果在火狐下则再调用一次元素的click()**

**2016.4.8 今天又发现在Safari里也有这个问题所以也是这样处理了一下**

同时代码中HEX与RGB颜色转换代码参照修改了
http://www.zhangxinxu.com/wordpress/2010/03/javascript-hex-rgb-hsl-color-convert/
这里的代码
