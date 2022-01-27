<template>
  
</template>

<script>
export default {
name:'users',
data(){
return {userData:undefined}
},
mounted(){
    const URL="https://jsonplaceholder.typicode.com/posts";
    fetch(URL)
    .then(res=>res.json())
    .then(data=>{
        this.userData=data
    })
}
}
</script>

<style>

</style>