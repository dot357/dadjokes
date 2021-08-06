<template>
 <div>
   <h1 class="heading">WELCOME</h1>
   <p class="content">
     This project is based on a <a href="https://www.youtube.com/watch?v=ltzlhAxJr74" target="_blank">youtube video tutorial</a> that is easy to follow. While I was learning <strong>Nuxt JS</strong> i followed this path. But I have implemented some other features. Such as;



     <ul>
       <li>1. Text to speech using <a href="https://developer.mozilla.org/en-US/docs/Web/API/Web_Speech_API" target="_blank"><strong> Web Speech API</strong></a> </li>
     </ul>
   </p>

 </div>
</template>

<script>

export default {
  head(){

    return {
      title : 'Welcome to DAD JOKES #corny',
      meta : [
        {
          hid : 'desc',
          name : 'desc',
          content : 'Some entertainment'
        }
      ]
    }
  }
}
</script>


<style scoped>
.heading{
  letter-spacing: 3px;
}

.content{
  font-family: 'Montserrat', sans-serif;
  width: 80%;
 
  line-height: 1.6em;
}


a {
    position: relative;
    color: black;
    background: linear-gradient(to bottom,rgb(255, 251, 0) 0%,rgb(255, 136, 0) 100%);
    background-position: 0 100%;
    background-repeat: repeat-x;
    background-size: 1px 1px;
    transition: all 0.15s ease-in;
}

a:hover{
    color: black;
    text-decoration: none;
    position: relative;
    font-weight: 400;
    background: linear-gradient(to bottom,rgb(255, 251, 0) 0%,rgb(255, 136, 0) 100%);
    background-position: 0 100%;
    background-repeat: repeat-x;
    background-size: 7px 7px;
}
</style>
