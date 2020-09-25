<template>
    <div class="status">
        <div class="status__list">
            <div class="status__list--icon">
                <div class="status__list--icon-wrapper">
                    <b-icon icon="building" variant="secondary"></b-icon>
                </div>
            </div>
            <div class="small-text text-uppercase">ZA11155484</div>
        </div>
        <div class="status__main d-flex">
            <radial-progress-bar
            class="status__main--progress"
            :diameter="150"
            :completed-steps="completedSteps"
            :total-steps="totalSteps"
            :innerStrokeColor="innerStrokeColor"
            :startColor="startColor"
            :stopColor="stopColor">
                <p>{{ completedSteps }}<span>%</span></p>
            </radial-progress-bar>
            <div class="status__main--content d-flex">
                <div>
                    <div class="small-text text-uppercase font-weight-bold">ZA11155484</div>
                    <div class="small-text text-uppercase">ZA11155484</div>
                </div>
                <b-icon icon="bricks" variant="secondary"></b-icon>
            </div>
        </div>
        <div class="status__list">
            <div class="status__list--icon">
                <div class="status__list--icon-wrapper">
                    <b-icon icon="cloud-check-fill" variant="secondary"></b-icon>
                </div>
            </div>
            <div class="small-text text-uppercase">ZA11155484</div>
        </div>
    </div>

</template>

<script>
import RadialProgressBar from 'vue-radial-progress';

export default {
  data() {
    return {
      completedSteps: 40,
      totalSteps: 100,
      innerStrokeColor: '#bad6f2',
      startColor: '#007bff',
      stopColor: '#007bff',
    };
  },
  components: {
    RadialProgressBar,
  },
};
</script>
<style lang="scss" scoped>
    @import '../styles/main';
    .status{
        &__list{
            @include flexbox();
            @include align-items(center);
            @include justify-content(space-between);
            &--icon{ width: 150px; }
            &--icon-wrapper{
                width: 50px;
                height: 50px;
                margin: auto;
                background: #e9ecef;
                border-radius: 50px;
                @include flexbox();
                @include align-items(center);
                @include justify-content(center);
            }
        }
        &__main{
            position: relative;
            @include align-items(center);
            &:after{
                content: '';
                position: absolute;
                background-color: #e9ecef;
                right: 0;
                width: calc(100% - 75px);
                height: calc(100% - 10px);
                padding: 0 15px;
                border-radius: 0px 80px 80px 0px;
                z-index: -1;
            }
            &--progress{
                height: 140px;
                p{
                    font-size: 35px;
                    color: #007bff;
                    margin: 0;
                    span{ font-size: 14px; }
                }
            }
            &--content{
                width: 100%;
                padding: 0 25px 0 15px;
                @include align-items(center);
                @include justify-content(space-between);
                svg{
                    width: 30px;
                    height: 30px;
                }
            }
        }
    }
</style>
