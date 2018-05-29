<template>
    <textarea
        class="cmui-textarea"
        :class="{
            'is-disabled': disabled
        }"
        :rows="rows"
        :value="currentValue"
        :placeholder="placeholder"
        :autofocus="autofocus"
        :disabled="disabled"
        @focus="handleFocus"
        @blur="handleBlur"
        @input="handleInput"></textarea>
</template>

<script>
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
                default: 2
            },
            autofocus: Boolean,
            disabled: Boolean,
            maxlength: Number
        },

        data() {
            return {
                currentValue: this.value
            }
        },

        watch: {
            'value' (val, oldValue) {
                this.setCurrentValue(val);
            }
        },

        methods: {
            handleBlur (event) {
                this.$emit('blur', event);
            },
            handleFocus (event) {
                this.$emit('focus', event);
            },
            handleInput (event) {
                let value = event.target.attr.value;

                this.$emit('input', value);

                this.setCurrentValue(value);

                this.$emit('change', value);
            },
            setCurrentValue (value) {
                if (value === this.currentValue) {
                    return;
                }

                this.currentValue = value;
            },
            getLen (str) {
                let len = 0;

                if (typeof str !== 'string') {
                    return len;
                }

                for (let i = 0; i < str.length; i++) {
                    if (str[i].charCodeAt(i) > 0 && str[i].charCodeAt(i) <= 128) {
                        len++;
                    } else {
                        len += 2;
                    }
                }

                return len;
            }
        }
    }
</script>

<style lang="sass" scoped>
    @import './textarea.scss';
</style>
