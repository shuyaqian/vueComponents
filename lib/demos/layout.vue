<template>
    <scroller class="page">
        <text class="title">Layout 布局</text>
        <text class="desc">通过基础的 24 分栏，迅速简便地创建布局。</text>
        <text class="sub-title">基础布局</text>
        <text class="desc">使用单一分栏创建基础的栅格布局。</text>
        <div class="demo-block">
            <cmui-row class="row">
                <cmui-col :span="24">
                    <div class="grid-content bg-purple-dark"></div>
                </cmui-col>
            </cmui-row>
            <cmui-row class="row">
                <cmui-col :span="12">
                    <div class="grid-content bg-purple"></div>
                </cmui-col>
                <cmui-col :span="12">
                    <div class="grid-content bg-purple-light"></div>
                </cmui-col>
            </cmui-row>
            <cmui-row class="row">
                <cmui-col :span="8">
                    <div class="grid-content bg-purple"></div>
                </cmui-col>
                <cmui-col :span="8">
                    <div class="grid-content bg-purple-light"></div>
                </cmui-col>
                <cmui-col :span="8">
                    <div class="grid-content bg-purple"></div>
                </cmui-col>
            </cmui-row>
            <cmui-row class="row">
                <cmui-col :span="6">
                    <div class="grid-content bg-purple"></div>
                </cmui-col>
                <cmui-col :span="6">
                    <div class="grid-content bg-purple-light"></div>
                </cmui-col>
                <cmui-col :span="6">
                    <div class="grid-content bg-purple"></div>
                </cmui-col>
                <cmui-col :span="6">
                    <div class="grid-content bg-purple-light"></div>
                </cmui-col>
            </cmui-row>
            <cmui-row>
                <cmui-col :span="4">
                    <div class="grid-content bg-purple"></div>
                </cmui-col>
                <cmui-col :span="4">
                    <div class="grid-content bg-purple-light"></div>
                </cmui-col>
                <cmui-col :span="4">
                    <div class="grid-content bg-purple"></div>
                </cmui-col>
                <cmui-col :span="4">
                    <div class="grid-content bg-purple-light"></div>
                </cmui-col>
                <cmui-col :span="4">
                    <div class="grid-content bg-purple"></div>
                </cmui-col>
                <cmui-col :span="4">
                    <div class="grid-content bg-purple-light"></div>
                </cmui-col>
            </cmui-row>
        </div>
        <text class="sub-title">分栏间隔</text>
        <text class="desc">分栏之间存在间隙。</text>
        <div class="demo-block">
            <cmui-row :gutter="20" class="row">
                <cmui-col :span="8">
                    <div class="grid-content bg-purple"></div>
                </cmui-col>
                <cmui-col :span="8">
                    <div class="grid-content bg-purple"></div>
                </cmui-col>
                <cmui-col :span="8">
                    <div class="grid-content bg-purple"></div>
                </cmui-col>
            </cmui-row>
            <cmui-row :gutter="20">
                <cmui-col :span="6">
                    <div class="grid-content bg-purple"></div>
                </cmui-col>
                <cmui-col :span="6">
                    <div class="grid-content bg-purple"></div>
                </cmui-col>
                <cmui-col :span="6">
                    <div class="grid-content bg-purple"></div>
                </cmui-col>
                <cmui-col :span="6">
                    <div class="grid-content bg-purple"></div>
                </cmui-col>
            </cmui-row>
        </div>
        <text class="sub-title">混合布局</text>
        <text class="desc">通过基础的 1/24 分栏任意扩展组合形成较为复杂的混合布局。</text>
        <div class="demo-block">
            <cmui-row :gutter="20" class="row">
                <cmui-col :span="16">
                    <div class="grid-content bg-purple"></div>
                </cmui-col>
                <cmui-col :span="8">
                    <div class="grid-content bg-purple"></div>
                </cmui-col>
            </cmui-row>
            <cmui-row :gutter="20" class="row">
                <cmui-col :span="8">
                    <div class="grid-content bg-purple"></div>
                </cmui-col>
                <cmui-col :span="8">
                    <div class="grid-content bg-purple"></div>
                </cmui-col>
                <cmui-col :span="4">
                    <div class="grid-content bg-purple"></div>
                </cmui-col>
                <cmui-col :span="4">
                    <div class="grid-content bg-purple"></div>
                </cmui-col>
            </cmui-row>
            <cmui-row :gutter="20">
                <cmui-col :span="4">
                    <div class="grid-content bg-purple"></div>
                </cmui-col>
                <cmui-col :span="16">
                    <div class="grid-content bg-purple"></div>
                </cmui-col>
                <cmui-col :span="4">
                    <div class="grid-content bg-purple"></div>
                </cmui-col>
            </cmui-row>
        </div>
        <text class="sub-title">对齐方式</text>
        <text class="desc">通过 flex 布局来对分栏进行灵活的对齐。</text>
        <div class="demo-block">
            <cmui-row class="row row-bg">
                <cmui-col :span="6"><div class="grid-content bg-purple"></div></cmui-col>
                <cmui-col :span="6"><div class="grid-content bg-purple-light"></div></cmui-col>
                <cmui-col :span="6"><div class="grid-content bg-purple"></div></cmui-col>
            </cmui-row>
            <cmui-row class="row row-bg" justify="center">
                <cmui-col :span="6"><div class="grid-content bg-purple"></div></cmui-col>
                <cmui-col :span="6"><div class="grid-content bg-purple-light"></div></cmui-col>
                <cmui-col :span="6"><div class="grid-content bg-purple"></div></cmui-col>
            </cmui-row>
            <cmui-row class="row row-bg" justify="end">
                <cmui-col :span="6"><div class="grid-content bg-purple"></div></cmui-col>
                <cmui-col :span="6"><div class="grid-content bg-purple-light"></div></cmui-col>
                <cmui-col :span="6"><div class="grid-content bg-purple"></div></cmui-col>
            </cmui-row>
            <cmui-row class="row row-bg" justify="space-between">
                <cmui-col :span="6"><div class="grid-content bg-purple"></div></cmui-col>
                <cmui-col :span="6"><div class="grid-content bg-purple-light"></div></cmui-col>
                <cmui-col :span="6"><div class="grid-content bg-purple"></div></cmui-col>
            </cmui-row>
            <cmui-row class="row-bg" justify="space-around">
                <cmui-col :span="6"><div class="grid-content bg-purple"></div></cmui-col>
                <cmui-col :span="6"><div class="grid-content bg-purple-light"></div></cmui-col>
                <cmui-col :span="6"><div class="grid-content bg-purple"></div></cmui-col>
            </cmui-row>
        </div>
    </scroller>
</template>

<script>
    module.exports =  {
        components: {
            CmuiRow: require('../widget/row/row.vue'),
            CmuiCol: require('../widget/col/col.vue')
        }
    }
</script>

<style lang="sass" scoped>

    @import './common.scss';

    .cmui-col {
        border-radius: 8;
    }
    .bg-purple {
        background-color: #d3dce6;

        &-dark {
            background-color: #99a9bf;
        }
        &-light {
            background-color: #e5e9f2;
        }
    }
    .grid-content {
        border-radius: 8;
        min-height: 72;
    }
    .row-bg {
        padding-left: 40;
        padding-right: 40;
        background-color: #f9fafc;
    }
    .row {
        margin-bottom: 40;
    }
</style>
