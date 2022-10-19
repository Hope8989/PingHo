<template>
  <nav class="ui fixed top inverted menu">
    <router-link class="item" to="/">
      <i class="home icon" />Home</router-link> 
    <router-link class="item" to="/bye">Bye</router-link> 
    <router-link class="item" to="/about">About</router-link>
  </nav>
  <div class="pad">
    <router-view/>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983 !important;
}

.pad {
  padding-top: 60px;
}

</style>
