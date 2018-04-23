<template>
    <div id="index" style="height:100%">
        <my-header></my-header>
        <div class="container index">
            <div class="row">
                <div class="col-xs-16 main">
                    <!--热门专题-->
                    <div class="recommend-collection">
                        <nuxt-link class="collection" to="/collection/123">
                            <img src="~/assets/img/c1.jpg">
                            <span name="name">故事</span>
                        </nuxt-link>
                        <nuxt-link class="collection" to="/collection/123">
                            <img src="~/assets/img/c2.jpg">
                            <span name="name">摄影</span>
                        </nuxt-link>
                        <nuxt-link class="collection" to="/collection/123">
                            <img src="~/assets/img/c3.jpg">
                            <span name="name">人文社科</span>
                        </nuxt-link>
                        <nuxt-link class="collection" to="/collection/123">
                            <img src="~/assets/img/c4.jpg">
                            <span name="name">历史</span>
                        </nuxt-link>
                        <nuxt-link class="collection" to="/collection/123">
                            <img src="~/assets/img/c5.jpg">
                            <span name="name">读书</span>
                        </nuxt-link>
                        <nuxt-link class="more-collection" to="/">
                            更多热门专题
                            <i class="fa fa-angle-right"></i>
                        </nuxt-link>   
                    </div>
                    <div class="split-line"></div>
                </div>
                <div class="col-xs-offset-1 col-xs-7 aside">
                    侧边栏
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import myHeader from '../components/myHeader'
export default {
    head:{
        title:'简书-创作你的创作',
        meta:[
            {name:'keywords',content:'简书首页'},
            {name:'description',content:'简书首页'},
            {name:'author',content:'毛江峰'}
        ]
    },
    components:{
        myHeader
    },
    data(){
        return{
            
        }
    }
}
</script>

<style scoped>

</style>