<template>
    <scroller class="page">
        <div class="component-title">
            <image :src="logoimg" class="logo-img"></image>
            <text class="title">GTS-Button</text>
        </div>
        <text class="desc">常用的操作按钮。</text>
        <text class="sub-title">基本按钮</text>
        <text class="desc">基础的按钮用法。</text>
        <div class="demo-block">
            <cmui-row :gutter="20">
                <cmui-col>
                    <cmui-button>默认按钮</cmui-button>
                </cmui-col>
                <cmui-col>
                    <cmui-button type="primary">主要按钮</cmui-button>
                </cmui-col>
                <cmui-col>
                    <cmui-button type="text">文字按钮</cmui-button>
                </cmui-col>
            </cmui-row>
        </div>
        <text class="sub-title">禁用状态</text>
        <text class="desc">按钮不可用状态。</text>
        <div class="demo-block">
            <cmui-row :gutter="20">
                <cmui-col>
                    <cmui-button :disabled="true">默认按钮</cmui-button>
                </cmui-col>
                <cmui-col>
                    <cmui-button type="primary" :disabled="true">主要按钮</cmui-button>
                </cmui-col>
                <cmui-col>
                    <cmui-button type="text" :disabled="true">文字按钮</cmui-button>
                </cmui-col>
            </cmui-row>
        </div>
        <text class="sub-title">不同尺寸</text>
        <text class="desc">Button 组件提供除了默认值以外的三种尺寸，可以在不同场景下选择合适的按钮尺寸。</text>
        <div class="demo-block">
            <cmui-row :gutter="20">
                <cmui-col>
                    <cmui-button type="primary" size="large">大尺寸按钮</cmui-button>
                </cmui-col>
                <cmui-col>
                    <cmui-button type="primary" size="normal">正常尺寸按钮</cmui-button>
                </cmui-col>
                <cmui-col>
                    <cmui-button type="primary" size="small">小尺寸按钮</cmui-button>
                </cmui-col>
            </cmui-row>
        </div>
        <text class="sub-title">朴素按钮</text>
        <text class="desc">按钮镂空。</text>
        <div class="demo-block">
            <cmui-row :gutter="20" style="margin-bottom:20">
                <cmui-col>
                    <cmui-button-plain>默认按钮</cmui-button-plain>
                </cmui-col>
                <cmui-col>
                    <cmui-button-plain type="primary">主要按钮</cmui-button-plain>
                </cmui-col>
                <cmui-col>
                    <cmui-button-plain type="warning">警告按钮</cmui-button-plain>
                </cmui-col>
            </cmui-row>
        </div>
        <text class="desc">朴素按钮不可用状态。</text>
        <div class="demo-block">
            <cmui-row :gutter="20">
                <cmui-col>
                    <cmui-button-plain :disabled="true">默认按钮</cmui-button-plain>
                </cmui-col>
                <cmui-col>
                    <cmui-button-plain type="primary" :disabled="true">主要按钮</cmui-button-plain>
                </cmui-col>
                <cmui-col>
                    <cmui-button-plain type="warning" :disabled="true">警告按钮</cmui-button-plain>
                </cmui-col>
            </cmui-row>
        </div>
        <text class="desc">朴素按钮也可以设置大小。</text>
        <div class="demo-block">
            <cmui-row :gutter="20">
                <cmui-col>
                    <cmui-button-plain type="primary" size="large">大尺寸按钮</cmui-button-plain>
                </cmui-col>
                <cmui-col>
                    <cmui-button-plain type="primary" size="normal">正常尺寸按钮</cmui-button-plain>
                </cmui-col>
                <cmui-col>
                    <cmui-button-plain type="primary" size="small">小尺寸按钮</cmui-button-plain>
                </cmui-col>
            </cmui-row>
        </div>
        <text class="sub-title">图标按钮</text>
        <text class="desc">带图标的按钮可增强辨识度(有文字)或节省空间(无文字)。</text>
        <div class="demo-block">
            <cmui-row :gutter="20">
                <cmui-col>
                    <cmui-button-icon type="primary" icon="edit">编辑</cmui-button-icon>
                </cmui-col>
                <cmui-col>
                    <cmui-button-icon type="primary" icon="delete">删除</cmui-button-icon>
                </cmui-col>
                <cmui-col>
                    <cmui-button-icon type="primary" icon="share">分享</cmui-button-icon>
                </cmui-col>
            </cmui-row>
        </div>
        <text class="sub-title">按钮组</text>
        <text class="desc">以按钮组的方式出现，常用于多项类似操作。</text>
        <div class="demo-block">
            <cmui-button-group style="margin-bottom:20">
                <cmui-button type="primary" group-index="first">上一页</cmui-button>
                <cmui-separate-line></cmui-separate-line>
                <cmui-button type="primary" group-index="last">下一页</cmui-button>
            </cmui-button-group>
            <cmui-button-group style="margin-bottom:20">
                <cmui-button type="primary" group-index="first">编辑</cmui-button>
                <cmui-separate-line></cmui-separate-line>
                <cmui-button type="primary">删除</cmui-button>
                <cmui-separate-line></cmui-separate-line>
                <cmui-button type="primary" group-index="last">保存</cmui-button>
            </cmui-button-group>
            <cmui-button-group>
                <cmui-button-icon type="primary" icon="edit" group-index="first"></cmui-button-icon>
                <cmui-separate-line></cmui-separate-line>
                <cmui-button-icon type="primary" icon="cycle-plus"></cmui-button-icon>
                <cmui-separate-line></cmui-separate-line>
                <cmui-button-icon type="primary" icon="delete" group-index="last"></cmui-button-icon>
            </cmui-button-group>
        </div>
    </scroller>
</template>

<script>
    module.exports = {
        components: {
            CmuiButton: require('../widget/button/button.vue'),
            CmuiButtonPlain: require('../widget/button/button-plain.vue'),
            CmuiButtonIcon: require('../widget/button/button-icon.vue'),
            CmuiButtonGroup: require('../widget/button/button-group.vue'),
            CmuiSeparateLine: require('../widget/line/separate-line.vue'),
            CmuiRow: require('../widget/row/row.vue'),
            CmuiCol: require('../widget/col/col.vue')
        },
        data () {
            return {
                logoimg:'https://gw.alicdn.com/tfs/TB1PaIWSFXXXXasXpXXXXXXXXXX-109-77.png'
            }
        },
    }
</script>

<style lang="sass" scoped>
    @import './common.scss';
</style>
