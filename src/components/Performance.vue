<template>
    <div class="Performance">
        <h2 class="text-uppercase">{{ title }}</h2>
        <div class="small-text text-uppercase">ZA11155484</div>
        <div v-for="(item, index) in progressBar" :key="index" class="progress-bar__wrapper">
          <div class="progress-bar__wrapper--header d-flex justify-content-between">
            <h5>300,125<span>.00฿</span></h5>
            <div class="small-text text-uppercase">1,200,000 ฿</div>
          </div>
          <b-progress :value="item.value" :max="item.max" class="mb-3"></b-progress>
        </div>
    </div>
</template>

<script>
export default {
  name: 'ProgressBar',
  data() {
    return {
      title: 'Sale Performance',
      progressBar: [
        { value: 40, max: 100 },
        { value: 62, max: 100 },
      ],
    };
  },
};
</script>
