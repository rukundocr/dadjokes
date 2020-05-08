<template>
     <div class="container">
         <br>
         <nuxt-link to="/jokes" class="btn teal black-text">Back to Jokes</nuxt-link>
         <hr>
     <h3 class="indigo-text" v-if="loading" >Looking for Response.Please Wait ..............</h3>
     <div v-if="available">
        <h3 class="teal-text">{{joke}}</h3>
        <hr>
        <small>Joke ID:<span class="purple-text">{{$route.params.id}}</span></small>
    </div>
     </div>
   

</template>
<script>
import axios from 'axios'
export default {
    data(){
        return{
        loading:true,
        available:false,
        joke:{},
        id:this.$route.params.id

        }
    },
   async  created(){
         const config ={
       headers:{
           'Accept':'application/json'
       }
   }
       try {
           const res = await axios.get(`https://icanhazdadjoke.com/j/${this.id}`,config)
           console.log(res.data.joke)
           this.joke = res.data.joke;
           this.available = true;
           this.loading = false;
       } catch (error) {
           console.log(error)
       }
     
    }
}
</script>