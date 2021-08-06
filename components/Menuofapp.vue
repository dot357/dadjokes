<template>
    <header class="header">
        <h1 class="title">Dad jokes</h1>
        <ul>
            <li>
                <nuxt-link to="/">Home</nuxt-link>
                <nuxt-link to="/jokes">Jokes</nuxt-link>
                <nuxt-link to="/about">About</nuxt-link>
            </li>
        </ul>
    </header>
</template>

<script>
export default {
    name : 'Menuofapp',
    
    
}
</script>


<style scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0;
  padding: 13px 13px;
  border-bottom: 1px dotted #ccc;
}
.header .title {
  font-size: 2rem;
  color: black;
  font-family: 'Playfair Display', serif;
  text-transform: uppercase;
  letter-spacing: 2px;
}
.header ul {
  display: flex;
  list-style: none;
}


.header a {
  display: inline-block;
  background: #333;
  color: #fff;
  padding: 0.3rem 1rem;
  margin-right: 0.5rem;
}
</style>