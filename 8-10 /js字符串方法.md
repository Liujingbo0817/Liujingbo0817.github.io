# js字符串方法
***
## 1.indexOf()
> 查找字符串出现的位置  返回该字符串的下标  
 如果查询的字符在对应的字符串里找不到，则返回-1

	参数可以传两个 
		第一个参数：要查找的字符串  
		第二个参数(可选)：开始查找的下标位置
	注意：字符串里放入空格也占位置
 eg:  
	 `var str = "good good study";`  
	 `console.log(str.indexOf("d",6));`  
	    `打印结果为8.`
## 2.lastindexOf()
> 跟indexOf()类似，在一个字符串中的指定位置从后向前搜索
	
	整体查找的话，无论是从前往后找，还是从后往前找，返回的都是第一个字母出现的下标
 eg:  
 `var str = "good good study";`  
  ` console.log(str.lastIndexOf("g"));`  
	    `打印结果为5.`
## 3.slice()
> 截取字符串的某一部分

	有两个参数
		1.表示开始截取的下标位置
		2.表示截取到的下标位置
	注意：
		1.所有的截取字符串的操作，截取的范围都是前闭后开
		2.该方法不会改变原来的字符串
		3.如果只传递一个参数，那这个参数会视为开始截取的下标，默认截取到字符串的最后一位
		4.如果没有参数的情况，那默认截取整个字符串
 eg:  
 `var str = "day day up";`  
	   `console.log(str.slice(0,5));`  
	   `console.log(str);`  
	   ` console.log(str.slice(0)); `  
	   `打印结果分别为：day d`  
	 ` day day up`  
	  ` day day up`
## 4.substring()
> 截取字符串

	有两个参数:
		1.表示开始截取的下标位置
		2.表示截取到的下标位置
	注意：
		1.该方法不会改变原来的字符串
		2.如果只传递一个参数，那这个参数会视为开始截取的下标，默认截取到字符串的最后一位
		3.如果没有参数的情况，那默认截取整个字符串
		4.substring()方法会自动比较两个参数的大小，如果我们给的第一个参数大于第二个的话，那该方法会自动进行参数位置的调整  如果有负数会按照0来解析
 eg:    
`var str = "day day up";`  
`console.log(str.substring(0,5));`  
`console.log(str);`  
`打印结果为day d和 day day up`
## 5.split()
> 把字符串分割成字符串数组

	如果没有参数，那原字符串就是转化数组的唯一一项内容
	如果有一个参数，那这个参数就是字符串分割的依据
	如果有第二个参数，那第二个参数表示数组的长度
 eg:  
 `var str = "1234554321";`  
 `console.log(str.split("4"));`  
 `console.log(str.split("4",2));`  
 `打印结果为["123", "55", "321"]和["123", "55"]`
## 6.charAt()
> 返回下标位置所对应的字符

	参数：1个，表示要获取字符的下标  
	如果不写参数，默认返回字符串第一位上的字符
 eg:  
 `var str = "nihaoma";`  
 `console.log(str.charAt(0));`  
 `打印结果为n`
## 7.charCodeAt()
> 返回下标位置对应字符的Unicode编码  
 eg:  
 `console.log(str.charCodeAt(0));`  
 `打印结果为110`

## 8.replace()
> 字符串替换

	两个参数:
		1.被替换的字符串
		2.替换的字符串
	不会改变原字符串
 eg:  
 `var str = "你可爱吗";`  
 `console.log(str.replace("吗","呀"));`  
 `打印结果为”你可爱呀”`
## 9.toLowerCase()
> 把原字符串转换为小写

	不会改变原字符串
 eg:  
 `var str = "YEAH";`  
 `console.log(str.toLowerCase());`  
 `打印结果为yeah`
## 10.toUpperCase()
> 把原字符串转换为大写

	不会改变原字符串
 eg:  
 `var str = "yeah";`  
 `console.log(str.toUpperCase());`  
 `打印结果为YEAH`
## 11.trim()
> 去掉字符串前后的空格  
 eg:  
 `var str = " hello world " ;`  
 `console.log(str.length);`  
 `console.log(str.trim());`  
 `console.log(str.trim().length);`  
 `最后打印结果为13、hello world、11`
