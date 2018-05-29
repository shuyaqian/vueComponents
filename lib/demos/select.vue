<template>
    <scroller class="page">
        <div class="component-title">
            <image :src="logoimg" class="logo-img"></image>
            <text class="title">GTS-Select</text>
        </div>
        <text class="desc">选单框</text>
        <div class="demo-block">
            <cmui-select
                :selectStyle="iconStyle"
                :selectOne=true
                :isRow=true
                :isRadio=true
                :radioList="radioList"
                @select="select"
                ></cmui-select>
        </div>
        <div class="demo-block">
            <cmui-select
                :selectStyle="borderStyle"
                :selectOne=true
                :isRow=true
                :isRadio=true
                :radioList="radioList5"
                @select="select"
            ></cmui-select>
        </div>
        <div class="demo-block">
            <cmui-select-cell
                :itemList="itemList"
                :selectColor="selectColor"
                :cellHeight="cellHeight"
            ></cmui-select-cell>
        </div>
        <div class="demo-block">
            <cmui-select
                :selectStyle="iconStyle"
                :selectColor="selectColor"
                :selectOne=true
                :isRow=false
                :isRadio=false
                :radioList="radioList2"
                @select="select"
            ></cmui-select>
        </div>
        <text class="desc">多选框</text>
        <div class="demo-block">
            <cmui-select
                :selectStyle="iconStyle"
                :selectOne=false
                :maxLimit='maxLimit'
                :isRow=true
                :isRadio=true
                :radioList="radioList3"
                @select="select"
            ></cmui-select>
        </div>
        <div class="demo-block">
            <cmui-select
                :selectStyle="iconStyle"
                :selectOne=false
                :maxLimit='maxLimit'
                :isRow=false
                :isRadio=false
                :radioList="radioList4"
                @select="select"
            ></cmui-select>
        </div>
    </scroller>
</template>

<script>
    module.exports =  {
        components: {
            cmuiSelect: require('../widget/select/select.vue'),
            CmuiSelectCell: require('../widget/select/select-cell.vue')
        },
        data () {
            return {
                logoimg:'https://gw.alicdn.com/tfs/TB1PaIWSFXXXXasXpXXXXXXXXXX-109-77.png',
                iconStyle: 'iconStyle',
                borderStyle: 'borderStyle',
                buttonStyle: 'buttonStyle',
                selectColor: '#0184d7',
                maxLimit: 3,
                cellHeight: 90,
                itemList: [{
                    index: 'sex',
                    label: '选项一',
                    value: '0',
                    checked: true
                }, {
                    index: 'sex',
                    label: '选项二',
                    value: '1',
                    checked: false
                }, {
                    index: 'sex',
                    label: '选项三',
                    value: '2',
                    checked: false
                }],
                radioList: [{
                    index: 'sex',
                    label: '备选项',
                    value: '0',
                    checked: true
                }, {
                    index: 'sex',
                    label: '备选项',
                    value: '1',
                    checked: false
                }, {
                    index: 'sex',
                    label: '备选项',
                    value: '2',
                    checked: false
                }],
                radioList5: [{
                    index: 'sex',
                    label: '备选项',
                    value: '0',
                    checked: true
                }, {
                    index: 'sex',
                    label: '备选项',
                    value: '1',
                    checked: false
                }, {
                    index: 'sex',
                    label: '备选项',
                    value: '2',
                    checked: false
                }],
                radioList2: [{
                    index: 'sex',
                    label: '备选项',
                    value: '0',
                    checked: true
                }, {
                    index: 'sex',
                    label: '备选项',
                    value: '1',
                    checked: false
                }, {
                    index: 'sex',
                    label: '备选项',
                    value: '2',
                    checked: false
                }],
                radioList3: [{
                    index: 'sex',
                    label: '备选项',
                    value: '0',
                    checked: false
                }, {
                    index: 'sex',
                    label: '备选项',
                    value: '1',
                    checked: false
                }, {
                    index: 'sex',
                    label: '备选项',
                    value: '2',
                    checked: false
                }, {
                    index: 'sex',
                    label: '备选项',
                    value: '2',
                    checked: false
                }, {
                    index: 'sex',
                    label: '备选项',
                    value: '2',
                    checked: false
                }],
                radioList4: [{
                    index: 'sex',
                    label: '备选项',
                    value: '0',
                    checked: false
                }, {
                    index: 'sex',
                    label: '备选项',
                    value: '1',
                    checked: false
                }, {
                    index: 'sex',
                    label: '备选项',
                    value: '2',
                    checked: false
                }, {
                    index: 'sex',
                    label: '备选项',
                    value: '2',
                    checked: false
                }, {
                    index: 'sex',
                    label: '备选项',
                    value: '2',
                    checked: false
                }]
            }
        }
    }
</script>

<style lang="sass" scoped>

    @import './common.scss';
</style>
