<template>
    <div class="cmui-textarea">
        <textarea
            :class="{
                'is-disabled': disabled
            }"
            :style="{fontSize: fontsize}"
            :rows="rows"
            :value="currentValue"
            :placeholder="placeholder"
            :autofocus="autofocus"
            :disabled="disabled"
            :maxlength="total"
            @input="handleInput"></textarea>
        <div class="cmui-textarea-counter">
            <text class="cmui-textarea-text cmui-textarea-text-current">{{current}}</text>
            <text class="cmui-textarea-separate">{{separate}}</text>
            <text class="cmui-textarea-text">{{total}}</text>
        </div>
    </div>
</template>

<script>
    var modal = weex.requireModule('modal');

    module.exports =  {
        name: 'CmuiTextarea',

        componentName: 'CmuiTextarea',

        props: {
            value: [String, Number],
            placeholder: {
                type: String,
                default: '请输入'
            },
            rows: {
                type: Number,
                default: 4
            },
            fontsize: {
                type: Number,
                default: 28
            },
            separate: {
                type: String,
                default: '/'
            },
            total: {
                type: [String, Number],
                default: 200
            }
        },

        data() {
            return {
                currentValue: this.value,
                current: 0
            }
        },

        methods: {
            handleInput(event) {
                var value = event.value;

                this.$emit('input', value);

                this.computeInputNum(value);
            },
            computeInputNum: function (str) {
                var len = 0;
                if (str == null || str == "") {
                    len = 0;
                }
                for (var i = 0, alen = str.length; i < alen; i++) {
                    var code = str.charCodeAt(i);

                    if (code > 255) {
                        len = len + 1;
                    } else {
                        len++;
                    }
                }
                this.remindNum(len);
            },
            remindNum: function (num) {
                if(num == 200) {
                    modal.toast({
                        message: "最多允许输入" + this.total + "个字符" ,
                        duration: 1
                    });
                }
                this.current = num;
            }
        }
    }
</script>

<style lang="sass" scoped>
    @import './textarea-counter.scss';
</style>
