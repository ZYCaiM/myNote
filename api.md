## API
### 数组
1. 把数组转换成字符串,用 , 分割
    
        arr.toString();      

2. 把原数组翻转,返回翻转后的原数组

        arr.reverse();

3. 将原数组排序后返回

        arr.sort();
        //传入参数为function(a,b){return a-b}为从小到大
        //传入参数为function(a,b){return b-a}为从小到大
4. 从数组中找到指定元素的索引值
       * arr.indexOf();
       * arr.lastIndexOf();
5. 从原数组中截取一个新数组并返回,不影响原数组,

        arr.slice();//接受两个参数,(start,end) 从start开始,到end结束,但并不包括end.
6. 从原数组中删除一个指定索引值的元素,

        arr.splice();//接受三个参数,(start,deleteConunt,options),
                     //star----指定要删除的元素的索引值
                     //deleteCount--从start开始,向后多少位
                     //options--删除后,要想空出来的位置添加的元素.
7. 清空数组
    * arr.length = 0;
    * arr = [];
8. 合并数组

        arr.concat();//接受任意个值,或者另一个数组.返回合并后的数组
9.  数组转化字符串

        arr.join();//将数组中的所有元素放入字符串,接受一个参数来分隔每个元素,默认是逗号.
10.
****
### 字符串
1. 字符串转化数组

        str.split();//将字符串转化为数组并返回数组,按接收的参数来分割字符串,默认是逗号.
2. 在字符串中截取字符串并返回,

        str.substr();//start,指定要截取字符串的起点;length,指定要截取字符串的长度.
3. 获取指定位置的字符

        str.charAt();
4. 返回指定位置的Unicode编码,

        str.charCodeAt();
5. 返回字符在字符串中的位置

    * str.indexOf();
    * str.lastIndexOf();
6. 连接字符串

        str.concat();
7. 提取字符串中的某个部分,以新的字符串返回

        ste.slice();
8. 字符串的大小写转换

    + str.toUpperCase();
    + str.toLowerCase();