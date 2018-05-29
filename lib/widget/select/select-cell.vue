<template>
    <scroller>
        <div v-for="(item, key) in itemList"
             class="cmui-cell"
             @click="handleClick(key)"
             :style="{height: cellHeight}">
            <text class="cmui-cell-bd">{{item.label}}</text>
            <cmui-icon
                class="cmui-icon-access"
                name="check"
                v-if="item.checked"
                :style="{color: selectColor}"></cmui-icon>
        </div>
    </scroller>
</template>

<script>

    module.exports = {
        name: 'CmuiSelectCell',

        componentName: 'CmuiSelectCell',

        components: {
            CmuiIcon: require('../icon/icon.vue')
        },
        data() {
            return {
                itemList: this.itemList
            }
        },

        props: {
            itemList: [],
            selectColor: {
                type: String,
                default: '#FF6A00'
            },
            cellHeight: {
                type: Number,
                default: '100'
            }
        },

        methods: {
            handleClick (index) {
                for(var i = 0; i < this.itemList.length; i++) {
                    var item = this.itemList[i];
                    if(i == index){
                        item.checked = true;
                    }
                    else {
                        item.checked = false;
                    }
                }
                this.$emit('select', {
                    index: this.itemList[index].index,
                    label: this.itemList[index].label,
                    value: this.itemList[index].value,
                    id: this.itemList[index].id,
                    pro: this.itemList[index].pro
                });
            }
        }
    }
</script>

<style lang="sass" scoped>
    @import './select-cell.scss';
</style>
