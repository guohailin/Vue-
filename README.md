# 使用vuejs搭建的一个单页面应用售卖平台项目实例，
涉及技术栈：vuex、vue-router、vue-resource、less、webpack 
模块：产品列表，新闻列表，轮播图切换，登入注册关于我们。
数据通过promise从后台请求,通过Mock.js模拟数据 http://easy-mock.com。

登入注册模块使用Vue钩子函数。
  vue-router 提供的导航钩子主要用来拦截导航，让它完成跳转或取消。
  为方便设置钩子函数建议在routes里面配置meta。
  ● to: Route: 即将要进入的目标 路由对象
  ● from: Route: 当前导航正要离开的路由
  ● next: Function: 一定要调用该方法来 resolve 这个钩子。执行效果依赖 next 方法的调用参数。

轮播图组件实现有很多插件可以使用，详细参考Vue组件库，关键字Carousel或slider.
https://github.com/vuejs/awesome-vue

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build
```
项目特效

![](https://i.ooxx.ooo/2017/10/11/104a8a2c0c43d33924eef60f0ddfc521.gif)

友情提示：数据模拟方法可参考如下：
当需要100条数据时，可通过如下方法快速创建，然后上传到easy-mock方便请求。
执行环境为node.js，如果使用HBuilder开发环境需要安装nodeclipse插件，
function getRandom(n, m) {
	return Math.round(Math.random() * (m - n) + n);
}
var str1 = "赵钱孙李周吴郑王冯陈褚卫蒋韩杨朱秦尤许何吕施张邹喻";
var str2 = "壹贰叁肆伍陆柒捌玖一二三四五六七八九";
var arry = [];
for(var i = 1; i <= 99; i++) {
	var obj = {};
	obj["id"] = i;
	obj["name"] = str1[getRandom(0, 24)] + str2[getRandom(0, 17)] + str2[getRandom(0, 17)];
	obj["sex"] = getRandom(0, 1);
	obj["score"] = getRandom(50,99);
	arry.push(obj);
}
console.log(JSON.stringify(arry));
