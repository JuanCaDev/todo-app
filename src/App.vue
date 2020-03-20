<template>
  <div id="app">
    <Logo />
    <Navigation />
    <router-view />
  </div>
</template>

<script>
import Logo from '@/components/Logo';
import Navigation from '@/components/Navigation';

export default {
  components: {
    Logo,
    Navigation
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
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
