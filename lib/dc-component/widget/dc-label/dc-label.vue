<template>
    <div :class="[subType=='group'?'cmui-cell-group':'', 'cmui-cell']">
        <text :class="[subType=='small'?'cmui-cell-small':'cmui-cell-big']">{{title}}</text>
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
    @import "dc-label"
</style>
