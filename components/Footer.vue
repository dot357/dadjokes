<template>
   <footer>
       <div class="topLevel"><h3><sup>#SUPERCORNY</sup> Dad Jokes <sup>©{{ date }}</sup></h3></div>
       
   </footer>
</template>


<script>
export default {
    name : 'Footer',
    data(){
        return {
            date : new Date().getFullYear()
        }
    }
}
</script>


<style scoped>

footer{
    font-family: 'Montserrat', sans-serif;
    width: 100%;
    background: #f8f8f8;
    padding-top: 13px;
    padding-bottom: 13px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    box-shadow: 0px -3px 5px -2px rgba(0, 0, 0, 0.247)
    
}
.topLevel h3{
    text-transform: uppercase;
    font-family: 'Playfair Display', serif;
    transition: all 0.15s ease;
    cursor: pointer;
}
.topLevel sup{
    font-size:0.6em;
    font-family: 'Montserrat', sans-serif;
    
}

.topLevel:hover{
    letter-spacing: 4px;
    text-shadow: 0px 15px rgba(0, 0, 0, 0.308);
}

</style>