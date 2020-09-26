<template>
  <div id="app">
    <Header/>
    <router-view/>
    <Navbar/>
  </div>
</template>

<script>
import Header from '@/components/Header.vue';
import Navbar from '@/components/Navbar.vue';

export default {
  components: {
    Header,
    Navbar,
  },
};
</script>

<style lang="scss">
@import 'styles/main';
#app {
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
