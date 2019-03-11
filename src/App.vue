<template>
  <div id="app">

    <!--btn1-->
    <!--<bf-btn1 :btn1Msg="msg"></bf-btn1>-->

    <gl-btn>咕噜</gl-btn>
    <gl-btn icons="download">咕噜</gl-btn>
    <gl-btn :loading="true" icons="like" icon-position="left">咕噜</gl-btn>
    <gl-btn :loading="true" icons="settings" icon-position="right">咕噜</gl-btn>
    <gl-btn :loading="isloading" @click=" isloading = !isloading ">咕噜</gl-btn>

    <g-icon iconName="download"></g-icon>

  </div>
</template>

<script>

  import bfbtn1 from './components/button/btn1/btn1.vue'
  import glbtn from './components/button/btn_gulu/btngl.vue'
  import gicon from './components/icon/icon.vue'

export default {
  name: 'app',
  data () {
    return {
      msg: '从此开始',
      isloading: false
    }
  },
  components:{
      'bf-btn1': bfbtn1,
      'gl-btn':glbtn,
      'g-icon':gicon
  }
}
</script>

<style lang="scss">
  #app{
    padding-left: 120px;
    padding-top: 50px;
  }
</style>
