<template>
   <div class="container">
     <h3 class="indigo-text" v-if="searching">Fetching Jokes.Please wait ........ </h3>
 <div v-if="loading">
    <searchJokes v-on:search-text ="searchText"/>
  <joke v-for="joke in jokes" :key="joke.id" :id="joke.id" :joke="joke.joke" />
  </div>
  <h6 v-if="message && !searching &&loading" class="cyan-text">no Joke Found for Your Search</h6>
  </div>
</template>

<script>
import axios from 'axios'
import joke from '../../components/joke'
import searchJokes from '../../components/searchJokes.vue'
export default {
  name:'index',
    components:{
        joke,
        searchJokes
    },
  data(){
      return{
           jokes:[],
           loading:false,
           searching:false,
           message:false

      }
  },
 async  created(){
   const config ={
       headers:{
           'Accept':'application/json'
       }
   }
   try {
       const res = await axios.get('https://icanhazdadjoke.com/search',config)
      this.jokes =(res.data.results);
    
      this.loading = true;

   } catch (error) {
       console.log(error)
   }
   
  },
  methods:{
        async searchText(text){
          this.searching =true;
              const config ={
       headers:{
           'Accept':'application/json'
       }
   }
   try {
       const res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`,config)
      this.jokes =(res.data.results)
        //console.log(res.data.results);
        if(res.data.results.length ===0){
         this.message = true;
        }else{
              this.message = false;
              this.loading =true;
        }
      this.searching = false;
   } catch (error) {
       console.log(error)
   }
      
         }
  },
  head () {
    return {
        title:'Dad Jokes',
        meta:[
            {
                hid:"decription",
                name:'decription',
                content:'Best places for Cory Daddy Jokes',
            }

        ],
      script: [
        { src: 'https://cdnjs.cloudflare.com/ajax/libs/materialize/1.0.0/js/materialize.min.js' }
      ],
      link: [
        { rel: 'stylesheet', href: 'https://cdnjs.cloudflare.com/ajax/libs/materialize/1.0.0/css/materialize.min.css' }
      ]
    }
  }
}
</script>


