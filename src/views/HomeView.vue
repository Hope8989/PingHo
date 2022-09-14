<template>
  <div class="home">
    <div class="grid">
      <div class="row">
        <img class= "mt" alt="mt" src="../assets/mnt.jpeg">
        <img class= "mt" alt="mt" src="../assets/mnt.jpeg">
        <img class= "mt" alt="mt" src="../assets/mnt.jpeg">
      </div>
      <div class="row">
        <img class= "mt" alt="mt" src="../assets/mnt.jpeg">
        <img class= "mt" alt="mt" src="../assets/mnt.jpeg">
        <img class= "mt" alt="mt" src="../assets/mnt.jpeg">
      </div>
    </div>
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
  width: 25%;
  max-width: 400px;
  border-radius: 25px;
  transition: all 1s cubic-bezier(.11,.48,.1,.49);
}

.mt:hover {
  width: 33%;
  max-width: 600px;
}

.row {
  width: 100%;
}


</style>
