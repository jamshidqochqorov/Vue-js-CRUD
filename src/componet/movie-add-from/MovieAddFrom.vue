<template>
 <div class="moovie-add-form">
   <h3>Yangi kino qo'shish</h3>
   <form class="add-form d-flex" @submit.prevent>
        <input type="text" v-model="name" class="form-control new-movie-label" placeholder="Qanday kino ?" >
        <input type="number" v-model="viewers" class="form-control new-movie-label" placeholder="Nechi marotaba ko'rilgan?" >
     <PharmaryButton @click="channge" type="submit" class="btn-outline-dark">Qo'shish</PharmaryButton>
   </form>
 </div>
</template>

<script>

export default {

data(){
  return{
    name:"",
    viewers:"",
  }
},
  methods:{
   channge(){
     if(!this.name || !this.viewers) return
     const Movie = {
       name:this.name,
       viewers: this.viewers,
       favourite:false,
       like:false,
     }
     this.$emit('createMovie',Movie)
     this.name = ""
     this.viewers = ""
   }
  }

}
</script>

<style scoped>
.moovie-add-form{
  margin-top: 2rem;
  padding: 1.5rem;
  background-color: #fcfaf5;
  border-radius: 4px;
  box-shadow: 15px 15px 15px rgb(0,0,0,0.15);

}
</style>