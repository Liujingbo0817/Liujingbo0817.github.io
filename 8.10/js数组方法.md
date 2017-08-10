#js数组方法
***
##1.join()
>把数组转换成字符串

	如果不写参数，默认以逗号分隔
	可以接受参数 表示以这个指定的参数进行分隔
eg:  
`var arr = [1,2,3,4];`  
`console.log(arr.join().length);`  
`console.log(arr.join('-'));`  
`打印结果为7、1-2-3-4`
##2.reverse()
>将字符串逆序

	会修改原数组
eg:  
`var arr1 = ["nihaoma","wobuhao"];`  
`console.log(arr1.reverse());`  
`console.log(arr1);`  
`打印结果为["wobuhao","nihaoma"]和["wubuhao","nihaoma"]`
##3.sort() 
>将数组排序

	会改变原数组
	
	sort()方法如果想按照从大到小或者从小到大的方式排序，需要我们传递参数，参数的形式是函数
	升序
	function asce (a,b) {
		return a-b;
	}
	降序
	function desc (a,b) {
		return b-a;
	}
eg:  
`var arr2 = [3,10,23,8,12];`  
`console.log(arr2.sort());`  
`console.log(arr2.sort(asce));`  
`console.log(arr2);`  
`打印结果分别为[10,12,23,3,8]、[3,8,10,12,23]、[3,8,10,12,23]`
##4.contact()
>将数组合并

	不会修改原数组
	contact()方法参数可以是数字，也可以是数组
	如果是一维数组的话，会把合并数组拉伸，跟原数组合并为同一个数组
	如果是二维数组或者多维数组的话，只会将合并数组的第一层拉伸合并，保留内层的数组
eg:  
`console.log(arr3.concat([6,5]));`  
`console.log(arr3.concat([6,[1,5]])); `  
`打印结果为[1,2,3,6,5]、[1,2,3,6[1,5]]`
##5.slice()
>返回数组的某一部分 

	不会改变原数组
	两个参数:
		第一个表示开始截取的位置
		第二个表示截取到的位置，前闭后开
	当只有一个参数时，这个参数表示开始截取的下标位置，一直截取到数组的最后一项
eg:  
`var arr = ["123","456","789","1","2","3"];`  
`console.log(arr.slice(2,5));`  
`console.log(arr.slice(1));`  
`console.log(arr.slice(arr));`  
`打印结果分别为["789","1","2"]、["456","789","1","2","3"]、["123","456","789","1","2","3"]`
##6.splice()
>数组拼接

	会修改原数组
	有三个参数:
		1.表示插入的下标位置
		2.删除多少项
		3.表示插入的内容
eg:  
`var arr = ["i","am","a","clever","girl"];`   
`arr.splice(4,1,"boy");`  
`console.log(arr);`  
`打印结果为["i","am","a","beautiful","boy","girl"]`
##7.pop()
>移除数组中的最后一个元素并返回该元素
	
	会改变原数组
eg:  
`var arr = [1,2,3,4,5];`  
`console.log(arr.pop());`  
`console.log(arr);`  
`打印结果为5、[1,2,3,4]`
##8.shift()
>移除数组中的第一个元素并返回该元素

	会改变原数组
eg:    
`var arr = [1,2,3,4,5];`  
`console.log(arr.shift());`  
`console.log(arr);`  
`打印结果为1、[2,3,4,5]`
##9.push()
>往数组的最后添加一项内容，返回的是新数组的长度

	会修改原数组
eg:  
`var arr = ["there","is","a"];`  
`console.log(arr.push("yes"));`  
`console.log(arr);`  
`打印结果为4、["there","is","a","yes"]`
##10.unshift()
>往数组的第一项添加内容,返回的是新数组的长度

	会修改原数组
eg:  
`var arr = [1,2,3,4];`  
`arr.unshift(0);`  
`console.log(arr);`  
`打印结果为[0,1,2,3,4]`
##11.indexOf()
>检测数组是否包含某一项内容，如果是，返回下标，如果没有，返回-1  
eg:  
`var arr=["aa","bb","cc"];`  
`console.log(arr.indexOf("dd"));`  
`打印结果为-1`

##12.lastIndexOf()
>从后往前查找  跟indexOf()类似
eg:  
`var arr=["aa","bb","cc"];`  
`console.log(arr.lastIndexOf("cc"));`  
`打印结果为2`

#新增数组方法
***
##1.forEach()
>遍历数组

	参数是匿名函数，匿名函数接受1-3个形参
	第一个形参表示数组的每一项内容
	第二个形参表示每一项内容所对应的下标
	第三个形参表示原数组
eg:  
`var arr = ["aaa","ddd","fff","ggg"];`  
	`arr.forEach(function(x,y,z) {`  
	`console.log(x,y,z);`  
	`})`  
`打印结果为aaa 0 ["aaa","ddd","fff","ggg"]`
##2.map() 
>映射

	参数接受一个匿名函数，匿名函数可以传递两个形参
	第一个 原数组里的每一项内容
	第二个 原数组里每一项内容对应的下标
eg:  
`var arr1 = [1,2,3,4,5,6];`  
`arr1.map(function(x,y) {`  
`console.log(x,y);`  
`})`  
`打印结果为1 0、2 1、3 2、4 3、 5 4、 6 5`
##3.filter() 
>过滤

##4.every()
##5.some()