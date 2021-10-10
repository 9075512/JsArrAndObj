

# JS数组常用方法

## 1、创建数组

### new Array

> 语法：`new Array(元素的个数)`

```js
var arr1 = new Array(5); //指创建长度为5的数组
```

> 语法：`new Array('元素1', '元素2', '元素3'.....)`

```js
var arr = new Array("b", 2, "a", 4);
```

### 字面量

```js
var arr = ["b", 2, "a", 4,];
```


## 2、检测变量是否为数组

### instanceof

> 作用：检测变量是不是某个构造函数的实例
>
> 语法：`变量 instanceof 构造函数名`
>
> 返回值：true 或 false

```js
var age = 20;
var arr = [1, 2, 3];

console.log(age instanceof Array);//false
console.log(arr instanceof Array);//true
```

### isArray()方法

> 作用： 用于确定传递的值是否是一个数组，返回一个布尔值。
>
> 语法：`Array.isArray(被检测的值/变量)`
>
> 返回值：true 或 false

```js
var age = 20;
var arr = [1, 2, 3];

console.log(Array.isArray('ABC'));//false
console.log(Array.isArray(123));//false
console.log(Array.isArray(1,2,3));//false
console.log(Array.isArray([1,2,3]));//true
console.log(Array.isArray(age));//false
console.log(Array.isArray(arr));//true
```

## 3、添加数组元素 :id=hello-world

### 在数组末尾添加新元素

> 语法：`数组.push(新元素1, 新元素2, 新元素3,...)`
>
> 返回值：数组的最新长度

```js
var arr = [1, 2];
console.log(arr.push(3, 4));//返回数组最新长度
```

### 在数组头部添加新元素

> 语法：`数组.unshfit(新元素1, 新元素2, 新元素3,...)`
>
> 返回值：数组的最新长度

```js
var arr = [1, 2];
console.log(arr.unshfit(3, 4));//返回数组最新长度
```

## 4、删除数组头尾的元素

### 删除数组的最后1个元素

> 语法：`数组.pop()`
>
> 返回值：被删除的数组元素

```js
var arr = [1, 2, 3, 4, 5];
console.log(arr.pop());//返回被删除的数组元素
```

### 删除数组的第1个元素

> 语法：`数组.shift()`
>
> 返回值：被删除的数组元素

```
var arr = [1, 2, 3, 4, 5];
console.log(arr.shift());//返回被删除的数组元素
```

## 5、翻转数组元素

> 语法：`数组reverse()`
>
> 返回值：翻转后的数组
>
> 注意：原数组发生变化（被翻转了）

```js
var arr = [1, 2, 3, 4, 5];
console.log(arr.reverse());//返回被颠倒后的数组
```

## 6、数组元素排序

- 从小到大排

  ```js
  数组.sort(function(a, b){
      return a-b
  })
  ```

- 从大到小排

  ```js
  数组.sort(function(a, b){
      return b-a
  })
  ```

## 7、查找元素的位置

### 查找第1次出现的位置

> 作用：查找给定元素在数组中第一次出现的位置（索引）
>
> 语法：`数组.indexOf('给定的元素'[,fromIndex])`
>
> 参数：fromIndex，从哪个位置开始查找（默认是0）
>
> 返回值：索引（如果没有该元素，则返回-1）

### 查找最后1次出现的位置

> 作用：查找给定元素在数组中最后一次出现的位置（索引）
>
> 语法：`数组.lastIndexOf('给定的元素')`
>
> 返回值：索引（如果没有该元素，则返回-1）

## 8、数组转字符串（把数组中的元素拼接成字符串）

- 数组.toString()

  ```js
  var arr = [1, 2, 3];
  console.log(arr.toString())
  ```

- 数组.join([分隔符])  默认分隔符是','

  ```js
  var arr = [1, 2, 3];
  console.log(arr.join('&'))
  ```

## 9、数组合并

> 语法：
>
> - `数组.concat(元素1, 元素2, 元素3,...);`
> - `数组.concat(数组1, 数组2, 数组3,...);`
>
> 返回值：返回合并后的新数组（原数组不受影响）

## 10、提取数组元素

> 语法：`数组.slice([begin[,end]])`
>
> 参数：
>
> - begin，开始提取的位置（索引），默认是0
> - end，提取终止的位置（索引）
>
> 返回值：新数组（原数组不受影响）

## 11、删除数组任意位置任意个数的元素

> 语法：`数组.splice(start,个数)`
>
> 参数：strat 从哪个位置开始删
>
> 返回值：被删除元素组成的数组（注意：原数组受影响了）

## 12、遍历数组元素

> 1. `for循环`
>
> 2. `$.each()`
>
> 3. `数组.forEach()`
>
>    语法：
>
>    ```js
>    数组.forEach(function(item, index, arr){
>        有几个元素此回调函数就被调用几次
>        // item 数组元素
>        // index 数组元素的索引
>        // arr 数组本身
>    })
>    ```

## 13、筛选数组元素

> 语法：
>
> ```js
> 数组.forEach(function(item, index, arr){ 有几个元素此回调函数就被调用几次 // item 数组元素 // index 数组元素的索引 // arr 数组本身 return 筛选条件;})
> ```
>
> 返回值：把符合条件的元素放到一个新数组中放，返回

## 14、判断是否有满足条件的元素

> 语法：
>
> ```js
> 数组.some(function(item, index, arr){ 有几个元素此回调函数就被调用几次 // item 数组元素 // index 数组元素的索引 // arr 数组本身 return 判断条件;})
> ```
>
> 返回值：true 或 false

## 15、操作数组的元素map()

> 作用：对数组的每一个元素进行操作，形成一个新数组
>
> 语法：
>
> ```js
> 数组.map(function(item, index, arr){ 有几个元素此回调函数就被调用几次 // item 数组元素 // index 数组元素的索引 // arr 数组本身})
> ```
>
> 返回值：新数组中的每一个元素都是回调函数的返回值（原数组不受影响）

## 16、判断所有的元素是否都符合条件every()

> 作用：判断数组中所有的元素是否都符合条件
>
> 语法：
>
> ```js
> 数组.every(function(item, index, array){ return 判断条件;})
> ```
>
> 返回值：true 或 false

## 17、伪数组转真数组

> 语法：`Array.from(伪数组)`

## 18、查找第1个满足条件的元素

> 语法：
>
> ```js
> 数组.find(function(item, index, array){ return 查找条件;})
> ```
>
> 返回值：数组元素或者underfined

## 19、查找第1个满足条件的元素的索引

> 语法：
>
> ```js
> 数组.findIndex(function(item, index, array){  return 查找条件;})
> ```
>
> 返回值：数组元素的索引或者 -1

## 20、判断数组中是否有某个元素

> 作用：查找数组中是否包含指定的元素
>
> 语法：`数组.includes(被查找的元素)`
>
> 返回值：true 或 false