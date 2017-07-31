# shell variables

## 定义变量

1.显示定义：

```
var_name="variable name"
```

2.隐式定义：

```
for via_name in `ls /etc` # 这里是英文的反引号，tab键上面那个，不是单引号
	do
		echo $via_name
	done
```

### 关于只读变量

1.定义只读变量

``` 
readonly pi=3.14
``` 

2.删除只读变量

``` 
cat << EOF| sudo gdb 
attach $$ 
call unbind_variable("pi") 
detach 
EOF
``` 

## 变量的调用

变量的调用使用`${variable name}`，例如：

``` 
for skill in Ada Coffe Action Java;
	do
		echo "I am good at ${skill}Script"
	done
``` 

运行的结果是：

> I am good at AdaScript

> I am good at CoffeScript

> I am good at ActionScript

> I am good at JavaScript

## 变量删除

``` 
unset variable_name
``` 