<template>
  <div class="home">
    <Hero/>
    <Process />
  </div>
</template>

<script>
// @ is an alias to /src
import Hero from '@/components/Hero.vue';
import Process from '@/components/Process.vue';

export default {
  name: 'Home',
  components: {
    Hero,
    Process,
  },
};
</script>
