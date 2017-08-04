# 函数（function）

函数定义的基本格式：

``` 
function function_name() 
{
	conmmand1
	conmmand2
	...
}
``` 

## 函数的返回值

函数可以通过`return`和`echo`返回参数。

`return`只能返回整数（0-255），使用`$?`的方式调用其返回值。

例如：

``` 
#!/bin/bash

function func2() 
{
	echo "please enter the first number:"
	read num1
	
	echo "please enter the second number:"
	read num2

	echo "the numbers are $num1 and $num2"
	thesum=$(($num1+$num2))
	return $thesum
}

func2

echo $?
```

`echo`可以返回字符串，使用`$(function_name)`调用其返回值，其返回值是一个数组，里面包含`echo`的所有返回值。

例如：

``` 
#!/bin/bash

function func3()
{
	echo "string1"

	echo "string2"

	echo "string3"	
}

func3

result=$(func3)
echo $result
``` 

其结果为：

> string1
> 
> string2
> 
> string3
> 
> string1 string2 string3

## 函数的参数传递

函数的参数传递和脚本的参数传递类似，调用方式也类似，例如：

``` 
#!/bin/bash

function func4() 
{
	echo "the first param is $1"
	echo "the second param is $2"
	echo "the third param is $3"
	echo "the fourth param is $4"
	echo "the fifth param is $5"
	echo "the sixth param is $6"
	echo "the seventh param is $7"
	echo "the eighth param is $8"
	echo "the ninth param is $9"
	echo "the tenth param is $10"
	echo "the tenth param is ${10}"
	echo "the eleventh param is ${11}"
	echo "all the param are $*"
}

func4 1 2 4 4 6 3 5 7 4 637824 234
``` 

其结果为：

> the first param is 1
> 
> the second param is 2
> 
> the third param is 4
> 
> the fourth param is 4
> 
> the fifth param is 6
> 
> the sixth param is 3
> 
> the seventh param is 5
> 
> the eighth param is 7
> 
> the ninth param is 4
> 
> the tenth param is 10
> 
> the tenth param is 637824
> 
> the eleventh param is 234
> 
> all the param are 1 2 4 4 6 3 5 7 4 637824 234