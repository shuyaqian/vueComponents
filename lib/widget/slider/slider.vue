<template>
    <div>
        <slider :interval="interval" :autoPlay="autoPlay" class="cmui-slider">
            <indicator class="indicator" :style="indicatorStyle"></indicator>
            <div v-for="img in imageList">
                <image class="image" resize="cover" :src="img.src"></image>
            </div>
        </slider>
    </div>
</template>

<style scoped>
    .cmui-slider {
        height: 320;
    }
    .image {
        height: 320;
    }
    .indicator {
        position: absolute;
        width: 800;
        height: 350;
        top: 100;
        itemColor: #dddddd;
    }
</style>

<script>
    module.exports =  {
        data () {
            return {
            }
        },
        props: {
            imageList: Array,
            interval: Number,
            autoPlay: {
                type: Boolean,
                default: true
            },
            indicatorColor: String,
            indicatorLeft: Number
        },
        computed: {
            indicatorStyle() {
                let style = {};

                style.itemSelectedColor = this.indicatorColor;
                style.left = this.indicatorLeft;

                return style;
            }
        }
    }
</script>
