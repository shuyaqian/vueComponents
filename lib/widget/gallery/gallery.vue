<template>
    <div class="cmui-gallery">
        <div class="cmui-gallery-bd">
            <image class="cmui-gallery-img" :src="galleryImgSrc"></image>
        </div>
        <div class="cmui-gallery-ft" @click="delGallery">
            <cmui-icon class="cmui-icon-gallery" name="delete"></cmui-icon>
        </div>
    </div>
</template>

<script>
    module.exports = {
        name: 'CmuiGallery',

        componentName: 'CmuiGallery',

        components: {
            CmuiIcon: require('../icon/icon.vue')
        },

        props: {
            index: String,
            galleryImgSrc: String
        },

        methods: {
            delGallery (e) {
                this.$emit('upload.del', {
                    index: this.index,
                    url: this.galleryImgSrc
                });
            }
        }
    }
</script>

<style lang="sass" scoped>
    @import './gallery.scss';
</style>
