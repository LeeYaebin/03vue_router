<template>
  <top-header/>
  <router-view :pdata="pdata"
  @pOpen="pView=true; pNum=$event" :bdata="bdata" @bOpen="bView=true; bNum=$event">
  </router-view> 
  <bottom-footer></bottom-footer>
  
<transition name="fade">
<pPop :pdata="pdata" :pView="pView" :pNum="pNum" @pClose="pView=false"/>
</transition>
<transition name="fade">
<bPop :bdata="bdata" :bView="bView" :bNum="bNum" @bClose="bView=false"/>
</transition>
</template>

<script>
import pPop from './components/pPop.vue'
import bPop from './components/bPop.vue'
import header from './components/header.vue'
import pdata from './pdata.js'
import footer from './components/footer.vue'
import bdata from './bdata.js'

export default {
  name:'app',
  components:{
    'top-header':header,
    'bottom-footer':footer,
    pPop,
    bPop
  },
  data(){
    return{
      bdata:bdata,
      bView:false,
      bNum:0,
      pdata:pdata,
      pView:false,
      pNum:0

    }
  }
}
</script>

<style>
.pPop {
  position: fixed; z-index:10;
  background: #fff; width: 80%; top:50%; left: 50%;
  transform: translate(-50%,-50%);
  box-shadow: 0 0 10px rgba(0,0,0,0.5); border-radius: 10px; padding: 20px;
  }

  .bPop {
  position: fixed; z-index:10;
  background: #fff; width: 80%; top:40%; left: 50%;
  transform: translate(-50%,-50%);
  box-shadow: 0 0 10px rgba(0,0,0,0.5); border-radius: 10px; padding: 20px;
  }

.fade-enter-from { opacity: 0;}
.fade-enter-active { transition:0.3s; }
.fade-enter.to { opacity: 1;}

.fade-enter.to {}
.fade-enter-active {}
.fade-enter-from {}


@media screen and (min-width:900px){
  .pPop {width: 600px;}
}
</style>