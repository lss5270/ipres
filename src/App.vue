<template>
  <div id="app" v-cloak>
    <!-- <img src="./assets/logo.png"> -->
    <transition :name="transitionName">
      <router-view  class="child-view"/>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
     return {
       transitionName: 'slide-left'
     }
   },
  watch: {
    '$route' (to, from) {
      const toDepth = to.path.split('/').length
      const fromDepth = from.path.split('/').length
      this.transitionName = toDepth < fromDepth ? 'slide-right' : 'slide-left'
    }
  }
}
</script>

<style>
[v-cloak] {
  display: none;
}

body{
    background:#fff;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /*text-align: center;
  color: #2c3e50;*/
  /*margin-top: 60px;*/
  background-color: #fff;

  font-size: 0.24rem;
  -webkit-overflow-scrolling: touch;
}
*{
  margin: 0;
  padding: 0;
}
.mint-header{
  background: #666;
  font-size: 0.3rem;
  line-height: normal;
  height: 0.9rem;
}
.mint-header-title{
  font-size: 0.36rem;
}
.mintui{
  font-size: 0.30rem;
}
.body{
  /*height: 10rem;*/
  margin-top: 0.9rem;
  /*padding: 1rem 0;*/
}

/*临时性解决分页加载更多bug*/
.page-loadmore-wrapper {

    margin-top: -1px;
    overflow: auto;
}

/*路由切换动画*/
.child-view {
  position: absolute;
  width:100%;
  transition: all .5s cubic-bezier(.55,0,.1,1);
}
.slide-left-enter, .slide-right-leave-active {
  opacity: 0;
  -webkit-transform: translate(150px, 0);
  transform: translate(150px, 0);
}
.slide-left-leave-active, .slide-right-enter {
  opacity: 0;
  -webkit-transform: translate(-150px, 0);
  transform: translate(-150px, 0);
}
</style>
