<template>
    <scroller class="page">
        <text class="title">Form 表单</text>
        <text class="desc">由输入框、选择器、单选框、多选框等控件组成，用以收集、校验、提交数据。</text>
        <text class="sub-title">文本框</text>
        <text class="desc">文本输入。</text>
        <cmui-cells title="文本输入">
            <cmui-form-item label="用户名">
                <cmui-input v-model="form.uname" placeholder="请输入用户名"></cmui-input>
            </cmui-form-item>
            <cmui-form-item label="性别">
                <cmui-select
                    :selectStyle="iconStyle"
                    :selectOne=true
                    :isRow=true
                    :isRadio=true
                    :radioList="radio"
                    @select="select"></cmui-select>
            </cmui-form-item>
            <cmui-form-item label="爱好">
                <cmui-select
                    :selectStyle="iconStyle"
                    :selectOne=false
                    :maxLimit='maxLimit'
                    :isRow=true
                    :isRadio=false
                    :radioList="checkbox"
                    @select="select"></cmui-select>
            </cmui-form-item>
            <cmui-form-item label="个人博客">
                <cmui-input type="url" v-model="form.blog" placeholder="请输入个人博客地址"></cmui-input>
            </cmui-form-item>
            <cmui-form-item label="联系方式">
                <cmui-input type="tel" v-model="form.tel" placeholder="请输入联系方式"></cmui-input>
            </cmui-form-item>
            <cmui-form-item label="特殊技能">
                <cmui-switch @change="changeSwitch"></cmui-switch>
            </cmui-form-item>
            <cmui-form-item label="日期">
                <cmui-picker type="date" placeholder="请选择日期"></cmui-picker>
            </cmui-form-item>
            <cmui-form-item label="时间">
                <cmui-picker type="time" placeholder="请选择时间"></cmui-picker>
            </cmui-form-item>
            <cmui-form-item label="自我介绍" :inline="false" last="true">
                <cmui-textarea v-model="form.desc" rows="4" :maxlength="10" placeholder="自我介绍" :fontsize="fontsize"></cmui-textarea>
            </cmui-form-item>
        </cmui-cells>
    </scroller>
</template>

<script>
    var checkboxList = [{
        index: 'fav',
        label: '羽毛球',
        value: '1',
        checked: false
    }, {
        index: 'fav',
        label: '篮球',
        value: '2',
        checked: false
    }, {
        index: 'fav',
        label: '足球',
        value: '3',
        checked: false
    }];

    module.exports =  {
        components: {
            CmuiCells: require('../widget/cells/cells-item.vue'),
            CmuiFormItem: require('../widget/form/form-item.vue'),
            CmuiInput: require('../widget/input/input.vue'),
            CmuiSelect: require('../widget/select/select.vue'),
            CmuiTextarea: require('../widget/textarea/form-textarea-count.vue'),
            CmuiSwitch: require('../widget/switch/form-switch.vue'),
            CmuiPicker: require('../widget/picker/picker.vue')
        },
        data () {
            return {
                maxLimit: 3,
                form: {
                    uname: '',
                    sex: '',
                    fav: [],
                    desc: ''
                },
                radio: [{
                    index: 'sex',
                    label: '男',
                    value: '1',
                    checked: true
                }, {
                    index: 'sex',
                    label: '女',
                    value: '0',
                    checked: false
                }],
                checkbox: checkboxList,
                fontsize: 50
            }
        },
        methods: {
            resetRadios (val) {
                var self = this,
                    temp = this.radio;

                for (var i = 0, len = temp.length; i < len; i++) {
                    var item = temp[i];

                    if (val === item.value) {
                        temp[i].checked = true;
                    } else {
                        temp[i].checked = false;
                    }
                    console.log('ooooooooooo---' + JSON.stringify(temp[i]));
                }

                self.radio = temp;
            },
            select (event) {
                if (event.index === 'sex') {
                    this.form[event.index] = event.value;

                    // this.resetRadios(event.value);
                }

                if (event.index === 'fav') {
                    this.form[event.index].push(event.value);
                }

                console.log(this.form);
            },
            changeSwitch (event) {
                console.log(event);
            }
        }
    }
</script>

<style lang="sass" scoped>

    @import './common.scss';
</style>
