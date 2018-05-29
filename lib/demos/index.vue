<template>
    <scroller>
        <div class="cmui-cells">
            <text class="cmui-cells-title">Weex组件库</text>
            <div class="cmui-cell" v-for="(item, key) in itemList" @click="open(key)"
                 :style="{ backgroundColor: key == highIndex ? '#E0E0E0' : 'white' }"
                 @touchend="touchend" @touchstart="touchstart(key)" @touchmove="touchmove">
                <text class="cmui-cell-bd">{{item.title}}</text>
                <text class="cmui-cell-ft">{{item.desc}}</text>
            </div>
        </div>
    </scroller>
</template>
<script>

    var navigator = weex.requireModule('navigator');
    var modal = weex.requireModule('modal');
//    var url = 'http://127.0.0.1:8088/weex/newindex.js?_wx_tpl=http://' +
//               weex.config.bundleUrl.match(/\d+\.\d+\.\d+\.\d+/) +
//              ':7002/build/components/cmui/demos/';
    var url = 'http://g.alicdn.com/aliseller/weex-ui/1.0.5/components/cmui/demos/'

    var itemList = [{
        title: 'Layout',
        desc: '布局组件',
        url: url + 'layout.js'
    },{
        title: 'Button',
        desc: '按钮组件',
        url: url + 'button.js'
    },{
        title: 'List',
        desc: '列表组件',
        url: url + 'list.js'
    },{
        title: 'Tab',
        desc: '标签组件',
        url: url + 'tab.js'
    },{
        title: 'Topbar',
        desc: '顶部导航栏',
        url: url + 'inlineTab.js'
    },{
        title: 'Tabbar',
        desc: '底部导航栏',
        url: url + 'tabbar.js'
    },{
        title: 'Color',
        desc: '色彩组件',
        url: url + 'color.js'
    },{
        title: 'Typography',
        desc: '字体组件',
        url: url + 'typography.js'
    },{
        title: 'Icon',
        desc: '图标组件',
        url: url + 'icon.js'
    },{
        title: 'Form-cell',
        desc: '类表单组件',
        url: url + 'form-cell.js'
    },{
        title: 'Form',
        desc: '表单组件',
        url: url + 'form.js'
    },{
        title: 'Upload',
        desc: '图片上传组件',
        url: url + 'upload.js'
    },{
        title: 'Select',
        desc: '单选框组件',
        url: url + 'select.js'
    },{
        title: 'Search',
        desc: '搜索框组件',
        url: url + 'search.js'
    },{
        title: 'Menu',
        desc: '菜单组件',
        url: url + 'menu.js'
    },{
        title: 'Slider',
        desc: '轮滑图组件',
        url: url + 'slider.js'
    }];

    module.exports =  {
        data() {
            return {
                itemList: itemList,
                highIndex: -1
            };
        },

        methods: {
            open (key) {
                navigator.push({
                    url: itemList[key].url,
                    animated: "true"
                }, event => {})
            },
            touchstart: function (key) {
                this.highIndex = key;
            },
            touchend: function () {
                this.highIndex = -1;
            },
            touchmove: function () {
                this.highIndex = -1;
            }
        }
    };
</script>

<style lang="sass" scoped>
    @import '../widget/cells/cells-item.scss';
    @import '../widget/cell-item/cell-item.scss';
    .cmui-cells-title {
        font-size: 50;
        color: #0184d7;
    }
    .cmui-cell-bd {
        font-size: 40;
    }
    .cmui-cell-ft {
        font-size: 30;
    }
    .cmui-cell {
        padding-top: 40;
        padding-bottom: 40;
        padding-left: 30;
        padding-right: 30;
        margin-left: 0;
    }
</style>
