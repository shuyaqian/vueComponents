<template>
    <div class="cmui-col"
        :style="style"
        :class="[
            span ? 'cmui-col-' + span : ''
        ]">
        <slot></slot>
    </div>
</template>

<script>
    module.exports =  {
        name: 'CmuiCol',

        componentName: 'CmuiCol',

        props: {
            span: {
                type: Number,
                default: 24
            }
        },

        computed: {
            gutter () {
                let parent = this.$parent;

                while (parent && parent.$options.componentName !== 'CmuiRow') {
                    parent = parent.$parent;
                }

                return parent ? parent.gutter : 0;
            },
            style () {
                let style = {};

                if (this.gutter) {
                    style.paddingLeft = this.gutter / 2;
                    style.paddingRight = style.paddingLeft;
                }

                return style;
            }
        }
    }
</script>

<style lang="sass" scoped>
    @import './col.scss';
</style>
