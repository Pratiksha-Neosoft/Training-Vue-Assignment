<template>
  <div>
       <h2> Products </h2>
       <i class="fa fa-cart"></i>{{count}}
       <div class="row">
           <div class="col-md-4" v-for="pro of proData" :key="pro.id">
               <div class="card" style="width: 18rem;">
  <img class="card-img-top" :src="pro.image" width=200 height=150 alt="Card image cap">
  <div class="card-body">
    <h5 class="card-title">{{pro.pname}}</h5>
    <p class="card-text">
        Price : <b> {{pro.price}} </b> <br/>
        Quantity : <b> {{pro.quantity}}</b>
    </p>
    <a href="javascript:void(0)" class="btn btn-primary" @click="addToCart()">Add To Card</a>
    <a href="javascript:void(0)" class="ml-2 btn btn-primary" v-on:click="delPro(pro.id)">Delete</a>
  </div>
</div>
           </div>
       </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name:"Products",
  data(){
      return {proData:undefined,count:0};
  },
  methods:{
      delPro(id){
           const URL="http://localhost:3000/products/";
          if(confirm("Do u want to delete it ?")){
              axios.delete(`${URL}${id}`)
              .then(res=>{
                  if(res){
                       axios.get(URL)
                       .then(res=>{
                         this.proData=res.data;
                     })
                  }
              })
          }
      },
      addToCart(){
        localStorage.setItem('cart',this.count++);
      }
  }
  ,
  mounted(){
    const URL="http://localhost:3000/products";
    axios.get(URL)
    .then(res=>{
        console.log(res.data)
        this.proData=res.data;
    })
  }
}
</script>

<style>

</style>