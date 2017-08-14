# DOM知识点  
***
## 1.定义  
> DOM(文档对象模型(Document Object Model))   
是W3C组织推荐的处理可扩展标志语言的标准编程接口。  
DOM w定义了所有 HTML 元素的对象和属性，以及访问它们的方法。

## 2.分类  
> 按层级分  

	父节点  
	子节点  
	兄弟节点  
> 按节点类型分  

	1.元素节点
	2.属性节点
	3.文本节点
	8.注释节点
	9.document节点  

## 3.属性  
> innerHTML属性  

	获取元素内容的最简单方法是使用 innerHTML 属性。  
	innerHTML 属性对于获取或替换 HTML 元素的内容很有用。  
	innerHTML 属性可用于获取或改变任意 HTML 元素，包括 <html> 和 <body>。  
> nodeValue 属性

	nodeValue 属性规定节点的值。  
	元素节点的 nodeValue 是 undefined 或 null
	文本节点的 nodeValue 是文本本身  
	属性节点的 nodeValue 是属性值
> nodeType 属性

	nodeType 属性返回节点的类型。nodeType 是只读的。


## 4.获取  
> children/childNodes 获取指定元素的第一层子节点  

	区别：
		1.children 在标准浏览器和IE9下，不会造成空白文本解析，获取到的是真实的子节点。（不支持IE6/7/8）
		2.childNodes 会解析空白文本节点  
> firstChild/firstElementChild 获取指定元素的第一个子节点  

	区别：
		1.firstChild 在标准浏览器和IE9下会获取到空白文本节点
		2.firstElementChild 标准下获取第一个子元素节点，IE6/7/8不支持
> lastChild/lastElementChild 获取指定元素的最后一个子节点  

	区别：
		1. lastChild 在标准浏览器和IE9下会获取到空白文本节点  
		2.lastElementChild 标准下获取最后一个子元素节点，IE6/7/8不支持  
> previousSibling/previousElementSibling 获取指定元素的上一个兄弟节点  
> nextSibling/nextElementSibling 获取指定元素的下一个兄弟节点  

	区别同上
> parentNode 获取指定元素的父节点  
> offsetParent 获取离指定元素最近的具有定位属性的祖先节点  

	以上两个属性都是把获取到的元素结构整体返回，不仅仅只是返回一个标签  
> 获取元素属性的方式  

	1.元素.属性名
		注意：如果获取的是元素的class的话，在写的时候必须是className，获取不到非标准属性
	2.["属性名"]
	3.getAttribute("属性名")
		注意：可以获取到元素的自定义属性
	4.setAttribute("属性名"，"属性值")  设置元素属性
	5.removeAttribute("属性名")  移除元素属性
	注意:attributes属性能访问到元素上所有的属性,返回的是一个类数组,我们可以通过下标的形式拿到每一个属性。  

## 5.增删改查
> 创建节点

	document.createElement(' ');
> 给指定元素追加子节点  

	appendChild()
> 插入元素  

	insertBefore(插入的元素，参照元素)
> 移除子节点  

	removeChild()
> 替换子节点  

	replaceChild(替换元素，被替换元素)
> 克隆节点  

	cloneNode()  接受一个布尔值作为参数  
	当参数为true时，会克隆元素的innerHTML  
	false不会，默认是false  
> 判断指定元素是否拥有子节点  

	hasChildNodes()  
	返回布尔值true或false  
	
## 6.获取窗口可视区域宽高/页面滚动高度  
> 调整窗口大小时触发的事件  

	window.onresize = function  () {
		
	}
> 获取浏览器窗口可视区域宽度/高度  

	document.documentElement.clientWidth/clientHeight
> 获取页面滚动高度

	document.documentElement.scrollTop

	












	
