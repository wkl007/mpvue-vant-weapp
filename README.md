# mpvue-vant-weapp

>使用mpvue通过usingComponents导入[vant-weapp](https://github.com/youzan/vant-weapp)

## 预览

``` bash
1. git clone
git clone https://github.com/wkl007/mpvue-vant-weapp.git

2. 安装依赖
cd mpvue-vant-weapp && npm install

3. 启动程序
npm run dev

4. 预览
打开微信开发者工具，新建项目，将目录指向 /dist 即可
```

## 问题
- 小程序中`this.$emit(event,data)`中：
`event`有些使用中划线命名法，在mpvue中不支持，需要修改
- 小程序中`this.trigger('click', index)`中：
`mpvue`无法从`event.mp`中读取到正确的`detail`，原因是因为`mpvue`将`click`事件编译为`tap`导致`this.trigger('click', index)`无法找到`click`句柄

## 解决方案
`this.$emit('click-left'); => this.$emit('clickLeft');`
`this.trigger('click', index);=>this.trigger('iclick', index);`

> 注：本次示例中修改了`nav-bar`、`tabs`、`field`、`tree-select`组件

## 受影响组件(仅传值情况受影响)
1. nav-bar
2. tabs
3. field
4. tree-select
