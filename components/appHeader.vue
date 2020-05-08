<template>
  <div>
    <nav>
    <div class="nav-wrapper teal">
      <a href="#" class="brand-logo">Dad Jokes</a>
      <ul id="nav-mobile" class="right hide-on-med-and-down">
        <li><nuxt-link to='/'>Home</nuxt-link></li>
        <li><nuxt-link to='/jokes'>Jokes</nuxt-link></li>
         <li><nuxt-link to='/about'>about</nuxt-link></li>
      </ul>
    </div>
  </nav>
   
  </div>
</template>

<script>


export default {
    name:'appHeader',

 
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


