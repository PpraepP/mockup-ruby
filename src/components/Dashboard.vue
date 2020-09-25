<template>
    <div class="dashboard">
        <div class="container-fluid">
            <div class="dashboard__wrapper">
                <div class="dashboard__wrapper--btn-group">
                    <b-button>Button</b-button>
                    <b-button variant="danger">Button</b-button>
                    <b-button variant="success">Button</b-button>
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
