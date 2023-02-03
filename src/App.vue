<template>
  <Header @tog="toggleSide"></Header>
  <Sidebar :class="open" />
  <div class="container" :class="open">
    <router-view />
  </div>
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
  padding: 4.5rem .7rem .5rem 4.8rem;
  color: #adb5bd;
  transition: padding 200ms ease-in-out;
}

.container.open {
  padding: 4.5rem .5rem .5rem 15.5rem;
  transition: padding 200ms ease-in-out;
}

.content {
  display: grid;
  grid-template-columns: repeat(1, 1fr);
  row-gap: 10px;
  justify-items: center;
}

.content-top {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 1rem;
  background-image: url('./assets/bg.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  background-attachment: fixed;
  height: 575px;
  width: 100%;
  font-size: 28px;
  font-weight: 700;
  letter-spacing: .7mm;
}

.material-symbols-outlined {
  font-variation-settings:
    'FILL' 0,
    'wght' 500,
    'GRAD' 0,
    'opsz' 48
}

::-webkit-scrollbar {
  width: 10px;
}

::-webkit-scrollbar-track {
  background: #343a40;
}

::-webkit-scrollbar-thumb {
  background: #adb5bd;
}

::-webkit-scrollbar-thumb:hover {
  background: #dee2e6;
}

@media(max-width: 620px) {
  .container {
    padding: 5rem .5rem .5rem .5rem;
  }
}
</style>
