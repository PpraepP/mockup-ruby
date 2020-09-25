<template>
  <div class="home">
    <Hero/>
    <Performance />
  </div>
</template>

<script>
// @ is an alias to /src
import Hero from '@/components/Hero.vue';
import Performance from '@/components/Performance.vue';

export default {
  name: 'Home',
  components: {
    Hero,
    Performance,
  },
};
</script>
