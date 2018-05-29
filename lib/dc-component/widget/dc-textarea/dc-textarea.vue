<template>
    <div class="cmui-cell">
        <text class="cmui-cell-warn">{{warning}}</text>
        <textarea :class="[textAreaStyle=='big'?'cmui-cell-ta-big':'cmui-cell-ta-small']" :value="value"
                  :placeholder="placeholder" :max-length="maxSize" @input="onInput"></textarea>
        <text class="cmui-cell-tips">{{value.length || 0}}/{{maxSize}}</text>
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
            value: {
                type: String,
                default: ''
            },
            placeholder: {
                type: String,
                default: ''
            },
            warning: {
                type: String,
                default: ''
            },
            showWarning: {
                type: Boolean,
                default: false
            },
            maxSize: {
                type: Number,
                default: Number.MAX_VALUE
            },
            textAreaStyle: {
                type: String,
                default: 'big'
            }
        },
        data () {
            return {
            }
        },
        methods: {
            onInput: function (event) {
                var context = this;
                context.value = event.value
                this.$emit('dcTextArea', {
                    key: context.key,
                    result: event.value || ''
                });
            }
        },
        created () {

        }
    }
</script>

<style lang="sass" scoped>
    @import "dc-textarea"
</style>
