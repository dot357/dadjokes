<template>
    <div>
        <Menuofapp />
        <div class="container">
            <nuxt />
        </div>
        <Footer />
    </div>
</template>

<script>

import Footer from '../components/Footer.vue'
import Menuofapp from '../components/Menuofapp.vue'
export default {
    name :'default',
    components:{
        Footer,
        Menuofapp,
       
    }
    
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;500;700&display=swap');


* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {

  font-size: 1rem;
  line-height: 1.6;
  background: white;
  font-family: 'Playfair Display', serif;
    color: black;
}
a {
  
  text-decoration: none;
}
ul {
  list-style: none;
}
.container {
  min-height: 82vh;
    padding: 24px 13px;
}
</style>