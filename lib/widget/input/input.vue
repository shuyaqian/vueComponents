<template>
    <input
        class="cmui-input"
        :class="[
            disabled ? 'is-disabled' : ''
        ]"
        :type="type"
        :value="currentValue"
        :index="index"
        :placeholder="placeholder"
        :autofocus="autofocus"
        :disabled="disabled"
        @input="handleInput"
        @focus="handleFocus"
        @blur="handleBlur"></input>
</template>

<script>
    module.exports =  {
        name: 'CmuiInput',

        componentName: 'CmuiInput',

        data() {
            return {
                currentValue: this.value
            };
        },

        props: {
            type: {
                type: String,
                default: 'text'
            },
            index: String,
            value: [String, Number],
            placeholder: {
                type: String,
                default: '请输入'
            },
            autofocus: Boolean,
            disabled: Boolean,
            maxlength: Number
        },

        watch: {
            'value' (val, oldValue) {
                this.setCurrentValue(val);
            }
        },

        methods: {
            handleBlur(event) {
                this.$emit('blur', event);
            },
            handleFocus(event) {
                this.$emit('focus', event);
            },
            handleInput(event) {
                var value = event.target.attr.value;
                var index = event.target.attr.index;

                var input = {index: index, value: value};

                this.$emit('input', input);

                this.setCurrentValue(value);

                this.$emit('change', value);
            },
            setCurrentValue(value) {
                if (value === this.currentValue) {
                    return;
                }

                this.currentValue = value;
            }
        }
    }
</script>

<style lang="sass" scoped>
    @import './input.scss';
</style>
