<template>
  <h2 class="text-center mt-4 mb-4">board</h2>
  <table class="table mb-4">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">내용</th>
      <th scope="col">날짜</th>
    </tr>
  </thead>
  <tbody>
    <tr v-for="(item,i) in bdata" :key="i">
      <td>{{bdata[i].idx+1}}</td>
      <td @click="$emit('bOpen',bdata[i].idx)">{{bdata[i].title}}</td>
      <td>{{bdata[i].data}}</td>
    </tr>
  </tbody>
</table>
</template>

<script>
export default {
name:'board',
props:['bdata']
}
</script>

<style>
th { background: #fad6dc; color:#333; }
</style>