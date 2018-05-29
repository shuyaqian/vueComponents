<template>
    <text
        class="cmui-icon"
        :class="[
            name ? 'cmui-icon-' + name : ''
        ]"
        :style="{fontFamily:'cmui'}">{{getFontName}}</text>
</template>

<script>
    let icons = require('./icon.data.js');

    module.exports =  {
        name: 'CmuiIcon',

        props: {
            name: String
        },

        computed: {
            getFontName() {
                return this.decodeIconFont(icons[this.name])
            }
        },

        methods: {
            decodeIconFont: function(str) {
                if (str.length === 0) {
                    return '';
                }
                return str.replace(/&(#?[\w\d]+);?/g, function (s, entity) {
                    var char, code;
                    if (entity.charAt(0) === "#") {
                        if (entity.charAt(1) === 'x') {
                            code = parseInt(entity.substr(2).toLowerCase(), 16);
                        } else {
                            code = parseInt(entity.substr(1));
                        }
                        if (isNaN(code) || code < -32768 || code > 65535) {
                            char = '';
                        } else {
                            char = String.fromCharCode(code);
                        }
                    }
                    if (char === void 0) {
                        return s;
                    } else {
                        return char;
                    }
                });
            }
        },

        mounted () {
            var domModule = weex.requireModule("dom");

            domModule.addRule('fontFace', {
                'fontFamily': 'cmui',
                'src': "url(\'http://at.alicdn.com/t/font_dc97ha5pts2a9k9.ttf\')"
            });
        }
    }
</script>

<style lang="sass" scoped>
    @import './icon.scss';
</style>
