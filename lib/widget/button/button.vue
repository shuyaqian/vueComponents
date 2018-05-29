<template>
    <text
        class="cmui-button"
        :class="[
            type ? 'cmui-button-' + type : '',
            size ? 'cmui-button-' + size : '',
            disabled ? 'cmui-button-disabled' : '',
            groupIndex ? 'cmui-button-' + groupIndex : ''
        ]"
        :style="style"
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
            disabled: Boolean,
            groupIndex: String
        },

        computed: {
            isGroup() {
                let parent = this.$parent;

                while (parent) {
                    if (parent.$options.componentName !== 'CmuiButtonGroup') {
                        parent = parent.$parent;
                    } else {
                        return true;
                    }
                }

                return false;
            },
            style() {
                let style = {};

                if (this.isGroup) {
                    style.borderRadius = 0;
                }

                return style;
            }
        },

        methods: {
            handleClick (evt) {
                this.$emit('click', evt);
            }
        }
    }
</script>

<style lang="sass" scoped>
    @import './button.scss';
</style>
