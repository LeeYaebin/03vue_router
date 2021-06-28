<template>
  <h2 class="text-center mt-4 mb-4">product</h2>
  <div class="container mb-4">
    <div class="row">
      <div class="col-sm-6 col-md-3 p-2" v-for="(item,i) in pdata" :key="i">
        <img :src="pdata[i].image" alt="" class="w-100 p-1">
        <div @click="$emit('pOpen',pdata[i].id)">{{pdata[i].title}}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name:'product',
  props:['pdata']
}
</script>

<style>

</style>