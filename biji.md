#数组笔记
#关于数组相关函数的详解

##concat():合并数组
```
var arr1=[1,2,3]
var arr2=[4,5,6]
document.write(arr1.concat(arr2))//输出1,2,3,4,5,6
```

##copyWithin(target,start,end):操作数组本身，将某一部分的元素复制并覆盖到其他位置上
##target：目的起始位置。
##start：复制源的起始位置，从下标0开始，可以省略，可以是负数。
##end：复制源的结束位置，从下标0开始，可以省略，可以是负数，实际结束位置是end-1
```
var arr=[1,2,3,4,5,6,7,8]
arr.copyWithin(1,3,5)
document.write(arr)//输出：1,4,5,4,5,6,7,8
```

##entries():返回一个新的Iterator对象，该对象包含数组中每个索引的键值对
```
var arr=['a','b','c']
var iterator=arr.entries()
document.write(iterator.next().value)
```

##可以将一个类似数组或者可迭代的对象创建成一个新的数组，新数组中每个元素只出现一次

```
document.write(Array.from('abc'))//输出a,b,c
```

##every():测试数组中是否每个元素都满足某种规则
```
var arr=[1,2,3,4,5]
document.write(arr.every(function(value,index,arr){
	return value<10//输出结果为boole值，此处输出true
}))
```

##some():测试数组中是否有元素满足某种条件
```
var arr=[1,2,3,55,6]
document.write(arr.some(function(values,index,arr){
	return values>50//输出true
}))
```

##filter():创建一个新的数组，满足通过参数函数测试的所有函数
```
var arr=[1,2,3,5,66]
document.write(arr.filter(function(value,index,arr){
	return value>10//输出66
}))
```

##find():用法与filter相似，返回值为符合测试函数的第一个值，如果没有符合条件的返回Undefined

```
var arr=[1,2,3,5,66]
document.write(arr.find(function(value,index,arr){
	return value<10//输出1,2,3,5
}))
```

##findIndex():用法与find相似，返回值为符合测试函数的第一个值的索引
```
var arr=[1,2,3,5,66]
document.write(arr.findIndex(function(value,index,arr){
	return value<10//输出0
}))
```

##fill():用一个固定值去填充数组中从起始索引到终止索引的全部元素
##参数：
##value（必填）用来填充数组的值
##start（选填）起始索引，默认值为0 如果为负数的话start = start+arr.length
##end （选填）终止索引，默认值为arr.length 如果为负数的话 end = end+arr.length
##start=>end 在数学中是[)，选择大于等于start，小于end的值
##返回值：修改之后的数组
```
var arr=[1,2,3,6,5,4,7,8,9]
document.write(arr.fill(5,0,arr.length))//输出：5,5,5,5,5,5,5,5,5,
```

##indexOf(searchElement,formIndex):从指定起始索引查找指定的元素
##返回值为该元素对应的索引，没有找到元素或者索引，返回-1

```
var arr=[1,2,3,4,5,6,7,8,9]
document.write(arr.indexOf(6,2))//输出5
```

##数组的遍历
##1.普通for循环
```
var arr=[1,2,3,4,5,6]
for(var i=0;i<arr.length;i++){
	document.write(arr[i]+",")
}
```
##2.forEach循环
```
var arr = [1, 2, 3];
arr.forEach(function(element) {
    document.write(element);
})
```
##map循环
```
var arr=[1,2,3,4,5,6]
document.write(arr.map(function(arr){
	return arr
}))
```


##push():往数组中添加一个或多个元素
```
var arr=[1,2,3]
arr.push(4,5)
arr.push(6)
document.write(arr)
```

##pop():删除数组的最后一个值，并返回删除元素的值
```
var arr=[1,2,3]
arr.pop()
document.write(arr)
```

##shift():删除数组的第一个值，并返回删除元素的值
```
var arr=[1,2,3]
arr.shift()
document.write(arr)
```

##unshift():将一个或者多个元素添加到素组的开头，并返回数组的长度
```
var arr=[1,2,3]
arr.unshift(1)
arr.unshift(4,5,6)
document.write(arr)
```


##join():将数组转化成字符串，不会改变原数组，返回生成的一个字符串
```
var arr=['a','b','c']
document.write(arr.join())//a,b,c
document.write(arr.join(""))//abc
document.write(arr.join('-'))//a-b-c
```

