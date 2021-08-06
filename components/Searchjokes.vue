<template>
    <form @input.prevent="OnSubmit">
        <input type="text" v-model="text" placeholder="Search Jokes">
        
    </form>
</template>

<script>
export default {
    data(){
        return{
            text : ''
        }
    },
    methods: {
        OnSubmit(){
            
            this.$emit('search-txt', this.text)
        }
    }
    
}
</script>

<style scoped>

form input{
    width: 25%;
    padding: 13px 13px;
    border-radius: 4px;
    border:1px solid rgba(0, 0, 0, 0.253);
    transition: all 0.5s ease-in;
}
form input:focus{
    width: 100%;
    outline: none;
    
    border:1px solid rgb(0, 0, 0);
}

</style>