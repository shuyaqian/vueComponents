<template>
    <div class="cmui-tabbar">
        <div  v-for="(item, key) in tabitem"
              :key="key"
              class="cmui-tabbar-container"
              @click="onclickitem(key)">
            <cmui-icon
                class="cmui-tabbar-icon"
                :name="item.icon"
                :style="[key == selectedIndex ? selectIconStyle : unselectIconStyle]"
            ></cmui-icon>
            <text class="cmui-tabbar-text"
                  :style="[key == selectedIndex ? selectTitleStyle : unselectTitleStyle]"
            >{{item.title}}</text>
        </div>
    </div>
</template>

<script>
    module.exports = {
        name: 'CmuiTabbar',

        componentName: 'CmuiTabbar',

        components: {
            CmuiIcon: require('../icon/icon.vue')
        },
        props: {
            tabitem: Array,
            itemstyle: Object
        },
        data: function () {
            return {
                selectedIndex: 0
            }
        },
        computed: {
            selectIconStyle() {
                let style = {};

                style.color = this.itemstyle.selectedIconColor;

                return style;
            },
            unselectIconStyle() {
                let style = {};

                style.color = this.itemstyle.iconColor;

                return style;
            },
            selectTitleStyle() {
                let style = {};

                style.color = this.itemstyle.selectedTitleColor;

                return style;
            },
            unselectTitleStyle() {
                let style = {};

                style.color = this.itemstyle.titleColor;

                return style;
            }
        },
        methods: {
            onclickitem: function (index) {
                this.selectedIndex = index;
                this.$emit('tabItemOnClick', index);

                for(var i = 0; i < this.tabitem.length; i++) {
                    var tabItem = this.tabitem[i];

                    tabItem.visibility = i==index;

                    Vue.set(this.tabitem, i, Object.assign({}, tabItem));

                }
            }
        }
    }
</script>

<style lang="sass" scoped>
    @import './tabbar.scss';
</style>

