<template>
        <b-navbar variant="faded" type="light">
            <div class="navbar__list" v-for="(item, index) in menu" :key="index">
                <b-icon :icon="item.icon"></b-icon>
                <b-navbar-brand href="#">{{ item.title}}</b-navbar-brand>
            </div>
        </b-navbar>
</template>

<script>
export default {
  name: 'Navbar',
  data() {
    return {
      menu: [
        { title: 'ภาพรวม', icon: 'file-earmark' },
        { title: 'รายการซื้อขาย', icon: 'cart3' },
        { title: 'ความคืบหน้า', icon: 'calendar3-week' },
        { title: 'การเข้าเยี่ยม', icon: 'people' },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
    @import '../styles/main';
    .navbar{
        display: none;
        position: sticky;
        bottom: 0;
        background-color: #f9f9f9;
        padding: 10px 0 0;
        border-top: 1px solid #A3A5A7;
        @include align-items(baseline);
        @include justify-content(center);
        @include flex-wrap(wrap);
        @include media-breakpoint-down(md){
            @include flexbox();
        }
        &-brand{
            font-size: 10px;
            margin: 0;
            color: #A3A5A7;
        }
        &__list{
            position: relative;
            width: 98px;
            @include flexbox();
            @include flex-flow(column);
            @include align-items(center);
            @include justify-content(center);
            &:not(:last-child){
                &:after{
                    content: '';
                    position: absolute;
                    right: 0;
                    top: 8px;
                    width: 1px;
                    height: 20px;
                    background-color: #A3A5A7;
                }
            }
            svg{
                width: 22px;
                height: 22px;
                color: #A3A5A7;
            }
        }
    }
</style>
