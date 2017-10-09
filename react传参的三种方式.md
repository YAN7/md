# react传参的三种方式
### props.params传参
1. 使用Link传参：
```javascript
<Link to="/user/:id">jump router</Link>
```
2. 使用browserHistory传参：
```javascript
browserHistory.push("user/:id");
```
3. 获取参数
```javascript
this.props.parmas
```

### query传参
1. 传递参数
```javascript
const path = {pathname: "/user", query: {id: 123}};
<Link to={path}>jump</Link>
browserHistory.push(path);
```
2. 获取参数
```javascript
this.props.location.query
```
3. 缺点：以上两种传参都会以明文的形式显示在url中

### state传参
1. 传递参数
```javascript
cosnt path = {pathname: "/user", state: {id: 123}};
<Link to={path}>jump</Link>
browserHistory.push(path);
```

2. 获取参数
```javascript
this.props.location.state;
```
