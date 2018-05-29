<template>
    <div class="cmui-item">
        <image class="cmui-item-image" :src="demoUrl"></image>
        <div class="cmui-item-title-container">
            <text v-if="required" class="cmui-item-require">*</text>
            <text class="cmui-item-title">{{title}}</text>
        </div>
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
            from: {
                type: String,
                default: 'all'
            },
            required: {
                type: Boolean,
                default: false
            },
            demoUrl: {
                type: String,
                default: ''
            }
        },
        data () {
            return {
            }
        },
        methods: {
        },
        created () {

        }
    }
</script>

<style lang="sass" scoped>
    @import "dc-media-item"
</style>
