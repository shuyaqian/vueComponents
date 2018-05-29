<template>
    <div :class="[
            inline ? 'cmui-tab' : 'cmui-tab-vertical'
        ]"
         :style="style">
        <text :class="[
                inline ? 'cmui-tab-item' : 'cmui-vertical-item'
            ]"
              v-for="(item, key) in tabitem"
              :key="key"
              :style="[key == selectedIndex || item.visibility ? selectStyle : unselectStyle]"
              @click="onclickitem(key)">{{item.title}}</text>
    </div>
</template>

<script>
    module.exports = {
        name: 'CmuiTab',

        componentName: 'CmuiTab',

        data: function () {
            return {
                selectedIndex: 0
            }
        },
        props: {
            inline: Boolean,
            tabWidth: Number,
            tabitem: Array,
            fontSize: {
                type: Number,
                default: 28
            },
            selectedColor: {
                type: String,
                default: '#FF6A00'
            }
        },
        computed: {
            style() {
                let style = {};

                if (!this.inline) {
                    style.width = this.tabWidth;
                }
                style.height = this.height;

                return style;
            },
            selectStyle() {
                let style = {};
                style.fontSize = this.fontSize;

                if (this.inline) {
                    style.color = this.selectedColor;
                    style.borderBottomColor = this.selectedColor;
                    style.borderBottomWidth = 2;
                } else {
                    style.color = this.selectedColor;
                    style.backgroundColor = '#FFF';
                    style.borderLeftColor = this.selectedColor;
                    style.borderLeftWidth = 4;
                }

                return style;
            },
            unselectStyle() {
                let style = {};
                style.fontSize = this.fontSize;

                if (this.inline) {
                    style.color = '#666';
                    style.borderBottomColor = '#DCDED3';
                    style.borderBottomWidth = 1;
                } else {
                    style.color = '#666';
                    style.backgroundColor = '#F2F3F7';
                    style.borderLeftColor = '#F2F3F7';
                }

                return style;
            }
        },

        methods: {
            onclickitem(index) {
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
    @import './tab.scss';
</style>
