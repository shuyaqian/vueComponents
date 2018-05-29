<template>
    <div 
        class="cmui-cell"
        :class="[
            inline ? 'cmui-cell-inline' : 'cmui-cell-vertical',
            last ? 'cmui-cell-last' : ''
        ]"
        @click="handleClick">
        <text 
            class="cmui-label"
            :class="[
                inline ? 'cmui-label-inline' : '',
                align !== 'left' ? 'cmui-label-' + align : ''
            ]"
            :style="labelWidth"
            v-if="label">{{label}}</text>
        <slot></slot>
    </div>
</template>

<script>
    module.exports = {
        name: 'CmuiFormItem',

        componentName: 'CmuiFormItem',

        props: {
            inline: {
                type: Boolean,
                default: true
            },
            align: {
                type: String,
                default: 'left'
            }, 
            label: String,
            width: Number,
            last: Boolean
        },

        computed: {
            labelWidth () {
                let ret = {};

                if (this.width) {
                    ret.width = this.width;
                }

                return ret;
            }
        }
    }
</script>

<style lang="sass" scoped>
    @import './form-item.scss';
</style>
