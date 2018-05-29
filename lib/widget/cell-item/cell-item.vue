<template>
    <div 
        class="cmui-cell"
        :class="[
            access ? 'cmui-cell-access' : '',
            last ? 'cmui-cell-last' : ''
        ]"
        @click="handleClick">
        <image 
            class="cmui-cell-hd cmui-cell-icon" 
            :src="cellIcon"
            v-if="cellIcon"></image>
        <text class="cmui-cell-bd">{{title}}</text>
        <text class="cmui-cell-ft">{{desc}}</text>
        <cmui-icon 
            class="cmui-icon-access" 
            name="arrow-right" 
            v-if="access"></cmui-icon>
    </div>
</template>

<script>
    module.exports = {
        name: 'CmuiCellItem',

        componentName: 'CmuiCellItem',

        components: {
            CmuiIcon: require('../icon/icon.vue')
        },

        props: {
            access: Boolean,
            last: Boolean,
            cellIcon: String,
            title: {
                type: String,
                default: '标题文字'
            },
            desc: {
                type: String,
                default: '说明文字'
            }
        },

        methods: {
            handleClick (evt) {
                this.access && this.$emit('click', evt);
            }
        }
    }
</script>

<style lang="sass" scoped>
    @import './cell-item.scss';
</style>
