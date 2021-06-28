<template>
  <div v-if="pView==true">
  <div class="pPop text-center">
      <div class="text-center">
        <img v-bind:src="pdata[pNum].image" alt="" class="w-100 mb-3">
        <p>{{pdata[pNum].title}}</p>
        <button class="btn mt-3 mb-2" @click="$emit('pClose')">닫기</button>
      </div>
    </div>
</div>
</template>

<script>
export default {
name:'pPop',
props:['pdata','pNum','pView']
}
</script>

<style>
.pPop { width: 80%; }
.btn { background:pink; transition:0.3s; border: none; }
.btn:hover { background:rgb(207, 52, 112); color:#fff; }
</style>