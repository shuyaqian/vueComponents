Icon组件
===

图标更新步骤:
1.登录http://www.iconfont.cn/plus
2.找到想添加的图标添加至项目vue-com
3.更新Unicode的在线链接
4.将icon.vue文件中的url('//at.alicdn.com/t/***.ttf')替换掉
5.在icon.data.js中添加图标的名称和对应的code，搞定！

### Icon Attributes
| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| --- | --- | --- | --- | --- |
| name | 图标名称 | string | — | — |