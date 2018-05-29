<template>
    <scroller class="page">
        <div class="component-title">
            <image :src="logoimg" class="logo-img"></image>
            <text class="title">GTS-List</text>
        </div>
        <text class="desc">纯文字无序列表:</text>
        <div class="demo-block">
            <cmui-list
            v-for="(item, key) in itemList"
            key="key"
            :itemTitle="item.itemTitle"
            :itemContent="item.itemContent"
            :itemName="item.itemName"
            :itemTime="item.itemTime"
            :itemStatus="item.itemStatus"></cmui-list>
        </div>
        <text class="desc">图文混排列表:</text>
        <div class="demo-block">
            <cmui-list
            v-for="(item, key) in itemList"
            key="key"
            :inline="true"
            :imgSrc="item.imgSrc"
            :itemTitle="item.itemTitle"
            :itemContent="item.itemContent"
            :itemName="item.itemName"
            :nameColor="nameColor"
            :nameSize="nameSize"
            :itemTime="item.itemTime"
            :timeColor="timeColor"
            :timeSize="timeSize"
            :statusColor="statusColor"
            :statusSize="statusSize"
            :itemStatus="item.itemStatus"></cmui-list>
        </div>
        <text class="desc">有序列表:</text>
        <div class="demo-block">
            <cmui-list
                v-for="(item, key) in itemList"
                key="key"
                :hasIndex="true"
                :index="key"
                :itemTitle="item.itemTitle"
                :itemContent="item.itemContent"
                :itemName="item.itemName"
                :itemTime="item.itemTime"
                :itemStatus="item.itemStatus"></cmui-list>
        </div>
        <text class="desc">无序节点列表:</text>
        <div class="demo-block">
            <cmui-list
                v-for="(item, key) in itemList"
                key="key"
                :hasNode="true"
                :inline="true"
                :index="key"
                :itemTitle="item.itemTitle"
                :itemContent="item.itemContent"
                :itemName="item.itemName"
                :itemTime="item.itemTime"
                :itemStatus="item.itemStatus"></cmui-list>
        </div>
    </scroller>
</template>

<script>
    var itemList=[{
        imgSrc: 'https://gw.alicdn.com/tfs/TB1RrLuPFXXXXcnXFXXXXXXXXXX-72-72.png',
        itemTitle: 'item list',
        itemContent: 'content content content content content content content content content content content content content content ',
        itemName: '张三',
        itemTime: '2016.09.04 13:14',
        itemStatus: '已签约'
    },{
        imgSrc: 'https://gw.alicdn.com/tfs/TB1RrLuPFXXXXcnXFXXXXXXXXXX-72-72.png',
        itemTitle: 'item list',
        itemContent: 'content content content content content content content content content content content content content content ',
        itemName: '张三',
        itemTime: '2016.09.04 13:14',
        itemStatus: '已签约'
    },{
        imgSrc: 'https://gw.alicdn.com/tfs/TB1RrLuPFXXXXcnXFXXXXXXXXXX-72-72.png',
        itemTitle: 'item list',
        itemContent: 'content content content content content content content content content content content content content content ',
        itemName: '张三',
        itemTime: '2016.09.04 13:14',
        itemStatus: '已签约'
    },{
        imgSrc: 'https://gw.alicdn.com/tfs/TB1RrLuPFXXXXcnXFXXXXXXXXXX-72-72.png',
        itemTitle: 'item list',
        itemContent: 'content content content content content content content content content content content content content content ',
        itemName: '张三',
        itemTime: '2016.09.04 13:14',
        itemStatus: '已签约'
    },{
        imgSrc: 'https://gw.alicdn.com/tfs/TB1RrLuPFXXXXcnXFXXXXXXXXXX-72-72.png',
        itemTitle: 'item list',
        itemContent: 'content content content content content content content content content content content content content content ',
        itemName: '张三',
        itemTime: '2016.09.04 13:14',
        itemStatus: '已签约'
    }]
    module.exports =  {
        components: {
            CmuiList: require('../widget/list/list.vue')
        },
        data () {
            return {
                logoimg:'https://gw.alicdn.com/tfs/TB1PaIWSFXXXXasXpXXXXXXXXXX-109-77.png',
                itemList: itemList,
                nameColor: 'red',
                nameSize: 24,
                timeColor: 'blue',
                timeSize: 30,
                statusColor: 'green',
                statusSize: 40
            }
        },
        methods: {

        },
        created () {

        }
    }
</script>

<style lang="sass" scoped>
    @import './common.scss';
</style>
