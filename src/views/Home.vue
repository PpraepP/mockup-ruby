<template>
  <div class="home">
    <Hero/>
    <Process />
    <Dashboard/>
  </div>
</template>

<script>
// @ is an alias to /src
import Hero from '@/components/Hero.vue';
import Process from '@/components/Process.vue';
import Dashboard from '@/components/Dashboard.vue';

export default {
  name: 'Home',
  components: {
    Hero,
    Process,
    Dashboard,
  },
};
</script>
