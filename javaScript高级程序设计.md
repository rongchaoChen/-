阅读笔记
-----
*	延迟脚本 defer属性. 表名脚本在执行时,会被延迟到整哥页面都被解析完毕后在运行,相当于告诉浏览器立即下载,但是延迟执行.会按照出现的顺讯先后执行,而且适用于外部引入的js文件, 如果是在html 页面中直接引入,会忽略.
```

		 <script type="text/javascript" defer="defer" src="example1.js"></script>  
		 <script type="text/javascript" defer="defer" src="example2.js"></script>   
*	异步脚本async 和延迟脚本defer 一样 ,告诉浏览器立即下载脚本但是延后执行,和defer 不同的是,不能按照脚本的先后顺序执行.
```

		 <script type="text/javascript" async src="example1.js"></script> 

---
####3 - 基本概念
* javascript 中区分大小写
* 标识符
	* 第一个字母必须是一个字母,或者下划线,或者美元$ 符号
	* 其他的字符可以是字母,下滑先,美元符号或数字
	* 驼峰式命名规则,第一个单词后,的单词首字母大写
* 数据类型
	* undefined 
	 ```
		
				-- 进行了数据声明,但是没有进行初始化赋值
				console.log(a);	-- undefined
				var a = 1;  或者 var a; 
				-- 在es6 中上述代码会报错
	* Null
	* booleab
	* number
	* String
	* Object
	```
* typeof();因为JavaScript 是松散型语言所以,需要该方法检测变量的数据类型
	* undefind  --  该值未定义
	* boolean 	-- 如果这个值是布尔类型
	* string	-- 字符串类型
	* number	-- 数值类型
	* object	-- 对象或者null
	* function	-- 函数类型
	
*	函数
	*	使用function 关键字来声明,后跟一组参数以及函数体,
	*	不能把函数喝参数命名为eval 或者arguments
	*	不能出现两个参数命名同名
* 数值类型
	* 非数值转换为数值
		* Number() 
	
		 ````
			
				如果布尔值,true 和false 会被专转换成1和0
				let num = Number(true) -- 1
				let num2 = Number(false_ -- 0
				如果是单纯的数值,只是简单的传入好肉返回
				如果是null 返回0
			如果是undefined 返回NaN 
		
		* parseInt()````
			
				在转换字符串的是,会忽略到前面的空格
				let num = parseInt("  123") -- 123
				如果第一个不是数字字符或者是符号,会返回NaN,如果前面是数字字符,后面是非数字字符则保留数字字符,忽略后面非数字字符
				let num2 = parseInt("123abc"); --123	
			
		* parseFloat()
	
	* String
	* toString
	
				let num = 11;
				let str1 = num.toString();  -- '11'
				或者是string 可以把任何类型的值转换成字符
				let str1 = String(true); -- 'true'
				let str2 = String(null); -- 'null'
				let str3;  -- undefined 该值未定义式
	*  Object
		
	*  在js 中对象其实就是一组数据和功能的集合,对象可以通过执行new 操作要创建的对象类型的名称来创建,而创建的Object类型的实例为其添加属性和方法
		
	* 布尔操作符
		* 非(not)!
	
				在js 中无论这个值是一个什么值,都会将它转换一个布尔值然后取反
				!false	-- true
				
			!! 该操作符会基于第一个逻辑操作符返回一个布尔值,然后第二个逻辑非 ! 再对该布尔值取反
				!! false -- false
	
		* 与(and) &&
		
				let res = true && false;
				如果第一个为true的时候会去判断第二个操作数是否为true,如果都为true 则结果为true
			如果第一个操作数为false ,那么后面的也不会去判断直接返回false
		
	* 或(or) ||
	
	
				let res = true || false;
				如果第一个操作数为false第二个为true则返回true
				如果第一个操作数为true 则直接返回true
	

##### 作用域和内存

1. 引用类型和基本数据类型

   1. 基本数据类型 undefined, null, boolean, number, 
   2. 引用类型: 是保存在内存中的对象,和其他语言不同的是,javascript 不允许直接访问内存中的位置,也就是说不能直接草对象的内存空间,在操作对象时,实际上是在操作对象的引用,而不是实际的对象

2. ```
   var person = new Object();
   person.anme = "rc";
   console.log(person.anme);
   
   在上面的代码说中,创建了一个object对象,并保存在了变量person中.
   然后为对象添加了name 属性,然后又调用了该属性.如果对象不销毁,或者删除,这个属性则一直存在
   
   -------------------
   但是我们不能给基本数据类型添加属性,虽然这样不会导致错误
   var names = "rcs";
   names.age = 17;
   console.log(names.age); // undefined
   
   ```

3. 复制变量值

   - 引用数据类型和基本数据类型出了保存的方式不同之外,在从另外一个变量向另外一个变量复制基本类型值和引用类型值也不同

   - 如果一个变量向另外一个变量赋值基本类型的值,会在变量上创建一个新的值,然后把该值复制到新变量分配的位置上

   - ```
     var num1 = 2;
     var num2 = num1;
     console.log(num1); -- 2
     console.log(num2); -- 2
     console.log("---");
     num2 = 5;
     console.log(num2);  -- 5
     console.log(num1);  -- 2
     ```

     - ![](C:\Users\chenr\Desktop\阅读\javascript高级程序设计\变量.png) 

   - 如果是引用类型的话,同样会将存储在变量中的值复制一份放到新变量分配的空间中,不同的是这个值的副本实际是一个执政,而这个指针会指向存储在堆中的一个对象,赋值结束后,起始两个变量还是引用的一个对象,如果改变其中一个,另外一个也会被改变		

     - ```
       var obj1 = new Object();
       var obj2 = obj1;
       obj1.name = "rc";
       console.log(obj1, obj2); -- obj1 = rc obj2 = rc
       obj2.name = "newRc";
       console.log(obj1, obj2); -- obj1 = newRc obj2 = newRc
       ```

   - 类型检测 **instanceof**

     - typeof 则是用来检测基本数据类型的
     -  用来检测引用数据类型,知道它是什么类型的对象
       - 怎么识别: 根据它的原型链来识别,如果是条原型链上的对象则返回true,反之为false

