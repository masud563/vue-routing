<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> |
    <router-link :to="{name: 'Jobs'}">Jobs</router-link>
  </div>

  <button @click="redirect">Redirect</button>
  <button @click="goBack">Go back</button>
  <button @click="goForward">Go forward</button>
  <router-view/>
</template>

<script>
  export default {
    methods: {
      redirect() {
        this.$router.push({name: 'Home'})
      },

      goBack() {
        this.$router.go(-1)
      },

      goForward() {
        this.$router.go(1)
      }
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

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
}

#nav a.router-link-exact-active {
  color: white;
  background-color: crimson;
  padding: 8px;
  border-radius: 5px;
  text-decoration: none;
}

button {
  padding: 10px;
  margin: 0 10px;
  background-color: #eee;
  border: none;
  border-radius: 5px;
}
</style>
