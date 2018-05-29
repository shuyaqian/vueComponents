<template>
    <div>
        <cmui-tab
            :tabitem="tabitem"
            :inline="true"
            :selectedColor = "selectedColor"
            :fontSize="fontSize"
            @tabItemOnClick = "tabItemClick"
        ></cmui-tab>
        <text class="content" v-if="tabitem[0].visibility">TAB 1 的内容</text>
        <text class="content" v-if="tabitem[1].visibility">TAB 2 的内容</text>
        <text class="content" v-if="tabitem[2].visibility">TAB 3 的内容</text>
    </div>
</template>

<script>
    var modal = weex.requireModule('modal');
    var tabList =  [{
        title: 'tab1',
        visibility: true
    },{
        title: 'tab2',
        visibility: false
    },{
        title: 'tab3',
        visibility: false
    }];

    module.exports = {
        components: {
            CmuiTab: require('../widget/tab/tab.vue')
        },
        data () {
            return {
                tabitem: tabList,
                selectedColor: '#0184d7',
                fontSize: 32
            }
        },
        methods: {
            tabItemClick: function (e) {
//                modal.alert({
//                    message:'当前tab:' + e,
//                    okTitle:'ok'
//                });
            }
        }
    }
</script>

<style lang="sass" scoped>

    @import './common.scss';
    .content {
        font-size: 60;
        text-align: center;
        margin-top: 300;
    }
</style>
