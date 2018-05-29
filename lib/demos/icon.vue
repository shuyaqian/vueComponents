<template>
    <scroller class="page">
        <text class="title">Icon 图标</text>
        <text class="desc">通过 CSS3 的 font-face 属性实现图标。</text>
        <text class="sub-title">使用方法</text>
        <text class="desc">直接通过设置类名为 cmui-icon-iconName 来使用即可。</text>
        <div class="demo-block">
            <cmui-row :gutter="20">
                <cmui-col>
                    <cmui-icon name="edit" class="demo-icon"></cmui-icon>
                </cmui-col>
                <cmui-col>
                    <cmui-icon name="share" class="demo-icon"></cmui-icon>
                </cmui-col>
                <cmui-col>
                    <cmui-icon name="delete" class="demo-icon"></cmui-icon>
                </cmui-col>
                <cmui-col>
                    <cmui-button-icon type="primary" icon="search">搜索</cmui-button-icon>
                </cmui-col>
            </cmui-row>
        </div>
        <text class="sub-title">图标集合</text>
        <div class="demo-block" style="flex-direction: row; flex-wrap:wrap; justify-content: space-between">
            <div v-for="name in icons" :key="name" class="demo-icon-list">
                <div class="demo-icon-item">
                    <cmui-icon :name="name" class="cmui-icon"></cmui-icon>
                    <text class="demo-icon-text">{{"cmui-icon-" + name}}</text>
                </div>
            </div>
        </div>
    </scroller>
</template>

<script>
    module.exports =  {
        components: {
            CmuiIcon: require('../widget/icon/icon.vue'),
            CmuiButtonIcon: require('../widget/button/button-icon.vue'),
            CmuiRow: require('../widget/row/row.vue'),
            CmuiCol: require('../widget/col/col.vue')
        },
        data () {
            return {
                icons: ['date', 'loading', 'star-off', 'view', 'arrow-left', 'arrow-up', 'arrow-right', 'arrow-down', 'd-arrow-left', 'd-arrow-right', 'menu', 'caret-left', 'caret-up', 'caret-right', 'caret-down', 'cycle-warning', 'message', 'document', 'information', 'upload', 'cycle-cross', 'edit-pen', 'cycle-close', 'close', 'cycle-check', 'time', 'share', 'check', 'attechment', 'calendar', 'cycle-minus', 'cycle-plus', 'plus', 'account', 'cycle-warning', 'cycle-question', 'search', 'cycle-success', 'edit', 'delete', 'home','customer']
            }
        }
    }
</script>

<style lang="sass" scoped>

    @import './common.scss';

    .demo-icon {
        padding-left: 30;
        padding-right: 30;
        height: 56;
        line-height: 56;
        background-color: #ff6a00;
        border-radius: 10;
        text-align: center;
    }
    .demo-icon-item {
        margin-bottom: 20;
        padding: 20;
        width: 300;
        background-color: #ff6a00;
        border-radius: 10;
        flex: 1;
    }
    .cmui-icon {
        margin-bottom: 20;
        text-align: center;
        font-size: 40;
    }
    .demo-icon-text {
        font-size: 24;
        color: #fff;
        text-align: center;
    }
</style>
