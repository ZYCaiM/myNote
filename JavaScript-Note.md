## 数组排序
### 1-冒泡排序

    var arr = [9,8,7,6,5,4,3,2,1];
	var temp;
	for(var i = 0; i < arr.length; i++){
		for(var j = 0; j < arr.length - i; j++){
			if(arr[j] > arr[j+1]){//从第零个数开始,依次将每个数和后一个数比大小,将最大的数换到最后一个
				temp = arr[j+1];
				arr[j+1] = arr[j];
				arr[j] = temp;
			}	
		}//一次内层循环完毕后只能将一个最大的数放到最后,需要外层循环来重新启动内层循环,每次将未排序的数中最大的数放到未排序的数的最后,
		console.log(arr);
	}	
### 2-选择排序
	var arr = [9,8,7,6,5,4,3,2,1];
	var temp,min;
	for(var i = 0; i < arr.length - 1; i++){
        min = i;
		for(var j = i+1; j < arr.length; j++){
			if(arr[j] < arr[min]){//如果arr[j]比arr[min]小,
				min = j;          //就将arr[j]的下标赋给min,然后j++,再和arr[min]比大小,直到最后一个数,min就是最小数的下标,arr[min]就是最小数
			}//if比较结束后,原数组还没有发生变化,因为min是在i与j之外的,只是用来暂存最小数下标的,        	
		}
        //这里,才开始将 arr[i] 和 arr[min] 换位置(与冒泡排序不同的是,只需要换一次位置就可以);
        if(arr[min] != arr[i]){	
          temp = arr[i];
		  arr[i] = arr[min];
		  arr[min] = temp;
        }
	}

## 函数提升和变量提升
>在ES6之前,没有块级作用域,只有全局作用域和函数作用域.
### 1-变量提升
>变量提升就是将变量声明提升到它所在作用域的最开始.

    console.log(a);//undiefined
    var a = "aaa";
    console.log(a);//aaa

    function fn = {
        console.log(a);//undefined
        var a = "aaa";
        console.log(a);//aaa
    }
上面这种情况可以拆分为

    var a;//变量提升,将变量声明提升到了最上面,但此时并未赋值;
    consolo.log(a); //undefined
    a = "aaa";//此时才赋值
    console.log(a);//aaa

    function fn(){
        var a;//变量提升到它所在的函数作用域最开始的地方
        console.log(a);//此时未赋值,underfined
        a = "aaa";//完成赋值
        console.log(a);//aaa
    }

### 2-函数提升
> JS创建函数的方式中,构造函数,声明函数,匿名函数,只有声明函数才存在函数提升,
> 声明函数会整体提升到最开始

    console.log(f1);//function f1(){}
    console.log(f2);//underfined
    function f1(){};
    var f2 = function(){};

这是因为在实际运行时

    function f1(){};
    console.log(f1);//function f1(){}(没有返回值的话,会另外出一次underfined)
    console.log(f2);//underfined
    var f2 = function(){};


****
### JS与json的关系
> json就是将JS对象用字符串来表示
> json中,key和value都要用""包裹,键值对之间用逗号分割

#### JS与json的相互转化
1. var json = JSON.stringify({name:"zhangsan",age:20});
2. var user = JSON.parse('{"name":"zhangsan","age":"20"}');

#### json遍历要使用 for in 循环
    var json = {
        "name":"zhangsan",
        "age":"20"
    }
    for(var key in json){
        console.log("key"+key+"=>value"+json[key])
    }

### 使用JS检测数据类型
  * typeof--------检测数据类型的运算符
  * instanceof:--检测某个实例是否属于这个类 
  * constructor:-检测当前实例的构造器
  * Object.prototype.toString.call:获取当前实例的所属类信息
   
### 当把其他类型的值转换为布尔类型
> 只有0,NaN,空字符串,null,underfined这五个值转换为布尔类型时为false,其他的都为true

### `NaN`
>not a number : 不是一个数,但他本身属于number类型
>NaN == NaN :false,NaN和任何其他值都不相等
>isNaN("12"): false, 当我们使用isNaN检测值时,检测的值不是number类型的,浏览器会默认把值先转换为number类型,然后再去检测