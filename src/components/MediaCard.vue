<!-- 
 列表通用电影卡片
-->
<template>
    <div class="card_wrap">
        <div class="item" v-for="media in media" :key="media.movieId" @click="jumpDetail(media.movieId)">
            <mu-card>
                <mu-card-media>
                    <div class="default_bg">
                        <div :style="`background-image: url(${media.image})`" class="img"></div>
                    </div>
                </mu-card-media>
                <mu-card-title titleClass="media_title" :title="media.title" subTitle="" />
            </mu-card>
        </div>
    </div>
</template>
<script>
let _self;
import Layout from '@/components/Layout';

export default {
    props: {
        media: {
            type: Array,
            require: true
        },
    },
    mounted() {},
    methods: {
        jumpDetail(id) {
            this.$router.push(`/movie/detail/${id}`)
        },
        getImageUrl(url) {
            let image = `background-image: url(${url})`;
            return image;
        }
    },
    computed: {
        
    },
};

</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
.card_wrap {
    padding: 0;
    margin: auto;
    .item {
        text-align: center;
        position: relative;
        display: inline-block;
        margin: 0 2px;
        margin-bottom: .8em;
        width: 50%;
        cursor: pointer;
        -moz-page-break-inside: avoid;
        -webkit-column-break-inside: avoid;
        break-inside: avoid;
        transition: 0.5s;
        &:hover {
            box-shadow: 0 0 16px #999;
        }
        .default_bg {
            background: url(../assets/images/default.jpeg) no-repeat;
            background-size: 100%;
        }
        .img {
            height: 110px;
            background-repeat: no-repeat;
            background-size: cover;
        }
    }
}

</style>
<style lang="less">
.media_title {
    font-size: 1em!important;
    line-height: 20px!important;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
}

</style>
<style scoped lang="less">
@import url('../assets/less/common.less');
// 响应式布局，流式布局

/* 大屏幕（大桌面显示器，最小宽度 1200px） */

@media (min-width: @screen_mg_min) {
    .card_wrap {
        max-width: 1200px!important;
        .item {
            margin: 0 10px;
            margin-bottom: 10px;
            width: 17%!important;
            .img {
                height: 305px!important;
            }
        }
    }
}


/* 大屏幕（大桌面显示器，大于等于 1200px） */

@media (max-width: @screen_lg_min) {
    .card_wrap {
        max-width: 1100px!important;
        .item {
            width: 20%!important;
            .img {
                height: 290px!important;
            }
        }
    }
}

/* 中等屏幕（桌面显示器，大于等于 992px） */

@media (max-width: @screen_md_min) {
    .card_wrap {
        max-width: 900px!important;
        .item {
            width: 24%!important;
            .img {
                height: 280px!important;
            }
        }
    }
}

/* 小屏幕（平板，大于等于 768px） */

@media (max-width: @screen_sm_min) {
    .card_wrap {
        padding: 0 5px!important;
        .item {
            width: 26%!important;
            .img {
                height: 250px!important;
            }
        }
    }
}


/* 小屏幕（手机，大于等于 640px） */

@media (max-width: @screen_mi_min) {
    .card_wrap {
        padding: 0 5px!important;
        .item {
            width: 32%!important;
            .img {
                height: 240px!important;
            }
        }
        
    }
}

@media (max-width: 510px) {
    .card_wrap {
        padding: 0 5px!important;
        .item {
            width: 32%!important;
            .img {
                height: 140px!important;
            }
        }
        
    }
}

</style>
<style lang="less">
    .card_wrap {
        .mu-card-title-container {
            padding: 15px 2px;
        }
    }
</style>