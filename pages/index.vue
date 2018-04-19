<template>
    <div id="index" style="height:100%">
        <my-header></my-header>
        <p>我的主题内容部分</p>
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