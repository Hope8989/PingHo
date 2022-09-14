<template>
  <div class="home">
    <img class= "mt" alt="mt" src="../assets/mnt.jpeg">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  }
}
</script>

<style type="text/css" scoped>
.mt {
  width: 80%;
  min-width: 200px;
  max-width: 400px;
  border-radius: 25px;
  transition: all 1s cubic-bezier(.11,.48,.1,.49);
}

.mt:hover {
  width: 90%;
  min-width: 300px;
  max-width: 600px;
}


</style>
