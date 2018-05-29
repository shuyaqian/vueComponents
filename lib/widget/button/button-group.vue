<template>
    <div class="cmui-button-group">
        <slot></slot>
    </div>
</template>

<script>
    module.exports =  {
        name: 'CmuiButtonGroup',

        componentName: 'CmuiButtonGroup'
    };
</script>

<style lang="sass" scoped>
    @import './button-group.scss';
</style>
