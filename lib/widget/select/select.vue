<template>
    <div :style="{flexDirection: isRow ? 'row' : 'column'}" style="flex-wrap: wrap">
        <div class="cmui-select" v-for="(item, key) in radioList" @click="select(key)">
            <div class="cmui-select-icon"
                 :class="[isRadio ? 'cmui-radio' : '']"
                 :style="[item.checked && borderStyle ? borderSelectStyle : '']"
            >
                <cmui-icon class="cmui-icon-select" name="check" v-if="item.checked && iconStyle"
                           :style="{color: selectColor}"></cmui-icon>
            </div>
            <text class="cmui-select-label">{{item.label}}</text>
        </div>
    </div>
</template>

<script>
    var modal = weex.requireModule('modal');
    module.exports =  {
        name: 'CmuiRadio',

        componentName: 'CmuiRadio',

        components: {
            CmuiIcon: require('../icon/icon.vue')
        },

        props: {
            selectStyle: {
                type: String,
                default: 'iconStyle'
            },
            selectColor: {
                type: String,
                default: '#0184d7'
            },
            selectOne: {
                type: Boolean,
                default: true
            },
            maxLimit: Number,
            isRow: {
                type: Boolean,
                default: true
            },
            isRadio: {
                type: Boolean,
                default: true
            },
            radioList: Array
        },
        computed: {
            iconStyle() {
                return this.selectStyle == 'iconStyle';
            },
            borderStyle() {
                return this.selectStyle == 'borderStyle';
            },
            borderSelectStyle() {
                let style = {};

                style.borderStyle = 'solid';
                style.borderWidth = 10;
                style.borderRadius = 30;
                style.borderColor = this.selectColor;

                return style;
            }
        },
        methods: {
            select (index) {
                if(this.selectOne) {
                    for(var i = 0; i < this.radioList.length; i++) {
                        var item = this.radioList[i];
                        if(i == index){
                            item.checked = true;
                        }
                        else {
                            item.checked = false;
                        }
                    }
                } else {
                    var j = 0;
                    for(var i = 0; i < this.radioList.length; i++) {
                        var item = this.radioList[i].checked;
                        if(item) {
                            ++j;
                        }
                    }
                    if(j < this.maxLimit || this.radioList[index].checked) {
                        this.radioList[index].checked = !this.radioList[index].checked;
                    } else {
                        modal.toast({
                            message: '最多可选' + this.maxLimit + '个选项'
                        });
                    }
                }
                this.$emit('select', {
                    index: this.radioList[index].index,
                    value: this.radioList[index].value
                });
            }
        }
    }
</script>

<style lang="sass" scoped>
    @import 'select.scss';
</style>
