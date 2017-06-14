# 学习react
1. 用es6的写法定义组件, 用到static定义defaultProps时报错,原因是static是es7草案中的语法,需要安装***babel-preser-stage-0***,然后在.babelrc文件中用`stage-0`来引用就可以了.

### 关于绑定this的三种方法

1. 在contructor函数中绑定
```javascript
constructor(){
	this.handleClick = this.handleClick.bind(this);
}
// 在组件中调用
onClick = {this.handleClick}
```

2. 在调用时绑定
```JavaScript
	handleClick() { 	}
// 在组件中调用
onClick= { this.handleClick.bind(this) }
```

3. 使用箭头函数.注意:此方法不能用于传参



### nginx 配置路径: `/etc/nginx/sites-enabled`
