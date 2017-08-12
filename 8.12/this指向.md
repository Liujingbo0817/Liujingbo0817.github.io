# this指向  
***
### 1.通过函数名直接调用  
//function声明函数  
`function fn(){`    
	`console.log(this);`  
`} `  
`fn();` 	 ** this -->  window **  
//自执行函数  
`(function () {console.log(this)})();` ** this --> window **
> 作为普通函数调用，这个时候this总是指向全局对象（在浏览器中即window对象）

### 2.通过方法调用  
// 对象方法调用    

`var person = {`  
	`run:function(){`  
		`console.log(this)`  
	`}`  
`}`  
`person.run()`  ** this --> person **  

// 事件绑定   

`var btn = document.getElementById("button")`  
`btn.onclick = function () {`  
    `console.log(this)` ** this --> btn**  
`}`  

// 事件监听  

`var btn = document.getElementById("button")`  
`btn.addEventListener('click', function () {`  
`console.log(this)`  **this --> btn**  
`})`
> 方法调用中谁调用this指向谁  

### 3.在构造函数或者构造函数原型对象中调用    
//不使用new  
`function Person (name) {`  
`console.log(this)`   **this -->  window**  
` this.name = name;`  
`}`    

`Person('inwe')`  

//使用new  
`function Person (name) {`  
`this.name = name`  
`console.log(this)`   **this -->  window**  
`self = this`  
`}`  
` var people = new Person('iwen')`  

`console.log(self === people)` ** true **  
> 这里new改变了this指向，将this由window指向Person的实例化对象people    
> 不使用new指向window  

### 4.通过call/apply调用  
// call()方法  
`function Cat(name){`  
`this.name = name;`  
`this.showName = function(){`  
`alert(this.name)`  **this -->  dog**  
`}`  
`}`  
`function Dog(name){`  
`this.name = name;`  
`}`  
`var cat = new Cat("小猫");`  
`var dog = new Dog("小狗");`  
`cat.showName.call(dog,"");`  
`原本执行结果应该弹出’小猫’，但是由于使用了call方法，相当于把cat下面的showName方法应用于dog,所以弹出的是‘小狗’`  

//apply()方法  
`function fn1(a,b){`  
`alert(this)`  **this --> document**  
`return a + b;`  
`}`  
`console.log(fn1.apply(document,[5,6]))`  
`弹出的是document，打印的数值为11`  
> 注意：  
	1.这里call()和apply()都是用来改变this指向的，两者的功能完全一样，只是参数不同      
	2.call第一个参数是this要指向的上下文，后面跟着的参数不固定，都是当成函数的参数传递进去  
	3.apply第一个参数也是this要指向的上下文，后面是一个数组或者类数组，数组的每一项按照顺序当成是函数的参数传递进去  
	
### 5.通过数组下标调用  
`function func(){`  
` console.log(this);`  

`}`    

`var arr = [func,1,2,3];`    

` arr[0]();`  ** // this --> arr **    

> 函数作为数组的一个元素，通过数组下标调用的：this指向这个数组  

### 6.回调函数（ setInterval setTimeout 等）
`function func(){`  
`console.log(this);`  
`}`  
`setTimeout(func,1000);`  **// this --> window**  
> 函数作为window内置函数的回调函数调用：this指向window
