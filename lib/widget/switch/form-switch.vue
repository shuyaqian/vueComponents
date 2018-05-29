<template>
    <div class="cmui-switch">
        <switch
            :checked="checked"
            :disabled="disabled"
            @change="change"></switch>
    </div>
</template>

<script>
    module.exports =  {
        name: 'CmuiSwitch',

        componentName: 'CmuiSwitch',

        props: {
            checked: Boolean,
            disabled: Boolean
        },

        methods: {
            change (e) {
                this.checked = e.value;

                this.$emit('change', e);
            }
        }
    }
</script>

<style lang="sass" scoped>
    @import './switch.scss';
</style>
