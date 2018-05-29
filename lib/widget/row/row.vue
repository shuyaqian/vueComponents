<template>
    <div class="cmui-row"
        :style="style"
        :class="[
            justify ? 'is-justify-' + justify : '',
            align ? 'is-align-' + align : ''
        ]">
        <slot></slot>
    </div>
</template>

<script>
    module.exports =  {
        name: 'CmuiRow',

        componentName: 'CmuiRow',

        props: {
            gutter: Number,
            justify: {
                type: String,
                default: 'start'
            },
            align: {
                type: String,
                default: 'top'
            }
        },

        computed: {
            style () {
                var ret = {};

                if (this.gutter) {
                    ret.marginLeft = `-${this.gutter / 2}`;
                    ret.marginRight = ret.marginLeft;
                }

                return ret;
            }
        }
    }
</script>

<style lang="sass" scoped>
    @import './row.scss';
</style>
