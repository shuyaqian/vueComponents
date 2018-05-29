<template>
    <scroller class="page">
        <text class="title">Tab 标签页</text>
        <text class="desc">分隔内容上有关联但属于不同类别的数据集合。</text>
        <text class="sub-title">横向Tab</text>
        <text class="desc">横向基础的、简洁的标签页。</text>
        <div class="demo-block" style="background-color: #f2f3f7">
            <cmui-tab
                :tabitem="tabList"
                :inline="true"
                :selectedColor = "selectedColor"
            ></cmui-tab>
        </div>
        <text class="sub-title">纵向Tab</text>
        <text class="desc">纵向标签页。</text>
        <div class="demo-block">
            <cmui-tab
                :tabitem="tabList2"
                :inline="false"
                :tabWidth="tabWidth"
            ></cmui-tab>
        </div>
    </scroller>
</template>

<script>
    var tabList =  [{title: 'tab1'},{title: 'tab2'},{title: 'tab3'}];
    var tabList2 =  [{title: 'tab1'},{title: 'tab2'},{title: 'tab3'}];

    module.exports =  {
        components: {
            CmuiTab: require('../widget/tab/tab.vue')
        },
        data () {
            return {
                tabList: tabList,
                tabList2: tabList2,
                tabWidth: 200,
                selectedColor: '#0184d7'
            }
        }
    }
</script>

<style lang="sass" scoped>

    @import './common.scss';
</style>
