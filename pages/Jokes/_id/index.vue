<template>
    <div>
        <nuxt-link class="link" to="/jokes">Back to jokes</nuxt-link>
        <h2>{{ joke}} </h2>
        <hr />
        <p class="id">  {{$route.params.id}}</p>

        <Speech  :text="stringJoke"/>
    </div>
</template>

<script>
import axios from 'axios'
import Speech from '../../../components/Speech.vue'

export default {
  components: { Speech },
    head(){
      return {
          title : this.joke,
          meta : [
              {
                  hid: this.$route.params.id,
                  name : this.$route.params.id,
                  content : this.joke
              }
          ]
      }  
    },

    data(){
        return {
            joke : [],
            stringJoke : ''
        }
    },
    async created() {
    const config = {
      headers: {
        Accept: "application/json",
      },
    };

    try {
      const res = await axios.get(`https://icanhazdadjoke.com/j/${this.$route.params.id}`, config);
      
      this.joke = res.data.joke;
   
      this.stringJoke = this.joke
     
    } catch (err) {
        console.log(err)
    }
  },
    
   
}
</script>


<style scoped>

.link {
    position: relative;
    color: black;
    background: linear-gradient(to bottom,rgb(255, 251, 0) 0%,rgb(255, 136, 0) 100%);
    background-position: 0 100%;
    background-repeat: repeat-x;
    background-size: 1px 1px;
    transition: all 0.15s ease-in;
}

.link:hover{
    color: black;
    text-decoration: none;
    position: relative;
    font-weight: 400;
    background: linear-gradient(to bottom,rgb(255, 251, 0) 0%,rgb(255, 136, 0) 100%);
    background-position: 0 100%;
    background-repeat: repeat-x;
    background-size: 7px 7px;
}

.id{
      font-family: 'Montserrat', sans-serif;
}

</style>