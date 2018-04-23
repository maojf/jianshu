<template>
    <div id="myHeader">
        <nav class="navbar navbar-fixed-top">
            <div class="width-limit">
                <!--logo-->                
                <nuxt-link class="logo" to="/">
                    <img src="~/assets/img/navlogo.png">
                </nuxt-link>
                <!--右上角，写文章-->
                <nuxt-link to="/write" class="write-btn">
                    <i class="fa fa-edit"></i>
                    写文章aaaaaa
                </nuxt-link>
                <!--登录用户信息-->
                <div class="user" @mouseover="isShow=true" @mouseleave="isShow=false">
                    <div class="drop-down">
                        <nuxt-link to="/u123" class="avatar">
                            <img src="~/assets/img/1.jpg">
                        </nuxt-link>
                    </div>
                    <ul class="drop-menu" v-show="isShow">
                        <li>
                            <nuxt-link to="/user/123">
                                <i class="fa fa-home"></i>
                                我的主页
                            </nuxt-link>
                        </li>
                        <li>
                            <nuxt-link to="/user/123/like">
                                <i class="fa fa-heart"></i>
                                喜欢的文章
                            </nuxt-link>
                        </li>
                        <li>
                            <nuxt-link to="/bookmarks">
                                <i class="fa fa-bookmark"></i>
                                收藏的文章
                            </nuxt-link>
                        </li>
                        <li>
                            <nuxt-link to="/settings/basic">
                                <i class="fa fa-cog"></i>
                                设置
                            </nuxt-link>
                        </li>
                        <li>
                            <nuxt-link to="/logout">
                                <i class="fa fa-sign-out"></i>
                                退出
                            </nuxt-link>
                        </li>
                    </ul>
                </div>
                <!--右上角-->
                <!--导航部分-->
                
                <div class="container">
                  <div class="row">
                    <div class="navbar-header">
                      <button @click="isNavListShow=!isNavListShow"> <!--**********************************************************************-->
                        <span class="icon"></span>
                        <span class="icon"></span>
                        <span class="icon"></span>
                      </button>
                    </div>

                    <transition enter-active-class="animated slideInDown" leave-active-class="animated slideOutUp">
  
                      <ul class="nav-list" v-show="isNavListShow"> <!--**********************************************************************-->
                        <li>
                          <nuxt-link to="/" class="active">
                            <i class="fa fa-compass"></i>
                            <span>发现</span>
                          </nuxt-link>
                        </li>
                        <li>    
                          <nuxt-link to="/follow">
                            <i class="fa fa-book"></i>
                            <span>关注</span>
                          </nuxt-link>
                        </li>
                        <li class="user" @mouseover="notifyShow=true" @mouseleave="notifyShow=false">
                          <nuxt-link to="/notify">
                              <i class="fa fa-bell-o"></i>
                              <span>消息</span>
                          </nuxt-link>
                          <ul class="drop-menu" v-show="notifyShow"> <!--**********************************************************************-->
                            <li>
                              <nuxt-link to="/">
                                <i class="fa fa-comment-o"></i>
                                  评论
                                  </nuxt-link>
                                </li>
                                <li>
                                  <nuxt-link to="/">
                                    <i class="fa fa-envelope"></i>
                                    简信
                                  </nuxt-link>
                                </li>
                                <li>
                                  <nuxt-link to="/">
                                    <i class="fa fa-plus-square-o"></i>
                                      关注
                                  </nuxt-link>
                                </li>
                                <li>
                                  <nuxt-link to="/">
                                    <i class="fa fa-heart-o"></i>
                                    喜欢和赞
                                  </nuxt-link>
                                </li>
                            </ul>
                          </li>
                          <li class="search">
                            <form method="post">
                                <input type="text" placeholder="搜索" class="search-input">
                                <a href="#" class="search-btn">
                                    <i class="fa fa-search"></i>
                                </a>
                            </form>
                          </li>
                      </ul>

                    </transition>


                  </div>
                   
                </div>
            </div>
        </nav>
    </div>
</template>

<script>
export default {
  data() {
    return {
      isShow: false,
      notifyShow: false,
      isNavListShow: false,
      screenWidth: 0,
      num: 0
    };
  }
  // methods:{
  //   navbarClick(){
  //     var navList = document.querySelector('.nav-list');
  //     this.num+=1
  //     if(this.num%2==1){
  //       navList.style.maxHeight = '226px';
  //     }else{
  //       navList.style.maxHeight = '0';
  //     }
  //   }
  // },
  // mounted () {
  //           const that = this
  //           window.onresize = () => {
  //               return (() => {
  //                   window.screenWidth = document.body.clientWidth
  //                   that.screenWidth = window.screenWidth
  //               })()
  //           }
  //       },
  // watch: {
  //           screenWidth (val) {
  //               this.screenWidth = val
  //           }
  //       }
};
</script>

<style scoped>
nav {
  width: 100%;
  height: 56px;
  border-bottom: 1px solid #fff;
}
.navbar {
  margin-bottom: 20px;
  border-width: 0 0 1px;
  border-color: #f0f0f0;
  background-color: #fff;
}
.navbar:before {
  content: "";
  display: table;
}
.navbar-fixed-top {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 9999;
}
nav .width-limit {
  min-width: 768px;
  max-width: 1440px;
  margin: 0 auto;
}
nav .logo {
  float: left;
  height: 56px;
}
nav .logo img {
  height: 100%;
}
nav .write-btn {
  float: right;
  width: 100px;
  height: 40px;
  line-height: 40px;
  margin: 8px 15px 0;
  border-radius: 20px;
  font-size: 15px;
  color: #fff;
  background: #ea6f5a;
  text-align: center;
}
nav .write-btn:hover {
  background: #ec6149;
  cursor: pointer;
}
nav .user {
  position: relative;
  float: right;
  overflow: hidden;
}
nav .user:hover {
  background: #f5f5f5;
}
nav .user .avatar {
  position: relative;
  display: block;
  width: 40px;
  height: 40px;
  margin: 8px 28px 8px 20px;
}
nav .user .avatar:before {
  content: "";
  position: absolute;
  border-left: 5px solid transparent;
  border-right: 5px solid transparent;
  border-top: 5px solid #999;
  top: 18px;
  right: -14px;
}
nav .user .avatar img {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  border: 1px solid #eee;
}
nav .user .drop-menu {
  position: absolute;
  box-shadow: 0 0 8px rgba(0, 0, 0, 0.1);
  min-width: 160px;
  z-index: 999;
  margin: 0;
  padding: 10px 0;
  font-size: 15px;
  background: white;
}
nav .user .drop-menu li a {
  padding: 10px 20px;
  line-height: 30px;
  display: block;
}
nav .user .drop-menu li a:hover {
  background: #f5f5f5;
}
nav .user .drop-menu li a i {
  margin-right: 10px;
  color: #ea6f5a;
  width: 20px;
  height: 20px;
  font-size: 20px;
  display: inline-block;
}
nav .nav-list {
  float: left;
  margin: 0;
  background: white; /**************************************************************************************/
}
/* nav .nav-list:after{
    content: '';
    height: 0;
    display: block;
    visibility: hidden;
    clear: both;
} */
nav .nav-list > li {
  float: left;
  margin-right: 5px;
}
nav .nav-list > li a {
  display: block;
  height: 56px;
  line-height: 26px;
  padding: 15px;
}
nav .nav-list > li a.active {
  color: #ea6f5a;
  background: none !important;
}
nav .nav-list > li a:hover {
  background: #f5f5f5;
}
nav .nav-list > li a i {
  margin-right: 5px;
  font-size: 20px;
}
nav .nav-list .search {
  padding-left: 15px;
  margin-right: 10px;
}
nav .nav-list .search form {
  margin-bottom: 20px;
  position: relative;
  top: 9px;
}
nav .nav-list .search form .search-input {
  width: 240px;
  height: 38px;
  font-size: 14px;
  padding: 0 40px 0 20px;
  border: 1px solid #eee;
  background: #eee;
  border-radius: 40px;
  transition: width 0.5s;
}
nav .nav-list .search form .search-input:focus {
  width: 320px;
}
nav .nav-list .search form .search-input:focus ~ .search-btn {
  background: #969696;
  color: white;
  border-radius: 50%;
  font-size: 5px;
}
nav .nav-list .search form .search-btn {
  position: absolute;
  width: 30px;
  height: 30px;
  top: 4px;
  right: 5px;
  color: #969696;
  text-align: center;
  padding: 0;
}
nav .nav-list .search form .search-btn:hover {
  background: none;
}

nav .nav-list .search form .search-btn i {
  display: block !important;
  margin: 0;
  text-align: center;
  line-height: 30px;
}
nav .container .navbar-header button {
  float: left;
  padding: 11px 10px;
  margin-top: 9px;
  border: 1px solid #ddd;
  background: white;
  border-radius: 4px;
  display: none;
}
nav .container .navbar-header button:hover {
  background: #f7f7f7;
  cursor: pointer;
}
nav .container .navbar-header button:after {
  content: "";
  display: block;
  clear: both;
}
nav .container .navbar-header button .icon {
  background-color: #969696;
  color: rgb(51, 51, 51);
  cursor: pointer;
  display: block;
  width: 22px;
  height: 2px;
  margin-top: 4px;
}
nav .container .navbar-header button .icon:nth-of-type(1) {
  margin-top: 0;
}

@media (max-width: 1440px) {
  nav .nav-list > li a i {
    display: none;
  }
  nav .nav-list .search form .search-input {
    width: 160px;
  }
  nav .nav-list .search form .search-input:focus {
    width: 240px;
  }
}
@media (max-width: 1080px) {
  nav .nav-list li span {
    display: none;
  }
  nav .nav-list > li a i {
    display: block;
    height: 226px;
  }
}
@media (max-width: 768px) {
  /**************************************************************************************/
  nav .nav-list {
    /* max-height: 0; */
    /* display: block; */
    z-index: -10;
    overflow: hidden;
    width: 100%;
    float: none;
    position: absolute;
    top: 56px;
    left: 0;
    box-shadow: 0 0 8px rgba(0, 0, 0, 0.1);
    /* transition: max-height 0.5s; */
  }
  nav .container .navbar-header button {
    display: block;
  }
  nav .nav-list li span {
    display: block;
  }
  nav .nav-list > li a i {
    display: none;
  }
  nav .nav-list li {
    float: none;
    /* display: block; */
  }
  nav .nav-list li span {
    text-align: center;
  }
  nav .nav-list .search form .search-input {
    width: 100%;
  }
  nav .nav-list .search form .search-input:focus {
    width: 100%;
  }
}

@media (min-width: 768px) {
  .nav-list {
    display: block !important;
  }
}
</style>