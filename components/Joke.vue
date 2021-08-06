<template>
 
    <div class="joke">
       <nuxt-link class="link" :to="'jokes/'+ id">
      <p>{{ joke }}</p>
     </nuxt-link>
    <!-- 
       <hr />
      <span> Joke ID :<b>{{ id}}</b></span>
      -->
     <!-- <Speech :text="joke" @click="disablePlay" /> -->
    </div>
  

</template>

<script>
import Speech from './Speech.vue';
export default {
  name: "Joke",
  props: {
    joke: String,
    id: String,
  },
  components:{
    Speech
  },
  methods:{ //disable playlinks and wait for it end
    disablePlay(){
      console.log("hidden");
      this.$emit('hide-play')
    }
  }
};
</script>

<style scoped>

.link {
   color: black;
  
}


.joke {
  padding: 1rem;
  border: 1px dotted #ccc;
  margin: 1rem 0;
}
hr{
  margin-top: 7px;
  border: none;
}

span{
  font-size: 0.7em;
      font-family: 'Montserrat', sans-serif;
}
</style>