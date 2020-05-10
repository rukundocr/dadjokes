<template>
  <div class="container" >

    <h4 class="teal-text">Welcome to the Best dad Jokes </h4>
    <jokes/>
  </div>
</template>

<script>

import jokes from "./jokes/index";
export default {
  components:{
   jokes
  },
  head () {
    return {
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


