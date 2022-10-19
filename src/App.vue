<template>
  <nav class="ui fixed top inverted menu">
    <router-link class="item" to="/">
      <i class="home icon" />Home</router-link> 
    <router-link class="item" to="/bye">Bye</router-link> 
    <router-link class="item" to="/about">About</router-link>
  </nav>
  <div class="pad">
    <router-view :todo="todo" @addItem="addItem"/>
  </div>
</template>

<script type="text/javascript">

import { db } from './firebase.js'
import { ref, set, onValue } from 'firebase/database'

export default {
  name: 'HomeView',
  data () {
    return {
      todo: []
    }
  },
  methods: {
    addItem (item) {
      this.todo.push(item)
      set(ref(db, 'todo', this.todo).then(() => {
          console.log('todo updated!')
        })
      )
    }
  },
  mounted () {
    const vm = this
    onValue(ref(db, 'todo'), (snapshot) => {
      const data = snapshot.val()
      vm.todo = data
      // vm.logged('wdpXGWEUObY7miKsK5hH5qDjkJ43', 'bestian@gmail.com')
    })
  }
}
</script>

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
