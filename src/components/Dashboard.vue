<template>
    <div class="dashboard">
        <div class="container-fluid">
            <h3 class="text-uppercase">Dashboard</h3>
            <div class="dashboard__wrapper">
                <div class="dashboard__wrapper--btn-group">
                    <b-button class="blue">
                        <b-icon icon="shift" aria-hidden="true"></b-icon>
                        เข้าเยี่ยม
                    </b-button>
                    <b-button class="yellow">
                        <b-icon icon="cart4" aria-hidden="true"></b-icon>
                        ตามขาย
                    </b-button>
                    <b-button class="green">
                        <b-icon icon="telephone" aria-hidden="true"></b-icon>
                        โทรนัด
                    </b-button>
                </div>
                <div class="dashboard__wrapper--chart">
                    <bar-chart></bar-chart>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import BarChart from '@/components/Chart.vue';

export default {
  name: 'Dashboard',
  components: { BarChart },
};
</script>

<style lang="scss" scoped>
@import '../styles/main';
.dashboard{
    h3{ margin-bottom: 16px; }
    @include media-breakpoint-down(sm){
        h3{ font-size: 16px;}
    }
    &__wrapper{
        &--btn-group{
            margin-bottom: 20px;
            @include flexbox();
            @include justify-content(center);
            @include flex-wrap(wrap);
            button{
                border-radius: 12px;
                border: none;
                font-size: 14px;
                padding: 0 20px;
                height: 32px;
                margin-bottom: 15px;
                @include flexbox();
                @include align-items(center);
                &:not(:last-child){ margin-right: 15px; }
                svg{ margin-right: 8px;}
                &.blue{ background-color: #4b8fe0;}
                &.yellow{ background-color: #f5a623;}
                &.green{ background-color: #51e2c1;}
            }
        }
    }
}
</style>
