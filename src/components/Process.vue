<template>
    <div class="process">
      <div class="container-fluid">
        <div class="row">
          <div class="col-12 col-md-6">
            <div class="process__performance">
              <h3 class="text-uppercase">{{ title }}</h3>
              <div class="small-text text-uppercase">Gross sale / Opra</div>
              <div class="process__performance--wrapper">
                <div v-for="(item, index) in progressBar"
                :key="index"
                class="process--box">
                  <div class="header d-flex justify-content-between">
                    <h5>300,125<span>.00฿</span></h5>
                    <div class="small-text text-uppercase">1,200,000 ฿</div>
                  </div>
                  <b-progress :value="item.value" :max="item.max" class="mb-3"></b-progress>
                </div>
              </div>
            </div>
          </div>
          <div class="col">
            <div class="process__status">
              <div class="process__status--header d-flex justify-content-between">
                <h3 class="text-uppercase">Status</h3>
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

<style lang="scss">
@import '../styles/main';
.process{
  padding: 27px 0;
  h3{
    margin-bottom: 30px;
    }
    @include media-breakpoint-down(sm){
      h3{ font-size: 16px;}
    }
  &__performance{
    .small-text { margin-bottom: 20px;}
    &--wrapper{
      .process--box{
        &:not(:last-child){ margin-bottom: 40px;}
        &:first-of-type{
          .progress-bar{ background-color: #51e4c1; }
        }
        &:last-of-type{
          .progress-bar{ background-color: #f5a721; }
        }
      }
      .header{
        h5{
          margin-bottom: 18px;
          span{ font-size: 12px; }
        }
      }
    }
    @include media-breakpoint-down(sm){
      padding-right: 30px;
      padding-bottom: 25px;
      border-bottom: 1px solid #A3A5A7;
      .progress{
        height: 9px;
      }
    }
  }
  &__status{
    @include media-breakpoint-down(sm){
      border-bottom: 1px solid #A3A5A7;
      padding: 25px 54px 28px 0;
    }
  }
}
</style>
