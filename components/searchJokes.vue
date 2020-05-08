<template>
    <div class="container"> 
        

        <form @submit.prevent="onSubmit">
         <div class="input-field">
        <input type="text" name="Search_Jokes" v-model="text" placeholder="">
        <label for="last_name">Type here to Search for  Jokes</label>
        </div>
        <input type="submit" value="Search Jokes" class="btn wave-effect">
            </form>
            <hr>
            </div>
        
</template>
<script>
export default {
    name:'searchjokes',
    data(){
        return{
            text:''
        }
    },
    methods:{
        onSubmit(){
            this.$emit('search-text',this.text);
            this.text = '';
        }
    }
}
</script>