## 如何使用
1. clone 本项目
2. 安装 wepy 命令行工具
`npm install wepy-cli -g`
3. 开发实时编译
`npm run dev`
4. 在微信开发者工具中新建项目，本地开发选择 dist 目录
5. 微信开发者工具 → 项目 → 关闭ES6转ES5，否则运行会报错

## 技巧和注意点
* 设置编辑器 wby 文件语法高亮识别为 vue
* dist 目录要在 git 仓库中保留，里面的 npm 目录生成方式暂不清楚

## 文件骨架
程序入口 app.wpy：
```
<style lang="less">
/** less **/
</style>
<script>
import wepy from 'wepy';
export default class extends wepy.app {
    config = {
            "pages":[
            "pages/index/index"
        ],
        "window":{
            "backgroundTextStyle": "light",
            "navigationBarBackgroundColor": "#fff",
            "navigationBarTitleText": "WeChat",
            "navigationBarTextStyle": "black"
        }
    };
    onLaunch() {
        console.log(this);
    }
}
</script>
```

页面 index.wpy：
```
<style lang="less">
/** less **/
</style>
<template lang="wxml">
    <view>
    </view>
    <counter1></counter1>
</template>
<script>
import wepy form 'wepy';
import Counter from '../components/counter';
export default class Index extends wepy.page {

    config = {};
    components = {counter1: Counter};

    data = {};
    methods = {};

    events = {};
    onLoad() {};
    // Other properties
}
</script>
```

组件 com.wpy，同页面，没有页面特有的 config 和生命周期事件

## 参考
* [wepyjs - 小程序组件化开发框架](https://wepyjs.github.io/wepy/#/)
* [【腾讯Bugly干货分享】打造“微信小程序”组件化开发框架 - 知乎专栏](https://zhuanlan.zhihu.com/p/24176267)i
