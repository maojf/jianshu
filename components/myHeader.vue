<template>
    <div id="myHeader">
        <nav class="navbar navbar-fixed-top">
            <div class="width-limit"></div>
        </nav>
    </div>
</template>

<script>
export default {
  
}
</script>

<style scoped>
    nav{
        width: 100%;
        height: 56px;
    }
    .navbar{
        margin-bottom: 20px;
        border-width: 0 0 1px;
        border-color: #f0f0f0;
        background-color: #fff;
    }
    .navbar:before{
        content: '';
        display: table;
    }
    .navbar-fixed-top{
        position: fixed;
        top: 0;
        left: 0;
        z-index: 9999;
    }
    nav .width-limit{
        min-width: 768px;
        max-width: 1440px;
        margin: 0 auto;
        height: 56px;/************/
    }
</style>