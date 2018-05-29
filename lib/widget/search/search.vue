<template>
    <div class="cmui-search">
        <div class="cmui-search-form">
            <div class="cmui-search-box">
                <cmui-icon class="cmui-icon-search" name="search"></cmui-icon>
                <input return-key-type="search" class="cmui-search-input" placeholder="搜索" @focus="focus" v-model="message">
                </input>
            </div>
        </div>
        <text class="cmui-search-cancel" v-if="show" @click="close">取消</text>
    </div>
</template>

<script>
    var modal = weex.requireModule('modal');
    module.exports =  {
        name: 'CmuiSearch',

        componentName: 'CmuiSearch',

        components: {
            CmuiIcon: require('../icon/icon.vue')
        },
        data() {
            return {
                show: false,
                message: ''
            }
        },
        methods: {
            focus() {
                this.show = true;
            },
            close() {
                this.show = false;
                this.message = '';
            }
        }
    }
</script>

<style lang="sass" scoped>
    @import './search.scss';
</style>
