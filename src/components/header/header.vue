<template>
    <header class="header">
        <div class="container clearfix">
            <figure class="fl">
                <a href="">
                    <img src="../../../static/images/logo.jpg" alt="">
                </a>
            </figure>
            <nav class="fl">
                <ul class="clearfix nav">
                    <li v-for="(item, index) in cnav" :key="index">
                        <a href="" :class="{'active': index == cnav.length - 1}">
                            {{ item.name }}
                            <img :src="item.icon" alt="" v-if="item.icon">
                        </a>
                        <i v-if="item.sub" class="triangle"></i>
                        <ul v-if="item.sub" class="navsub clearfix">
                            <li v-for="(val, idx) in item.sub" :key="idx">
                                <a href="">{{ val }}</a>
                            </li>
                        </ul>
                    </li>
                </ul>
            </nav>
            <nav class="fr">
                <ul class="clearfix nav">
                    <li v-for="(item, index) in rnav" :key="index">
                        <a href="">
                            <img :src="item.icon" alt="" v-if="item.icon">
                            {{ item.name }}
                        </a>
                    </li>
                    <li>
                        <a href="" class="bcb">投稿</a>
                    </li>
                </ul>
            </nav>
        </div>
    </header>
</template>

<script>
import $ from 'jquery'
export default {
    data() {
        return {
            cnav: [
                {
                    name: '资讯',
                    sub: ['电商消费', '娱乐淘金', '车与出行', '人工智能', '年轻一代', '智能终端', '医疗健康', '文化教育', '金融地产', '企业服务', '创业维艰', '社交通讯', '全球热点', '生活腔调']
                },
                {
                    name: '24小时'
                },
                {
                    name: '活动'
                },
                {
                    name: '创新快车道'
                },
                {
                    name: '虎嗅精选'
                },
                {
                    name: '官方Blog'
                },
                {
                    name: '新版体验',
                    icon: require('../../../static/images/face.png')
                }
            ],
            rnav: [
                {
                    name: 'APP下载',
                    icon: require('../../../static/images/phone.png')
                },
                {
                    name: '搜索',
                    icon: require('../../../static/images/search.png')
                },
                {
                    name: '登录'
                },
                {
                    name: '注册'
                }
            ]
        }
    },
    methods: {

    },
    mounted() {
        this.$nextTick(() => {
            $(window).scroll(() => {
                var distance = $(window).scrollTop();
                if (distance > 0) {
                    $('.header').addClass('active');
                } else {
                    $('.header').removeClass('active');
                }
            })
        })
    }
}
</script>

<style lang="less">
@import '.././../../static/less/header.less';
</style>
