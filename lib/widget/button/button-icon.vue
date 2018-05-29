<template>
    <div
        class="cmui-button"
        :class="[
            type ? 'cmui-button-' + type : '',
            size ? 'cmui-button-' + size : '',
            disabled ? 'cmui-button-disabled' : '',
            groupIndex ? 'cmui-button-' + groupIndex : ''
        ]"
        :style="style"
        @click="handleClick">
        <cmui-icon :name="icon" v-if="icon"></cmui-icon>
        <text
            class="cmui-button-inner"
            :class="[
                type ? 'cmui-button-inner-' + type : '',
                size ? 'cmui-button-inner-' + size : '',
                disabled ? 'cmui-button-inner-disabled' : ''
            ]"
            v-if="$slots.default">
            <slot></slot>
        </text>
    </div>
</template>

<script>
    module.exports =  {
        name: 'CmuiButtonIcon',

        componentName: 'CmuiButtonIcon',

        components: {
            CmuiIcon: require('../icon/icon.vue')
        },

        props: {
            type: {
                type: String,
                default: 'default'
            },
            size: String,
            icon: {
                type: String,
                default: ''
            },
            disabled: Boolean,
            groupIndex: String
        },

        computed: {
            isGroup () {
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
            style () {
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
    @import './button-icon.scss';
</style>
