<template>
    <scroller class="page">
        <text class="title">Typography 字体</text>
        <text class="desc">对字体进行统一规范，力求在各个操作系统下都有最佳展示效果。</text>
        <text class="sub-title">中文字体</text>
        <div class="demo-typo-box" style="font-family: 'PingFang SC'">
            <text class="box-hd">移动工作台</text>
            <text class="name">PingFang SC</text>
        </div>
        <div class="demo-typo-box" style="font-family: 'Hiragino Sans GB'">
            <text class="box-hd">移动工作台</text>
            <text class="name">Hiragino Sans GB</text>
        </div>
        <div class="demo-typo-box" style="font-family: 'Microsoft YaHei'">
            <text class="box-hd">移动工作台</text>
            <text class="name">Microsoft YaHei</text>
        </div>
        <text class="sub-title">英文／数字字体</text>
        <div class="demo-typo-box" style="font-family: -apple-system-font">
            <text class="box-hd">CRM mobile</text>
            <text class="name">-apple-system-font</text>
        </div>
        <div class="demo-typo-box" style="font-family: 'Helvetica Neue'">
            <text class="box-hd">CRM mobile</text>
            <text class="name">Helvetica Neue</text>
        </div>
        <text class="sub-title">Font-family 代码</text>
        <div class="demo-code-box">
            <text class="code">font-family: -apple-system-font, "Helvetica Neue", "PingFang SC", "Hiragino Sans GB", "Microsoft YaHei", sans-serif;</text>
        </div>
        <text class="sub-title">字体使用规范</text>
        <div class="demo-block">
            <text class="txt" style="font-size: 36">主标题</text>
            <text class="txt" style="font-size: 32">标题</text>
            <text class="txt" style="font-size: 28">正文</text>
            <text class="txt" style="font-size: 24">辅助文字</text>
        </div>
    </scroller>
</template>

<script>
    module.exports =  {}
</script>

<style lang="sass" scoped>

    @import './common.scss';

    .demo-typo-box {
        margin-right: 40;
        margin-bottom: 40;
        padding-bottom: 72;
        height: 400;
        border-style: solid;
        border-color: #dcded3;
        border-width: 1;
        border-radius: 8;
    }
    .box-hd {
        padding-left: 30;
        padding-right: 30;
        line-height: 324;
        font-size: 80;
        color: #666;
        text-align: center;
    }
    .name {
        position: absolute;
        left: 0;
        bottom: 0;
        right: 0;
        padding-left: 24;
        padding-right: 24;
        height: 70;
        line-height: 70;
        border-top-style: solid;
        border-top-color: #dcded3;
        border-top-width: 1;
        font-size: 28;
        color: #0184d7;
        text-align: left;
        text-indent: 20;
        font-family: 'Helvetica Neue';
    }
    .demo-code-box {
        margin-bottom: 50;
        padding-top: 30;
        padding-right: 50;
        padding-bottom: 30;
        padding-left: 50;
        background-color: #f2f3f7;
        border-style: solid;
        border-color: #dcded3;
        border-width: 1;
        border-radius: 8;
        color: #000;
        overflow-x: auto;
    }
    .code {
        font-size: 24;
        color: #333;
    }
    .txt {
        padding-bottom: 10;
    }
</style>
