<template>
    <div class="process">
      <div class="container-fluid">
        <div class="row">
          <div class="col-6">
            <div class="process__performance">
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
          </div>
          <div class="col-6">
            <div class="process__status">
              <div class="process__status--header d-flex">
                <h3>Status</h3>
                <div class="small-text text-uppercase">Contruction</div>
              </div>
              <Status/>
            </div>
          </div>
        </div>
      </div>

    </div>
</template>

<script>
import Status from '@/components/Status.vue';

export default {
  name: 'Process',
  components: {
    Status,
  },
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

<style lang="scss" scoped>
 .status{
   position: relative;
   &:after{
     content: '';
     position: absolute;
    top: 0;
    left: 70px;
    height: 100%;
    border-left: 6px dotted #e9ecef;
    z-index: -1;
   }
 }
</style>
