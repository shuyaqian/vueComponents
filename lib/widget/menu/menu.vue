<template>
    <div>
        <slot name="list"></slot>
        <slot name="empty"></slot>
        <div class="customer-total-container" @click="clearConditons" v-if="canClear">
            <text class="customer-total" v-if="hasotherCondition">{{searchText}} , </text>
            <text class="customer-total">共有{{totalSize}}位客户</text>
            <text class="customer-total" v-if="hasCondition || menuselectedIndex[selectedIndex] !== 0 || hasotherCondition || otherChanged"> , </text>
            <text class="clear-condition" v-if="hasCondition || menuselectedIndex[selectedIndex] !== 0 || hasotherCondition || otherChanged">清空条件</text>
        </div>
        <div v-if="showOptions" class="cmui-options-container" @click = "hideOptions"></div>
        <div class="cmui-options" ref="options">
            <div class="cmui-options-item"
                 v-for="(item, key) in optionsList"
                 @click="onclickmenu(key)">
                <text class="cmui-options-text"
                      :style="{backgroundColor: key == menuselectedIndex[selectedIndex] ? selectedColor : '#F2F3F7',
                               color: key == menuselectedIndex[selectedIndex] ? '#FFF' : '#333'}"
                >{{item.value}}</text>
            </div>
        </div>
        <div class="cmui-tab">
            <div v-for="(item, key) in tabList"
                 :key="key"
                 :class="[hasBorder ? 'cmui-tab-item' : 'cmui-tab-items']"
                 :style="[key == selectedIndex ? selectStyle : unselectStyle]"
                 @click="onclickitem(key)">
                <div class="cmui-tab-container">
                    <text class="cmui-tab-text" :style="{color: key == selectedIndex ? selectedColor : '#666'}">{{item.tab}}</text>
                    <image :ref="key + 'tree'" class="cmui-tab-icon" :src="key == selectedIndex ? selectedIcon : iconSrc"></image>
                </div>
            </div>
            <div v-if="hasFt" class="cmui-tab-ft" @click="ftclick">
                <text class="cmui-tab-fttext" :style="{color: hasCondition ? selectedColor : '#666'}">筛选</text>
            </div>
        </div>
    </div>
</template>

<script>
    var animation = weex.requireModule('animation');

    module.exports = {
        name: 'CmuiMenu',

        componentName: 'CmuiMenu',
        data: function () {
            return {
                selectedIndex: 0,
                lastSelected: -1,
                needFade: false,
                menuselectedIndex: [],
                showOptions: false,
                optionsList: [],
                tabList: [],
                desc: '',
                textLimit: 0,
                didClear: false
            }
        },
        props: {
            menuList: Array,
            totalSize: String,
            searchText: String,
            hasCondition: {
                type: Boolean,
                default: false
            },
            hasotherCondition: {
                type: Boolean,
                default: false
            },
            otherChanged: {
                type: Boolean,
                default: false
            },
            canClear: {
                type: Boolean,
                default: false
            },
            clearAllTab: {
                type: Boolean,
                default: false
            },
            hasBorder: {
                type: Boolean,
                default: true
            },
            hasFt: {
                type: Boolean,
                default: false
            },
            needCloseMenu: {
                type: Boolean,
                default: false
            },
            iconSrc: {
                type: String,
                default: 'https://gw.alicdn.com/tfs/TB1f6BzhjihSKJjy0FiXXcuiFXa-32-32.png'
            },
            selectedColor: {
                type: String,
                default: '#FF6A00'
            },
            selectedIcon: {
                type: String,
                default: 'https://gw.alicdn.com/tfs/TB1.GDNlgoQMeJjy0FoXXcShVXa-32-32.png'
            }
        },
        computed: {
            selectStyle() {
                let style = {};

                style.borderBottomColor = this.selectedColor;
                style.borderBottomWidth = 3;
                return style;
            },
            unselectStyle() {
                let style = {};

                style.borderBottomColor = '#DCDED3';
                style.borderBottomWidth = 2;
                return style;
            }
        },
        watch: {
            needCloseMenu() {
                if(this.needCloseMenu) {
                   this.fadeOut();
                   if(this.needFade) {
                       this.rotate(this.selectedIndex);
                       this.needFade = false;
                   }
                }
            }
        },
        methods: {
            onclickitem(index) {
                this.lastSelected = this.selectedIndex
                this.selectedIndex = index;
                this.$emit('tabItemOnClick', {index: index, value: this.menuList[index].tab});

                if(this.lastSelected == this.selectedIndex) {
                    if(!this.needFade) {
                        this.optionsList = this.menuList[index].options;
                        this.fadeIn();
                        this.rotate(index);
                        this.needFade = true;
                    } else {
                        this.fadeOut();
                        this.rotate(index);
                        this.needFade = false;
                    }
                } else {
                    if(this.needFade) {
                        this.fadeOut();
                        this.rotate(this.lastSelected);
                        this.needFade = false;
                    }
                }
            },
            onclickmenu(index){
                this.rotate(this.selectedIndex);
                this.menuselectedIndex[this.selectedIndex] = index;
                if(this.optionsList[index].value.length > this.textLimit) {
                    this.tabList[this.selectedIndex].tab = this.getSubStr(this.optionsList[index].value);
                } else {
                    this.tabList[this.selectedIndex].tab = this.optionsList[index].value;
                }
                this.needFade = false;
                this.fadeOut();
                this.$emit('menuOnClick', {index: this.optionsList[index].key, value:this.optionsList[index].value});
            },
            hideOptions: function () {
                this.rotate(this.selectedIndex);
                this.fadeOut();
                this.needFade = false;
            },
            anim: function(index, styles, timingFunction, duration, callback) {
                animation.transition(this.$refs[index+'tree'][0], {
                    styles: styles,
                    timingFunction: timingFunction,
                    duration: duration
                }, callback);
            },
            rotate: function(index, text) {
                var self = this;
                if(!self.current_rotate) {
                    self.current_rotate = 0;
                }
                if(text) {
                    self.current_rotate += 0;
                } else {
                    self.current_rotate += 180;
                }

                self.anim(index,{
                    transform: 'rotate(' + self.current_rotate + 'deg)'
                }, 'linear', 100);
            },
            fadeIn: function () {
                this.showOptions = true;
                var options = this.$refs.options;
                animation.transition(options, {
                    styles: {
                        transform: 'translate(0, 480px)'
                    },
                    duration: 200,
                    timingFunction: 'ease',
                    needLayout:false,
                    delay: 0
                });
            },
            fadeOut: function () {
                this.showOptions = false;
                var options = this.$refs.options;
                animation.transition(options, {
                    styles: {
                        transform: 'translate(0, -480px)'
                    },
                    duration: 200,
                    timingFunction: 'ease',
                    needLayout:false,
                    delay: 0
                });
            },
            getSubStr: function (str) {
                var subStr1 = str.substr(0,4);
                var subStr2 = str.substr(str.length-3,3);
                var subStr = subStr1 + "..." + subStr2 ;
                return subStr;
            },
            ftclick: function (event) {
                this.$emit('ftclick', event);
            },
            clearConditons: function () {
                var index = this.selectedIndex;
                if(this.clearAllTab) {
                    for(var key in this.tabList) {
                        this.tabList[key] = {tab: this.menuList[key].tab, selectedMenu: -1};
                        this.menuselectedIndex[index] = 0;
                    }
                } else {
                    this.tabList[index] = {tab: this.menuList[index].tab, selectedMenu: -1};
                    this.menuselectedIndex[index] = 0;
                }
                this.lastSelected = this.selectedIndex;
                this.$emit('clearConditon', index);
                this.hasCondition = false;
            }
        },
        created () {
            for (var index in this.menuList) {
                this.tabList.push({tab: this.menuList[index].tab, selectedMenu: -1});
                this.menuselectedIndex[index] = 0;
            }
            this.textLimit = parseInt(600 / (40 * this.menuList.length));
        }
    }
</script>

<style lang="sass" scoped>
    @import './menu.scss';
</style>
