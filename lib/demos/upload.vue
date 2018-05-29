<template>
    <scroller class="page">
        <text class="title">Upload 上传图片</text>
        <text class="desc">上传本地图片。</text>
        <div class="demo-block">
            <cmui-upload
                v-for="(item, index) in uploads"
                :key="index"
                :index="item.index"
                :title="item.title"
                :limit="item.limit"
                :uploadLimit="item.uploadLimit"
                :desc="item.desc"
                :uploadList="item.uploadList"></cmui-upload>
        </div>
    </scroller>
</template>

<script>
    let uploadData = [{
        index: 'photo-business-license',
        title: '营业执照',
        limit: true,
        uploadLimit: 2,
        desc: '营业执照需要上传清晰的正反面照片',
        uploadList: ["http://photo.taobao.net/uploads/thumbnail/f4bd99c8f7e1b4f4e506f68216311e1f/2.jpg",
        "http://photo.taobao.net/uploads/thumbnail/e846e6db6deeda06469fa4c445a2becf/2.jpg"]
    }, {
        index: 'photo-office-environment',
        title: '办公环境照片',
        limit: false,
        desc: '请尽量上传角度良好、画面清晰的办公场所照片，确保真实性，不限数量'
    }, {
        index: 'photo-company-scene',
        title: '公司外景',
        limit: false
    }];

    module.exports =  {
        components: {
            CmuiUpload: require('../widget/upload/upload.vue')
        },

        data () {
            return {
                uploads: uploadData
            }
        }
    }
</script>

<style lang="sass" scoped>

    @import './common.scss';
</style>
