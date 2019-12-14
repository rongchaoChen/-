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
		

---



