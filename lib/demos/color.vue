<template>
    <scroller class="page">
        <text class="title">Color 色彩</text>
        <text class="desc">根据 DPL 标准，统一色觉基调。</text>
        <text class="sub-title">主色</text>
        <text class="desc">DPL 定义的主要品牌色有橙色和蓝色。</text>
        <cmui-row :gutter="20">
            <cmui-col :span="8">
                <div class="demo-color-box" style="background-color: #ff6a00">
                    <text class="box-hd">Orange brand</text>
                    <text class="value">#ff6a00</text>
                </div>
            </cmui-col>
            <cmui-col :span="8">
                <div class="demo-color-box" style="background-color: #0184d7">
                    <text class="box-hd">Blue brand</text>
                    <text class="value">#0184d7</text>
                </div>
            </cmui-col>
        </cmui-row>
        <text class="sub-title">辅助色</text>
        <text class="desc">除了主色外的场景色，需要在不同的场景中使用。</text>
        <cmui-row :gutter="20" style="margin-bottom:20">
            <cmui-col :span="8">
                <div class="demo-color-box" style="background-color: #038ee7">
                    <text class="box-hd">Blur for line</text>
                    <text class="value">#038ee7</text>
                </div>
            </cmui-col>
            <cmui-col :span="8">
                <div class="demo-color-box" style="background-color: #0289df">
                    <text class="box-hd">Blur for background</text>
                    <text class="value">#0289df</text>
                </div>
            </cmui-col>
            <cmui-col :span="8">
                <div class="demo-color-box" style="background-color: #1086cc">
                    <text class="box-hd">Blue for icon</text>
                    <text class="value">#1086cc</text>
                </div>
            </cmui-col>
        </cmui-row>
        <cmui-row :gutter="20">
            <cmui-col :span="8">
                <div class="demo-color-box" style="background-color: #ff3333">
                    <text class="box-hd">Warning</text>
                    <text class="value">#ff3333</text>
                </div>
            </cmui-col>
            <cmui-col :span="8"></cmui-col>
            <cmui-col :span="8"></cmui-col>
        </cmui-row>
        <text class="sub-title">中立色</text>
        <text class="desc">中立色用于文本、背景和边框颜色。通过运用不同的中性色，来表现层次结构。</text>
        <text class="sub-title">文本色</text>
        <cmui-row :gutter="20" style="margin-bottom:20">
            <cmui-col :span="8">
                <div class="demo-color-box" style="background-color: #000">
                    <text class="box-hd">Black text</text>
                    <text class="value">#000000</text>
                </div>
            </cmui-col>
            <cmui-col :span="8">
                <div class="demo-color-box" style="background-color: #333">
                    <text class="box-hd">Darker text</text>
                    <text class="value">#333333</text>
                </div>
            </cmui-col>
            <cmui-col :span="8">
                <div class="demo-color-box" style="background-color: #666">
                    <text class="box-hd">Dark text</text>
                    <text class="value">#666666</text>
                </div>
            </cmui-col>
        </cmui-row>
        <cmui-row :gutter="20">
            <cmui-col :span="8">
                <div class="demo-color-box" style="background-color: #999">
                    <text class="box-hd">Gray text</text>
                    <text class="value">#999999</text>
                </div>
            </cmui-col>
            <cmui-col :span="8">
                <div class="demo-color-box" style="background-color: #c7c7c7">
                    <text class="box-hd">Light text</text>
                    <text class="value">#c7c7c7</text>
                </div>
            </cmui-col>
            <cmui-col :span="8">
                <div class="demo-color-box" style="background-color: #ffffff; border: 1px solid #dcded3; color: #333">
                    <text class="box-hd black">White</text>
                    <text class="value">#ffffff</text>
                </div>
            </cmui-col>
        </cmui-row>
        <text class="sub-title">背景色</text>
        <cmui-row :gutter="20">
            <cmui-col :span="8">
                <div class="demo-color-box" style="background-color: #ebecf0; color: #333">
                    <text class="box-hd">Dark background</text>
                    <text class="value">#ebecf0</text>
                </div>
            </cmui-col>
            <cmui-col :span="8">
                <div class="demo-color-box" style="background-color: #f2f3f7; color: #333">
                    <text class="box-hd">Normal background</text>
                    <text class="value">#f2f3f7</text>
                </div>
            </cmui-col>
            <cmui-col :span="8">
                <div class="demo-color-box" style="background-color: #f7f8fa; color: #333">
                    <text class="box-hd">Light background</text>
                    <text class="value">#f7f8fa</text>
                </div>
            </cmui-col>
        </cmui-row>
        <text class="sub-title">边框色</text>
        <cmui-row :gutter="20">
            <cmui-col :span="8">
                <div class="demo-color-box" style="background-color: #c4c6cf; color: #333">
                    <text class="box-hd">Dark line</text>
                    <text class="value">#c4c6cf</text>
                </div>
            </cmui-col>
            <cmui-col :span="8">
                <div class="demo-color-box" style="background-color: #dcded3; color: #333">
                    <text class="box-hd">Normal line</text>
                    <text class="value">#dcded3</text>
                </div>
            </cmui-col>
            <cmui-col :span="8">
                <div class="demo-color-box" style="background-color: #e6e7eb; color: #333">
                    <text class="box-hd">Light line</text>
                    <text class="value gray">#e6e7eb</text>
                </div>
            </cmui-col>
        </cmui-row>
        <text class="sub-title">透明色</text>
        <cmui-row :gutter="20" style="margin-bottom:20">
            <cmui-col :span="8">
                <div class="demo-color-box" style="background-color: rgba(0, 0, 0, 0.7)">
                    <text class="box-hd">Dark opacity</text>
                    <text class="value">rgba(0, 0, 0, 0.7)</text>
                </div>
            </cmui-col>
            <cmui-col :span="8">
                <div class="demo-color-box" style="background-color: rgba(0, 0, 0, 0.5)">
                    <text class="box-hd">Normal opacity</text>
                    <text class="value">rgba(0, 0, 0, 0.5)</text>
                </div>
            </cmui-col>
            <cmui-col :span="8">
                <div class="demo-color-box" style="background-color: rgba(0, 0, 0, 0.2)">
                    <text class="box-hd">Light opacity</text>
                    <text class="value">rgba(0, 0, 0, 0.2)</text>
                </div>
            </cmui-col>
        </cmui-row>
        <cmui-row :gutter="20">
            <cmui-col :span="8">
                <div class="demo-color-box" style="background-color: rgba(0, 0, 0, 0.1)">
                    <text class="box-hd">Lighter opacity</text>
                    <text class="value">rgba(0, 0, 0, 0.1)</text>
                </div>
            </cmui-col>
            <cmui-col :span="8">
                <div class="demo-color-box" style="background-color: rgba(255, 255, 255, 0.5); border: 1px solid #dcded3; color: #333">
                    <text class="box-hd black">White opacity</text>
                    <text class="value">rgba(255, 255, 255, 0.5)</text>
                </div>
            </cmui-col>
        </cmui-row>
    </scroller>
</template>

<script>
    module.exports =  {
        components: {
            CmuiRow: require('../widget/row/row.vue'),
            CmuiCol: require('../widget/col/col.vue'),
            CmuiIcon: require('../widget/icon/icon.vue')
        }
    }
</script>

<style lang="sass" scoped>

    @import './common.scss';

    .demo-color-box {
        box-sizing: border-box;
        padding: 20;
        border-radius: 8;
        color: #fff;
    }
    .box-hd {
        padding-bottom: 10;
        font-size: 28;
        color: #fff;
    }
    .value {
        color: darken(#fff, 10%)
    }
    .black {
        color: darken(#fff, 30%)
    }
    .gray {
        color: #000;
    }
</style>
