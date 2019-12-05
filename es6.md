#### let 和  const
----
1.  let 和 var 一样, 但是用来声明的变量的作用域不一样 , var声明的是全局变量,let 声明只在所在代码块有效

```

	{
		let a = 1; -- 不能再外部访问
		var b = 1; -- 可以在外部访问
	}	

* 不能存在重复变量声明
```

		var a = 1; -- 
		var a = 2; -- 允许
		let a = 1;-- 报错
		let a = 2;

* 结构赋值
	* 在es6 中允许按照一定模式,从对象和数组中提取值,对变量进行辅助.
```

			-- 以前
			let a = 1;
			let b = 2;
			-- es6
			let [a,b] = [1,2];
	*  这种模式匹配,只要等号两边的模式相同,左边的变量就会被赋予对应的值 或者可以自定义指定值
```

			let [a,b = 2] = [1] -- 输出结果 a=1, b=2
	*	如果结构不成功,既没有定义值,左边也没有找到右边对应的值, 则为undefined. 如果自定义了值,但是左边的变量,找到匹配到了右边的值,则自定义的值会被覆盖
```

			let [a, b = 2] = [1,3]; -- a = 1 , b = 3
	*	不完全解构,左边的只能匹配到右边一部分的数组这种情况下,依然可以解构成功
```

			let[a, b] = [1,2,3];  -- a=1, b=2,
			let[a,[b],d] = [1,[2,4],5] -- a=1,b=2,d = 5

	*	对象解构赋值
		*	对象解构赋值和数组解构赋值不同,赋值解构赋值是按顺讯来排列的,变量的值由他的位置来决定,但是对象的属性没有次序,必须和属性同名,才能取到正确的值
	```

				let {foo,bar} = {foo = 'aaa', bar = 'bbb'} -- foo=aaa,bar =bbb
				let{foo,bar} = {foo = 'aaa'} -- foo = aaa, bar = undefined

		*	对象的解构赋值,是先找到同名属性,然后在付给对应的变量,真正被赋值的是后者,而不是前者
		*	嵌套解构
```

				let obj = {
					p :[hello],
					{y : word}
				}
				-- 结构赋值
				let {p : [x, {y}]} = obj  --- x = hello, y = word

*	字符串遍历接口
```

		for(let bianliangming of 需要遍历的对象)

	* at()
	
		*	在es5 中提供了charAt 方法,返回字符串给定位置的字符,但是该方法不能识别码点大于 0xffff 的字符(这个方法好像要子啊github 中下载进来,具体没去尝试, 先记录下来)
```

				"abc".charAt(0) -- 返回a
				"吉".charAt (0) -- 返回utf-16编码,无法显示
	
				"abc".At(0)  -- 返回a
				"吉".charAt (0) -- 返回吉
	*	include() ,startWidth(), endsWith()S
		*	之前在js 中可以用indexOf()方法来查找一个字符串是否包含在另外你一个字符串在中.现在ES6中又提供了上面三种方法
```

				-- indexOf
				let str = "hello";
				let indexStr = str.indexOf("需要查找的字符串");
				-- ES6  这三个方法都支持的第三个参数
				str.includes("o");		-- 表示在字符串中是否找到了该字符串,找到了返回true,反之返回false
				str.startWith("h");		-- 表示字符串是否在开头,找到返回true,反之返回false
				str.endsWith("o");		-- 表示字符串是否在结尾,找到返回true, 反之但会false
		* repeat()  表示原字符串重复n次
```

				"hello".repeat(2)  --- hello hello
				"hello".repeat(2.9) --  hellohello 如果是小数,则会取整,不会四合五入, 如果传入的是负数,或者Infintiy则会报错
		* padStart(), padEnd(),默认字符串补全功能 ,在某个字符串指定长度不够的时候 ,会在头部或者尾部补全	
````

				console.log("x".padStart(5, "ab"));		----ababx
				console.log("x".padEnd(5, "ab")); 		---- xabab
				-- padStart,padEnd 一共接收两个参数,第一个参数用来指定字符串的最小长度,第二个参数用来补全字符,

				-- 如果原字符串的长度等于或者大于指定的最小长度,则返回原字符串
				console.log("xxxxxx".padStart(5, "ab")); --xxxxxx
				console.log("xxxxx".padEnd(5, "ab"));	--xxxxx
				
				-- 如果用来补全的字符串和字符串两者的长度之和超过了指定的最小长度,则会截去超出位数的补全字符串.
				console.log("abc".padEnd(10, "0123456789"));	--abc0123456
				-- 如果省略第二个参数,默认使用空格补全长度
		*	模板字符串,以前我们对于字符串和变量拼接的时候都是这样" " + 变量 + "",在ES6中我们可以这样
```

				`字符串${变量}字符串   -- 就不可以不用再字符拼接了  
			

									