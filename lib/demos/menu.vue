<template>
        <cmui-menu
            :menuList="menuList"
            :selectedColor="selectedColor"
            :hasBorder="hasBorder"
            :hasFt="hasFt"
            @tabItemOnClick="tabItemOnClick"
            @menuOnClick="menuOnClick"
            @ftclick="ftclick">
            <slot>
            </slot>
        </cmui-menu>
</template>

<script>
    var modal = weex.requireModule('modal');

    module.exports = {
        components: {
            CmuiMenu: require('../widget/menu/menu.vue')
        },
        data() {
            return {
                menuList: [{tab: "Tab1", options: ["选项选项选项0", "选项选项1", "选项选项2", "选项选项3"]},
                    {tab: "Tab2", options: ["Tab2选项0", "Tab2选项13333233", "Tab2选项2", "Tab2选项3"]}],
                selectedColor: '#FF6A00',
                hasBorder: false,
                hasFt: true
            }
        },
        methods: {
            tabItemOnClick(event) {

            },
            menuOnClick(event) {

            },
            ftclick(event) {

            }
        }
    }
</script>

<style lang="sass" scoped>
    @import './common.scss';
</style>
