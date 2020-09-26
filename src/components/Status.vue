<template>
    <div class="status">
        <div class="status__list">
            <div class="status__list--icon">
                <div class="status__list--icon-wrapper">
                    <b-icon icon="building" variant="secondary"></b-icon>
                </div>
            </div>
            <div class="small-text text-uppercase">Early Finish</div>
        </div>
        <div class="status__main d-flex">
            <radial-progress-bar
            class="status__main--progress"
            :diameter="90"
            :completed-steps="completedSteps"
            :total-steps="totalSteps"
            :innerStrokeColor="innerStrokeColor"
            :startColor="startColor"
            :stopColor="stopColor">
                <p>{{ completedSteps }}<span>%</span></p>
            </radial-progress-bar>
            <div class="status__main--content d-flex">
                <div>
                    <div class="small-text text-uppercase">03 | Single house</div>
                    <div class="small-text text-uppercase">Fin : 12/11/30</div>
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
            <div class="small-text text-uppercase">35 Days</div>
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
<style lang="scss">
    @import '../styles/main';
    .status{
        position: relative;
        &:after{
            content: '';
            position: absolute;
            top: 0;
            left: 42px;
            height: 100%;
            border-left: 3px dotted #e9ecef;
            z-index: -1;
        }
        &__list{
            @include flexbox();
            @include align-items(center);
            .smal-text{ margin-left: 9px;}
            &--icon{ width: 90px; }
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
            @include media-breakpoint-down(sm){
                &--icon-wrapper{
                    width: 35px;
                    height: 35px;
                }
            }
        }
        &__main{
            position: relative;
            margin: 20px 0;
            @include align-items(center);
            &:after{
                content: '';
                position: absolute;
                background-color: #e9ecef;
                right: 0;
                width: calc(100% - 42px);
                height: calc(100% - 10px);
                padding: 0 15px;
                border-radius: 0px 12px 12px 0px;
                z-index: -1;
            }
            &--progress{
                height: 140px;
                .radial-progress-inner{
                    width: 85px;
                    height: 60px;
                }
                .radial-progress-bar{
                    circle{ stroke-width: 6px !important; }
                }
                p{
                    font-size: 28px;
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
            @include media-breakpoint-down(sm){
                &--progress{
                    // width: 70px !important;
                    // height: 70px !important;
                }
            }
        }
    }
</style>
