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
####基本概念
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

---
####变量和作用域


