<template>
  <div class="container">
    <div v-for="post in postData" :key="post.id">
        Title:{{post.title}}
        <br>
        Body:{{post.body}}
        <hr>
    </div>
  </div>
</template>

<script>
export default {
name:'posts',
data(){
return {postData:undefined}
},
mounted(){
    const URL="https://jsonplaceholder.typicode.com/posts";
    fetch(URL)
    .then(res=>res.json())
    .then(data=>{
        this.postData=data
    })
}
}
</script>

<style>

</style>