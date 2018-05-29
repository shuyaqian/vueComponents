<template>
    <scroller class="page" style="padding-right: 24">
        <text class="title">Slider轮播组件</text>
        <text class="desc">自动播放</text>
        <cmui-slider
            :imageList="sliders[0].imageList"
            :interval="sliders[0].interval"
            :autoPlay="sliders[0].autoPlay"
            :indicatorColor="sliders[0].indicatorColor"
            :indicatorLeft="sliders[0].indicatorLeft"></cmui-slider>
        <text class="desc">手动播放</text>
        <cmui-slider
            :imageList="sliders[1].imageList"
            :interval="sliders[1].interval"
            :autoPlay="sliders[1].autoPlay"
            :indicatorColor="sliders[0].indicatorColor"
            :indicatorLeft="sliders[0].indicatorLeft"></cmui-slider>
        <text class="desc">修改导航颜色位置</text>
        <cmui-slider
            :imageList="sliders[0].imageList"
            :interval="sliders[0].interval"
            :autoPlay="sliders[0].autoPlay"
            :indicatorColor="sliders[1].indicatorColor"
            :indicatorLeft="sliders[1].indicatorLeft"></cmui-slider>

    </scroller>
</template>

<script>
    module.exports =  {
        components: {
            CmuiSlider: require('../widget/slider/slider.vue')
        },
        data () {
            return {
                sliders: [{
                    indicatorColor: 'rgb(40, 96, 144)',
                    indicatorLeft: 240,
                    interval: 2000,
                    autoPlay: true,
                    imageList: [
                        { src: 'https://gw.alicdn.com/tfs/TB1gY9yRFXXXXXJXVXXXXXXXXXX-700-306.jpg'},
                        { src: 'https://gw.alicdn.com/tfs/TB1jeiqRFXXXXcLXVXXXXXXXXXX-700-306.jpg'},
                        { src: 'https://gw.alicdn.com/tfs/TB1O3t.RFXXXXXCaFXXXXXXXXXX-700-306.jpg'}
                    ]
                },{
                    indicatorColor: 'red',
                    indicatorLeft: 100,
                    interval: 2000,
                    autoPlay: false,
                    imageList: [
                        { src: 'https://gw.alicdn.com/tfs/TB1gY9yRFXXXXXJXVXXXXXXXXXX-700-306.jpg'},
                        { src: 'https://gw.alicdn.com/tfs/TB1jeiqRFXXXXcLXVXXXXXXXXXX-700-306.jpg'},
                        { src: 'https://gw.alicdn.com/tfs/TB1O3t.RFXXXXXCaFXXXXXXXXXX-700-306.jpg'}
                    ]
                }]
            }
        },
        methods: {

        }
    }
</script>

<style lang="sass" scoped>

    @import './common.scss';
</style>
