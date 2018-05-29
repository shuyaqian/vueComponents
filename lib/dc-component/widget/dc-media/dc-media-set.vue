<template>
    <div class="cmui-cell">
        <scroller class="cmui-cell-scroller" scroll-direction="horizontal">
            <div class="cmui-cell-item" v-for="(item, index) in mediaItemKeys" v-on:click="handleClick(index, item)">
                <dc-media-item :title="item.title" :demoUrl="item.demoUrl" :key="item.key"
                               :subType="item.subType" :required="item.required" :readOnly="item.readOnly"
                               :maxTime="item.maxTime" :compressionRatio="item.compressionRatio"></dc-media-item>
            </div>
        </scroller>
    </div>
</template>
<script>
    module.exports = {
        props: {
            title: {
                type: String,
                default: ''
            },
            key: {
                type: String,
                default: ''
            },
            subType: {
                type: String,
                default: 'big'
            },
            mediaItemKeys: {
                type: JSON,
                default: []
            },
            readOnly: {
                type: Boolean,
                default: false
            }
        },
        components: {
            dcMediaItem: require('./dc-media-item.vue')
        },
        data () {
            return {}
        },
        methods: {
            handleClick: (index, item) => {
                var modal = weex.requireModule('modal')
                modal.alert({message:JSON.stringify(item), duration:0.3})
            }
        },
        created () {

        }
    }
</script>

<style lang="sass" scoped>
    @import "dc-media-set"
</style>
