<template>
    <text
        class="cmui-button-plain"
        :class="[
            type ? 'cmui-button-' + type : '',
            size ? 'cmui-button-' + size : '',
            disabled ? 'cmui-button-disabled' : ''
        ]"
        @click="handleClick">
        <slot></slot>
    </text>
</template>

<script>
    module.exports =  {
        name: 'CmuiButton',

        componentName: 'CmuiButton',

        props: {
            type: {
                type: String,
                default: 'default'
            },
            size: String,
            disabled: Boolean
        },

        methods: {
            handleClick (evt) {
                this.$emit('click', evt);
            }
        }
    }
</script>

<style lang="sass" scoped>
    @import './button-plain.scss';
</style>
