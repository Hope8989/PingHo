<template>
  <div class="home">
    <div class="ui grid container">
      <div class="ui row">
        <div class="ten wide column">
          <img class= "mt" alt="mt" src="../assets/mnt.jpeg">
          <img class= "mt" alt="mt" src="../assets/mnt.jpeg">
          <img class= "mt" alt="mt" src="../assets/mnt.jpeg">
          <img class= "mt" alt="mt" src="../assets/mnt.jpeg">
          <img class= "mt" alt="mt" src="../assets/mnt.jpeg">
          <img class= "mt" alt="mt" src="../assets/mnt.jpeg">
        </div>
        <div class="six wide column">
          <HelloWorld msg="Welcome to Your Vue.js App"/>
        </div>
      </div>
    </div>
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
  width: 28%;
  border-radius: 25px;
  transition: all 1s cubic-bezier(.11,.48,.1,.49);
}

.mt:hover {
  width: 33%;
}

@media screen and (max-width: 600px) {
  .mt {
    width: 80%;
  }

  .mt:hover {
    width: 100%;
  }
}


@media screen and (min-width: 601px) and (max-width: 800px) {
  .mt {
    width: 45%;
  }

  .mt:hover {
    width: 50%;
  }
}



</style>
