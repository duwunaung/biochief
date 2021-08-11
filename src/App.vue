<template>
  <div id="nav" v-if="menu">
    <router-link to="/">Home</router-link> |
    <router-link to="/profile">Profile</router-link>
  </div>
  <router-view />
</template>

<script>
export default {
  data() {
    return {
      menu: true,
    };
  },
  mounted() {
    if (
      window.location.pathname == "/register" ||
      window.location.pathname == "/login"
    ) {
      this.menu = false;
    }
  },
};
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

body {
  background: whitesmoke;
}
#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
