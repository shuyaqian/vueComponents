<template>
    <div class="cmui-cell">
        <div class="cmui-cell-row" @click="handleClick">
            <text class="cmui-cell-bd">{{title}}</text>
            <input :max-length="maxSize" v-if="!readOnly" class="cmui-cell-fi"
                   :type="inputType" @input="onInput" :value="value" :placeholder="placeholder"/>
            <text v-if="readOnly" class="cmui-cell-ft" :placeholder="placeholder">{{value}}</text>
        </div>
        <div class="cmui-cell-row" v-if="showWarning">
            <text class="cmui-cell-bd"></text>
            <text class="cmui-cell-warn">{{warning}}</text>
        </div>
    </div>

</template>
<script>
    const picker = weex.requireModule('picker')
    module.exports = {
        components: {
        },
        computed: {
            inputType:function () {
                if (this.subType == 'TIME'){
                    return 'time'
                } else if (this.subType == 'DATE'){
                    return 'date'
                } else if (this.subType == 'INT'){
                    return 'number'
                } else if (this.subType == 'PHONE'){
                    return 'tel'
                } else {
                    return 'text'
                }
            }
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
            subType: {
                type: String,
                default:'text'
            },
            readOnly: {
                type: Boolean,
                default: false
            },
            value: {
                type: String,
                default: ''
            },
            suffix: {
                type: String,
                default: ''
            },
            placeholder: {
                type: String,
                default: ''
            },
            warning: {
                type: String,
                default:''
            },
            showWarning: {
                type: Boolean,
                default: false
            },
            maxSize: {
                type: Number,
                default:Number.MAX_VALUE
            }
        },
        data () {
            return {
                type: this.subType
            }
        },
        methods: {
            onInput:function (event) {
                var context = this;
                this.$emit('dcInput', {
                    key:context.key,
                    result:event.value || ''
                });
            }
        },
        created () {

        }
    }
</script>

<style lang="sass" scoped>
    @import "dc-input"
</style>
