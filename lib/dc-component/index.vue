<template>
    <scroller >
        <dc-media-set :mediaItemKeys="mediaItemKeys"></dc-media-set>
        <dc-select title="SElECT标签" :options="options" v-on:dcSelect="dcSelect" placeholder="请选择"></dc-select>
        <dc-select showWarning="true" warning="请选择企业" title="SElECT标签" :options="options" v-on:dcSelect="dcSelect"
                   placeholder="请选择"></dc-select>
        <dc-input title="INPUT标签" placeholder="请选择日期" subType="DATE" v-on:dcInput="deInput"></dc-input>
        <dc-input title="INPUT标签" placeholder="请选择时间" subType="TIME" v-on:dcInput="deInput"></dc-input>
        <dc-input title="INPUT标签" placeholder="请输入整数" subType="INT" v-on:dcInput="deInput"></dc-input>
        <dc-input title="INPUT标签" placeholder="请输入电话" subType="PHONE" v-on:dcInput="deInput"></dc-input>
        <dc-input maxSize="10" value="sds" title="INPUT标签" placeholder="请选择" subType="TEXT"
                  v-on:dcInput="deInput"></dc-input>
        <dc-input maxSize="10" value="测试sdasdadsfasdfasd发" title="INPUT标签" subType="TEXT"
                  v-on:dcInput="deInput"></dc-input>
        <dc-input showWarning="true" warning="请输入正确信息" value="测试sdasdadsfasdfasd发" readOnly="true"
                  title="INPUT标签" subType="TEXT" v-on:dcInput="deInput"></dc-input>
        <dc-textarea swarning="请输入正确信息" value="测试sdasdadsfasdfasd发" readOnly="true"
                     title="INPUT标签" subType="TEXT" v-on:dcInput="deInput" placeholder="请选择"
                     maxSize="100"></dc-textarea>
        <dc-textarea showWarning="true" warning="请输入正确信息" value="测试sdasdadsfasdfasd发" readOnly="true"
                     title="INPUT标签" subType="TEXT" v-on:dcInput="deInput" placeholder="请选择"
                     maxSize="10" textAreaStyle="small"></dc-textarea>
        <dc-label title="这是一个测试这是一个测试这是一个测试这是一个测试这是一个测试这是一个测试这是一个测试这是一个测试"></dc-label>
        <dc-label subType="group" title="这是一个测试"></dc-label>
        <dc-label subType="small" title="这是一个测试这是一个" style="margin-bottom: 200"></dc-label>

    </scroller>
</template>
<script>
    export default {
        components: {
            dcSelect: require('./widget/dc-select/dc-select.vue'),
            dcInput: require('./widget/dc-input/dc-input.vue'),
            dcTextarea: require('./widget/dc-textarea/dc-textarea.vue'),
            dcLabel: require('./widget/dc-label/dc-label.vue'),
            dcMediaSet: require('./widget/dc-media/dc-media-set.vue')
        },

        data () {
            return {
                options: [
                    {
                        "key": "lb",
                        "value": "老板"
                    },
                    {
                        "key": "gcfzr",
                        "value": "工厂负责人"
                    },
                    {
                        "key": "cw",
                        "value": "财务"
                    },
                    {
                        "key": "xs",
                        "value": "销售"
                    }
                ],
                mediaItemKeys:[
                    {
                        "demoUrl": "https://vuejs.org/images/logo.png",
                        "key": "factory.selfNameplate",
                        "required": true,
                        "subType": "PIC",
                        "title": "铭牌照片1",
                        "type": "MEDIAITEM"
                    },
                    {
                        "demoUrl": "https://vuejs.org/images/logo.png",
                        "key": "factory.selfNameplate",
                        "required": false,
                        "subType": "PIC",
                        "title": "铭牌照片1",
                        "type": "MEDIAITEM"
                    },
                    {
                        "demoUrl": "https://vuejs.org/images/logo.png",
                        "key": "factory.selfNameplate",
                        "required": true,
                        "subType": "PIC",
                        "title": "铭牌照片1",
                        "type": "MEDIAITEM"
                    },
                    {
                        "demoUrl": "https://vuejs.org/images/logo.png",
                        "key": "factory.selfNameplate",
                        "required": true,
                        "subType": "PIC",
                        "title": "铭牌照片1",
                        "type": "MEDIAITEM"
                    }
                ]
            }
        },
        methods: {
            dcSelect: function (result) {
//                var modal = weex.requireModule('modal')
//                modal.alert({message:JSON.stringify(result), duration:0.3})
            },
            deInput: function (result) {
//                var modal = weex.requireModule('modal')
//                modal.alert({message:JSON.stringify(result), duration:0.3})
            }
        },
        created () {

        }
    }
</script>

<style scoped>

</style>
