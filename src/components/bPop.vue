<template>
  <div v-if="bView==true">
  <div class="bPop text-center">
      <div class="text-center">
        <p class="mb-3">{{bdata[bNum].title}}</p>
        <p class="content">{{bdata[bNum].content}}</p>
        <button class="btn btn-primary" @click="$emit('bClose')">닫기</button>
      </div>
    </div>
</div>
</template>

<script>
export default {
name:'bPop',
props:['bdata','bNum','bView']
}
</script>

<style>
.content { color:#f17081; }
</style>