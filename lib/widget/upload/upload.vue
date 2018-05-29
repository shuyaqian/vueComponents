<template>
    <div class="cmui-upload">
        <div class="cmui-upload-hd">
            <text class="cmui-upload-title">{{title}}</text>
            <div v-if="limit" class="cmui-upload-info">
                <text class="cmui-upload-num">{{uploadNum}}</text>
                <text class="cmui-upload-text">/</text>
                <text class="cmui-upload-text">{{uploadLimit}}</text>
            </div>
        </div>
        <text v-if="desc" class="cmui-upload-desc">{{desc}}</text>
        <div class="cmui-upload-bd">
            <image 
                class="cmui-upload-item" 
                v-for="(item, key) in uploadList" 
                :key="key"
                :index="key" 
                :src="item" 
                @click="show"></image>
            <div class="cmui-upload-plus" v-if="enabled" @click="upload">
                <cmui-icon class="cmui-icon-plus" name="plus"></cmui-icon>
            </div>
        </div>
    </div>
</template>

<script>
    module.exports = {
        name: 'CmuiUpload',

        componentName: 'CmuiUpload',

        components: {
            CmuiIcon: require('../icon/icon.vue')
        },

        props: {
            index: String,
            title: {
                type: String,
                default: '上传照片'
            },
            limit: Boolean,
            uploadLimit: {
                type: Number,
                default: 9
            },
            desc: String,
            uploadList: {
                type: Array,
                default () {
                    return [];
                }
            },
            enabled: {
                type: Boolean,
                default: true
            }
        },

        data () {
            return {
                uploadNum: 0
            }
        },

        methods: {
            upload (e) {
                this.$emit('upload.plus', {
                    index: this.index,
                    uploadList: this.uploadList
                });
            },
            show (e) {
                this.$emit('upload.show', {
                    index: this.index,
                    url: e.target.attr.src
                });
            }
        },
        
        created () {
            if (this.limit && this.uploadList) {
                this.uploadNum = this.uploadList.length;
            }

            if (this.uploadNum >= this.uploadLimit) {
                this.enabled = false;
            }
        }
    }
</script>

<style lang="sass" scoped>
    @import './upload.scss';
</style>
