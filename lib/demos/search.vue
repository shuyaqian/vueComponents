<template>
    <scroller class="page">
        <text class="title">Search组件</text>
        <text class="desc">搜索场景</text>
        <div class="demo-block">
            <cmui-search></cmui-search>
        </div>
    </scroller>
</template>

<script>
    module.exports =  {
        components: {
            CmuiSearch: require('../widget/search/search.vue')
        }
    }
</script>

<style lang="sass" scoped>

    @import './common.scss';
</style>
