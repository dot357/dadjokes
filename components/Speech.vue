<template>
  <div>
      <button :class="{active:isPlayying, 'play': !isPlayying  }" v-if="isPlayying == false" @click="playSound">Play </button> <!-- will be adding font awsome soon --> 
     

      <button  :class="{active:isPlayying, 'stop': isPlayying  }" v-if="isPlayying == true"  @click="stopSound">Stop </button>

  </div>
</template>

<script>
export default {
  name: "Speech",
  data(){
    return {
      isPlayying: false
    }
  },
  props: {
      text: String,
  },
  methods: {
    playSound() {
        console.log(this.text);
      var synth = window.speechSynthesis;

     //speech synthesis is here but doesnt work on chrome fix that

      var utterThis = new SpeechSynthesisUtterance(this.text);
   
      
         utterThis.lang= 'en-US';
         utterThis.pitch =0.9;
         utterThis.rate =0.9;
       this.isPlayying = !this.isPlayying
      synth.speak(utterThis);
     
    
    },
    stopSound(){
      var synth = window.speechSynthesis;
      this.isPlayying = !this.isPlayying
      synth.cancel()
    }
  },
};
</script>

<style scoped>
button{
  padding:1em 2em;
  outline:none;
  border:none;
  transition: all 0.15s ease;
  cursor: pointer;
  box-shadow: 0px 3px 3px -2px rgba(0, 0, 0, 0.288);
  margin-top: 13px;
  font-weight: 600;
  font-family: 'Montserrat', sans-serif;
  text-transform: uppercase;
  letter-spacing: 4px;
  
}

button:focus, button:hover{
  transform: scale(0.9);
box-shadow: 0px 3px 3px -2px rgba(0, 0, 0, 0);
}


.play{
  background: #99d066;
  color: #1d3b00;
}

.stop{
  background: #ff7543;
    color: #9f0000;
}

</style>