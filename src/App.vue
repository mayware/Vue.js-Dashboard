<template>
  <Header @tog="toggleSide"></Header>
  <Sidebar :class="open" />
  <router-view />
</template>

<script>
import Header from './components/Header.vue'
import Sidebar from './components/Sidebar.vue'
export default {
  data() {
    return {
      open: ''
    }
  },
  components: {
    Header,
    Sidebar
  },
  methods: {
    // redirect buttons
    redirect() {
      this.$router.push({ name: 'home' })
    },
    back() {
      this.$router.go(-1)
    },
    forward() {
      this.$router.go(1)
    },
    // 
    // sidebar toggler function
    toggleSide() {
      if (this.open == '') {
        this.open = 'open'
      } else {
        this.open = ''
      }
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background: #101010;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
}

.container {
  flex-direction: column;
  padding: 5rem .5rem .5rem 5rem;
  color: #adb5bd;
  transition: padding 200ms ease-in-out;
}

.material-symbols-outlined {
  font-variation-settings:
    'FILL' 0,
    'wght' 500,
    'GRAD' 0,
    'opsz' 48
}
</style>
