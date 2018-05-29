<template>
    <div>
        <text class="content" v-if="tabitems[0].visibility">TAB 1 的内容</text>
        <text class="content" v-if="tabitems[1].visibility">TAB 2 的内容</text>
        <text class="content" v-if="tabitems[2].visibility">TAB 3 的内容</text>
        <cmui-tabbar :tabitem = "tabitems" :itemstyle = "itemstyle" @tabItemOnClick="tabItemClick"></cmui-tabbar>
    </div>
</template>

<script>
    var modal = weex.requireModule('modal');
    var itemStyle = {
        titleColor: '#000000',
        iconColor:'#666',
        selectedTitleColor: '#ff6a00',
        selectedIconColor: '#ff6a00'
    };
    var tabItems =  [{
        title: 'tab1',
        icon: 'customer',
        visibility: true
    },{
        title: 'tab2',
        icon: 'menu',
        visibility: false
    },{
        title: 'tab3',
        icon: 'star-off',
        visibility: false
    }];

    module.exports =  {
        components: {
            cmuiTabbar: require('../widget/tabbar/tabbar.vue')
        },
        data: function () {
            return {
                tabitems: tabItems,
                itemstyle: itemStyle
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

<style scoped>
    .content {
        font-size: 60;
        text-align: center;
        margin-top: 300;
    }
</style>

