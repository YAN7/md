# 写rn遇到的一些坑


### react-native link
### react-native-linear-gradient
### pt和px的关系

显然输出的是dp的单位，那么如果要转成对应的px的单位怎么转呢，答案就在上面的pixelRatio，将dp单位* pixelRatio就是对应的px的值了，同理px/pixelRatio就是对应的dp的值了。和android中px与dp的转换是一样的。

### 引入网络图片必须必须手动指定图片的宽高,图片才会显示出来
### Image组件的style中有一个resizeMode属性,它的可能值有contain,cover,stretch,参考链接: [Image的resizeMode属性](https://segmentfault.com/a/1190000002658374)

#### 将安卓标题栏修改为居中,`react-navigation`没有暴露修改标题文字位置的接口,需要去修改密码,参考链接: [使安卓标题居中显示](https://juejin.im/entry/5920994d570c350069a54a4b)

#### 动态设置react-navigation的标题

1. 要在navigationOptions中使用navigation的params,需要给navigationOption传一个以navigation为参数的函数,返回一个对象,然后在对象中就可以使用navigation这个对象了,而一般要用到的参数在navigation.state.params中

#### 报错: Expected a component class, got[object object]
> 原因:<View>组件使用首字母没有大写,变成了<view>,所以报错了.

#### 报错 com.android.ide.common.process.ProcessException: org.gradle.process.internal.ExecException: Process 'command '/usr/lib/jvm/java-8-openjdk-amd64/bin/java'' finished with non-zero exit value 2

> 打开项目下的安卓文件夹, 在该项目下执行 `./gradlew clean`


#### Error: Activity class {com.damaiapp.yml.doctor/com.damaiapp.yml.doctor.MainActivity} does not exist.
- [解决办法](https://stackoverflow.com/questions/35131769/error-type-3-activity-class-com-awesome-project-com-awesome-project-mainactiv)


#### rn中drawable和mipmap文件夹的区别

- mipmap文件夹一般只用来放应用图标文件, drawable文件夹用来放应用内用到的静态资源图片
