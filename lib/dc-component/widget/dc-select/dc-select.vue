<template>
    <div class="cmui-cell cmui-cell-access" @click="handleClick">
        <text class="cmui-cell-bd">{{title}}</text>
        <text :class="[ showWarning?'cmui-cell-warn':(value ?'cmui-cell-ft':'cmui-cell-ph') ]">{{showWarning ? warning : (value || placeholder)}}</text>
        <cmui-icon class="cmui-icon-access" name="arrow-right"></cmui-icon>
    </div>
</template>
<script>
    const picker = weex.requireModule('picker')
    module.exports = {
        components: {
            CmuiIcon: require('@ali/weex-ui-components/icon')
        },
        props: {
            title: {
                type: String,
                default: ''
            },
            key: {
                type: String,
                default: ''
            },
            value: {
                type: String,
                default: ''
            },
            placeholder: {
                type: String,
                default: ''
            },
            options: {
                type: JSON,
                default: []
            },
            warning: {
                type: String,
                default: ''
            },
            showWarning: {
                type: Boolean,
                default: false
            }
        },
        computed: {
            optionItems: function () {
                let item = [];
                for (let i = 0; i < this.options.length; i++) {
                    item.push(this.options[i].value)
                }
                return item;
            }
        },
        data () {
            return {
                selectIndex: -1
            }
        },
        methods: {
            handleClick(){
                var context = this;
                if (this.options && this.options.length > 0) {
                    picker.pick({
                        items: context.optionItems,
                        index: this.selectIndex
                    }, (ret) => {
                        if (ret && ret.result === 'success' && ret.data != -1) {
                            context.selectIndex = ret.data
                            context.value = context.options[context.selectIndex].value
                            context.$emit('dcSelect', {
                                key: context.key,
                                index: context.selectIndex,
                                result: context.options[context.selectIndex]
                            });
                        }
                    })
                }
            }
        },
        created () {

        }
    }
</script>

<style lang="sass" scoped>
    @import "dc-select"
</style>
