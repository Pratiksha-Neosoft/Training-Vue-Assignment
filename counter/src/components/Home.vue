<template>
  <div>
      <h1 class="heading">Counter</h1>
      <counter />
  </div>
</template>

<script>
import Counter from './counter.vue'
export default {
name:'Home',
components:{
Counter
}
}
</script>

<style>
.heading{
    padding: 5px;
    color:aqua;
}
</style>