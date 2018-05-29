<template>
    <scroller class="page">
        <text class="title">类 Form 列表</text>
        <text class="desc">类 Form 的列表项，包含多重模式并可以跳转。</text>
        <text class="sub-title">带说明的列表项</text>
        <cmui-cells title="带说明的列表项">
            <cmui-cell-item></cmui-cell-item>
            <cmui-cell-item></cmui-cell-item>
            <cmui-cell-item last="true"></cmui-cell-item>
        </cmui-cells>
        <text class="sub-title">带图标、说明的列表项</text>
        <cmui-cells title="带图标、说明的列表项">
            <cmui-cell-item
                cell-icon="http://photo.taobao.net/uploads/thumbnail/b8b3e44c8517400dc085882a360bc769/2.jpg"
               ></cmui-cell-item>
            <cmui-cell-item
                cell-icon="http://photo.taobao.net/uploads/thumbnail/b8b3e44c8517400dc085882a360bc769/2.jpg"
               ></cmui-cell-item>
            <cmui-cell-item
                cell-icon="http://photo.taobao.net/uploads/thumbnail/b8b3e44c8517400dc085882a360bc769/2.jpg"
                last="true"></cmui-cell-item>
        </cmui-cells>
        <text class="sub-title">带跳转的列表项</text>
        <cmui-cells title="带跳转的列表项">
            <cmui-cell-item access="true" @click="handleClick"></cmui-cell-item>
            <cmui-cell-item access="true" @click="handleClick"></cmui-cell-item>
            <cmui-cell-item last="true" access="true" @click="handleClick"></cmui-cell-item>
        </cmui-cells>
        <text class="sub-title">带说明、跳转的列表项</text>
        <cmui-cells title="带说明、跳转的列表项">
            <cmui-cell-item access="true"></cmui-cell-item>
            <cmui-cell-item access="true"></cmui-cell-item>
            <cmui-cell-item last="true" access="true"></cmui-cell-item>
        </cmui-cells>
        <text class="sub-title">带图标、说明、跳转的列表项</text>
        <cmui-cells title="带图标、说明、跳转的列表项">
            <cmui-cell-item
                cell-icon="http://photo.taobao.net/uploads/thumbnail/b8b3e44c8517400dc085882a360bc769/2.jpg"
                access="true"></cmui-cell-item>
            <cmui-cell-item
                cell-icon="http://photo.taobao.net/uploads/thumbnail/b8b3e44c8517400dc085882a360bc769/2.jpg"
                access="true"></cmui-cell-item>
            <cmui-cell-item
                cell-icon="http://photo.taobao.net/uploads/thumbnail/b8b3e44c8517400dc085882a360bc769/2.jpg"
                last="true"
                access="true"></cmui-cell-item>
        </cmui-cells>
        <text class="sub-title">列表组合</text>
        <div class="cells-group">
            <cmui-cells title="带说明的列表项">
                <cmui-cell-item></cmui-cell-item>
                <cmui-cell-item></cmui-cell-item>
                <cmui-cell-item last="true"></cmui-cell-item>
            </cmui-cells>
            <cmui-cells title="带说明、跳转的列表项">
                <cmui-cell-item access="true"></cmui-cell-item>
                <cmui-cell-item access="true"></cmui-cell-item>
                <cmui-cell-item last="true" access="true"></cmui-cell-item>
            </cmui-cells>
        </div>
    </scroller>
</template>

<script>
    module.exports =  {
        components: {
            CmuiCells: require('../widget/cells/cells-item.vue'),
            CmuiCellItem: require('../widget/cell-item/cell-item.vue')
        },

        methods: {
            handleClick (e) {
                console.log(e);
            }
        }
    }
</script>

<style lang="sass" scoped>

    @import './common.scss';

    .cells-group {
        background-color: #F2F3F7;
    }
</style>
