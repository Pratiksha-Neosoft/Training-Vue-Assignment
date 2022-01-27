<template>
  <div>
      {{data}}<br>
      <input type="text" v-model="data">
        <button v-on:click="increment">Increment</button>
        <button v-on:click="decrement">Decrement</button>
        <button v-on:click="reset">Reset</button>
  </div>
</template>

<script>
export default {
name:'counter',
data(){
    return { data:0}
},
methods:{
    increment(){
    this.data=this.data+1    
    }

}
}
</script>

<style>

</style>