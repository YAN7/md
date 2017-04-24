# 你不知道的读书笔记

> 前言： 目前的读书进度还不错，保持一个月一本的节奏，但是看了过后就忘了，所以写点笔记，做点demo还是很有必要的，读过的书像微风吹过，不会留下什么痕迹，但是笔记是永远留存的，到80岁还可以看，哈哈.

### 数据类型

1. js中一共有7中数据类型，它们分别是：

* null;
* Undefined;
* Boolean;
* String;
* Number;
* Object;
* Symbol(es6新增);

2. 其中前五种是基本数据类型，Objec是复杂数据类型，它还是很多子类型，包括但不限于`Function`、`Arrary`、`Math`、`Date`;
3. js是弱数据类型语言,变量没有固定的数据类型，即变量的数据类型可以随意转换,但是值有固定的数据类型，且不会改变;

> 比如123的数据类型是Number，“123”的数据类型是String

4. 检测变量的数据类型可以用`typeof`来检测,但是这个方法有一个bug，这个bug存在将近有20年了，也许以后还会一直持续下去，正是因为这个bug存在的时间太长，要改的话成本太大，也许一改会牵扯到很多已上线的项目，所以这个bug不出意外会一直“美丽”的存在下去，这个bug就是：

```
typeof null === 'Object' // true

```

这个null的数据类型不是null，而是object，所以在检测null的时候不应该用`typeof`来检测,可以用一下方法来检测

```
const a = null;
if (a === null) {
  console.log(is null")
}
```

### 更详细的数据类型检测`instanceof`

1. `typeof`只能检测undefined, string, number, boolean, object这基本基本的数据类型，但是要对object作更深入的检测，比如检测工作中常用到的function，array等可以用`instanceof`
```

[] instanceof Array // true
function(){} instanceof Function // true

```

> 注意： ***instanceof只能用来判断对象和函数，不能用来判断字符串和数字等***
### 类型转换

#### `~`位操作符

1. 相当于-(x+1)

> ~100 ==> -(100+1)

2. 只有x=-1的时候，~x会转成0(实际是-0),可以利用这个这是特性来检测-1与其他数值,比如用来indexOf中
```javascript
// 为true时表示indexOf返回的是不是-1,即表示该字符串还有要检测的字符串字段
if(~"hello".indexOf("lo")) {}
```

#### “”是唯一可以转换成假值(false)的字符串

