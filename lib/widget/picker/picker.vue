<template>
    <text
        class="cmui-picker"
        :class="[
            !value ? 'cmui-placeholder' : ''
        ]"
        :index="index"
        @click="select">{{value}}</text>
</template>

<script>
    let picker = weex.requireModule('picker');

    module.exports = {
        name: 'CmuiPicker',

        componentName: 'CmuiPicker',

        props: {
            type: {
                type: String,
                default: 'date'
            },
            index: String,
            value: String
        },

        computed: {
            pickerFunc () {
                // 默认选择日期
                let funcName = 'pickDate';

                if (this.type === 'time') {
                    funcName = 'pickTime';  // 选择时间
                }

                return funcName;
            }
        },

        methods: {
            select (e) {
                var self = this;
                picker[this.pickerFunc]({
                    value: this.value
                }, event => {
                    if (event.result === 'success') {
                        self.value = event.data;
                        var data = {index: self.index, value: this.value}

                        self.$emit('pick', data);
                    }
                });
            }
        }
    }
</script>

<style lang="sass" scoped>
    @import './picker.scss';
</style>
