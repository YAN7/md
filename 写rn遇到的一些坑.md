# 写rn遇到的一些坑


### react-native link
### react-native-linear-gradient
### pt和px的关系

显然输出的是dp的单位，那么如果要转成对应的px的单位怎么转呢，答案就在上面的pixelRatio，将dp单位* pixelRatio就是对应的px的值了，同理px/pixelRatio就是对应的dp的值了。和android中px与dp的转换是一样的。

### 引入网络图片必须必须手动指定图片的宽高,图片才会显示出来
### Image组件的style中有一个resizeMode属性,它的可能值有contain,cover,stretch,参考链接: [Image的resizeMode属性](https://segmentfault.com/a/1190000002658374)

#### 将安卓标题栏修改为居中,`react-navigation`没有暴露修改标题文字位置的接口,需要去修改密码,参考链接: [使安卓标题居中显示](https://juejin.im/entry/5920994d570c350069a54a4b)
