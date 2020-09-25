<template>
    <header>
        <div class="container-fluid">
            <div class="row">
                <div class="col-6">
                    <div class="header__img-box">
                        <router-link to="/">
                            <b-img
                                :src="require('../assets/image/logo.png')"
                                fluid
                                alt="logo">
                            </b-img>
                        </router-link>
                    </div>
                </div>
                <div class="col-6 d-flex justify-content-end align-items-center">
                    <div class="header__hamberger">
                        <div
                        class="nav-icon3"
                        @click="activeHamburger = !activeHamburger"
                        :class="{active: activeHamburger}">
                            <span></span>
                            <span></span>
                            <span></span>
                            <span></span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </header>
</template>

<script>
export default {
  name: 'header',
  data() {
    return {
      activeHamburger: false,
    };
  },
  methods: {
  },
};
</script>

<style lang="scss" scoped>
    .header{
        &__img-box{
            max-width: 75px;
        }
        &__hamberger{
            .nav-icon3{
                position: relative;
                width: 30px;
                height: 20px;
                transform: rotate(0deg);
                transition: .5s ease-in-out;
                cursor: pointer;
                span{
                    display: block;
                    position: absolute;
                    height: 4px;
                    width: 100%;
                    background: #d3531a;
                    border-radius: 50px;
                    opacity: 1;
                    left: 0;
                    transform: rotate(0deg);
                    transition: .25s ease-in-out;
                    &:nth-child(1){ top: 0px; }
                    &:nth-child(2),
                    &:nth-child(3){  top: 8px; }
                    &:nth-child(4){ top: 16px;}
                }
                &.active{
                    span{
                        &:nth-child(1),
                        &:nth-child(4){
                            top: 8px;
                            width: 0%;
                            left: 50%;
                        }
                        &:nth-child(2){
                            transform: rotate(45deg);
                        }
                        &:nth-child(3){
                            transform: rotate(-45deg);
                        }
                    }
                }
            }

        }
    }
</style>
