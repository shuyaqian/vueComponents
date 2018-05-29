<template>
    <div>

            <text style="font-size: 40" value="Rotate" @click="rotate" type="primary" size="middle"></text>


        <div ref="block(1)" class="block">
            <text class="block-txt">Anim</text>
        </div>
        <image ref="block(2)" class="img" src="https://gw.alicdn.com/tfs/TB1gY9yRFXXXXXJXVXXXXXXXXXX-700-306.jpg"></image>
    </div>
</template>

<script>
    var modal = weex.requireModule('modal');
    var animation = weex.requireModule('animation')
    module.exports = {
        data: function () {
            return {
                transformOrigin: 'center center',
                current_rotate: 0
            }
        },
        components: {
        },
        methods: {

            anim: function(styles, timingFunction, duration) {
                for(var i=1; i<3; i++){
                    modal.alert({message: this.$refs[`block(${i})`]});
                    var ssss= this.$refs[`block(${i})`];

                    animation.transition(ssss, {
                        styles: styles,
                        timingFunction: timingFunction,
                        duration: duration
                    });
                }
            },
            rotate: function() {
                var self = this;
                if(!self.current_rotate) {
                    self.current_rotate = 0;
                }
                self.current_rotate += 180;
                self.anim({
                    transform: 'rotate(' + self.current_rotate + 'deg)'
                }, 'linear', 100);
            }
        }
    };
</script>

<style scoped>
    .block {
        position: absolute;
        width: 250px;
        height: 250px;
        top: 300px;
        left: 400px;
        background-color: #F0AD4E;
        align-items: center;
        justify-content: center;
    }

    .img {
        position: absolute;
        width: 250px;
        height: 250px;
        top: 600px;
        left: 400px;
        background-color: #F0AD4E;
        align-items: center;
        justify-content: center;
    }

    .block-txt {
        color: #FFFFFF;
        font-size: 70px;
    }
</style>
