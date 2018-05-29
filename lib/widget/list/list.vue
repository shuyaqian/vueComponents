<template>
    <div class="cmui-list">
        <div class="cmui-list-item"
            :class="[hasImg ? 'cmui-list-hasimg' : '',
                hasIndex ? 'cmui-list-hasseq' : '',
                hasNode ? 'cmui-list-hasnode' : '']">
            <image class="cmui-list-img" v-if="imgSrc" :src="imgSrc"></image>
            <text class="cmui-list-seq" v-if="hasIndex">{{index}}.</text>
            <text class="cmui-list-node" v-if="hasNode"></text>
            <div style="flex: 1">
                <text class="cmui-list-title" v-if="itemTitle">{{itemTitle}}</text>
                <text class="cmui-list-content" v-if="itemContent">{{itemContent}}</text>
                <div :class="[
                     inline ? 'cmui-list-inline' : '']">
                    <text class="cmui-list-name" v-if="itemName" :style="namestyle">{{itemName}}</text>
                    <text class="cmui-list-time" v-if="itemTime" :style="timestyle">{{itemTime}}</text>
                    <text class="cmui-list-status" v-if="itemStatus" :style="statusstyle">{{itemStatus}}</text>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

    module.exports = {
        name: 'CmuiList',

        componentName: 'CmuiList',

        props: {
            hasIndex: Boolean,
            index: Number,
            hasNode: Boolean,
            inline: Boolean,
            imgSrc: String,
            itemTitle: String,
            itemContent: String,
            itemName: String,
            itemTime: String,
            itemStatus: String,
            nameColor: String,
            nameSize: Number,
            timeColor: String,
            timeSize: Number,
            statusColor: String,
            statusSize: Number
        },
        computed: {
            hasImg: function() {
                return this.imgSrc ? true : false;
            },
            namestyle: function() {
                let ret = {};

                if (this.nameColor) {
                    ret.color = this.nameColor;
                }
                if (this.nameSize) {
                    ret.fontSize = this.nameSize;
                }

                return ret;
            },
            timestyle: function() {
                let ret = {};

                if (this.timeColor) {
                    ret.color = this.timeColor;
                }
                if (this.timeSize) {
                    ret.fontSize = this.timeSize;
                }

                return ret;
            },
            statusstyle: function() {
                let ret = {};

                if (this.statusColor) {
                    ret.color = this.statusColor;
                }
                if (this.statusSize) {
                    ret.fontSize = this.statusColor;
                }

                return ret;
            }
        }
    }
</script>

<style lang="sass" scoped>
    @import "./list.scss";
</style>
