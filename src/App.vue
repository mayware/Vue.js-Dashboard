<template>
  <nav>
    <router-link to="/">Home</router-link>
    <router-link :to="{ name: 'about' }">About</router-link>
    <router-link :to="{ name: 'jobs' }">Jobs</router-link>
  </nav>
  <router-view />

  <button @click="redirect">Redirect to Home Page</button>
  <button @click="back">Go back</button>
  <button @click="forward">Go forward</button>
</template>

<script>
export default {
  methods: {
    redirect() {
      this.$router.push({ name: 'home' })
    },
    back() {
      this.$router.go(-1)
    },
    forward() {
      this.$router.go(1)
    },
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
  background: #ced4da;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
}

nav {
  padding: 1.5rem;
  background: #212529;
  box-shadow: 0 2px 10px 0 rgb(0, 0, 0, .4);
}

nav a {
  font-weight: bold;
  color: #dee2e6;
  text-decoration: none;
  margin: .5rem;
  padding: .5rem;
  border-radius: 5px;
}

nav a.router-link-exact-active {
  color: #f8f8f8;
  background-color: #457b9d;
}

button {
  padding: .5rem;
  border: none;
  border-radius: 5px;
  background: #00754a;
  color: #dee2e6;
  cursor: pointer;
  margin: .1rem;
}
</style>
