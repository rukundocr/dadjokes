<template>
<div class="container">
 <nuxt-link :to="'jokes/'+ id ">
   <div class="card teal-text">
      {{joke}}
    </div>
 </nuxt-link>
  </div>
</template>

<script>
export default {
    name:'joke',
    props:[
        'joke',
        'id'
    ]
    
}
</script>