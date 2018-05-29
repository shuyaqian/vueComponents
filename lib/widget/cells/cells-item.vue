<template>
    <div class="cmui-cells">
        <text
            class="cmui-cells-title"
            v-if="title">{{title}}</text>
        <slot></slot>
    </div>
</template>

<script>
    module.exports =  {
        name: 'CmuiCells',

        componentName: 'CmuiCells',

        props: {
            title: String
        }
    }
</script>

<style lang="sass" scoped>
    @import './cells-item.scss';
</style>
