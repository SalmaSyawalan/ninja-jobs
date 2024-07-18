<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link :to="{name: 'about'}">About</router-link> |
    <router-link :to="{name: 'jobs'}">Jobs</router-link>
  </nav>

  <button @click="redirect">Redirect</button>
  <button @click="back">Go Back</button>
  <button @click="forward">Go Forward</button>
  <router-view/>
</template>

<script>
export default {
  methods:{
    redirect(){
      this.$router.push({ name:'home' })
    },
    back(){
      this.$router.go(-1)
    },
    forward(){
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

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
  padding: 10px;
  border-radius: 10px;
}

nav a.router-link-exact-active {
  color: white;
  background: #42b983;
}

button{
  border: none;
  padding: 10px;
  border-radius: 10px;
  margin: 0px 10px;
}

button:hover{
  background: palegoldenrod;
}

</style>
