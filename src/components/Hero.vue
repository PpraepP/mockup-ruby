<template>
    <div class="hero">
        <div
        class="hero__bg-img"
        :style="{ 'background-image': 'url('+ imageBackground +')' }">
        </div>
        <div class="container-fluid">
            <div class="row">
                <div class="col-12 col-lg-3">
                    <div class="hero__body">
                        <div class="hero__body--img">
                            <b-img-lazy
                            v-bind="mainProps"
                            :src="image"
                            fluid alt="Image 1">
                            </b-img-lazy>
                        </div>
                        <b-button>
                            <b-icon icon="exclamation-circle" variant="light"></b-icon>
                        </b-button>
                    </div>
                </div>
                <div class="col align-self-center">
                    <div class="hero__content">
                        <div class="small-text text-uppercase">ZA11155484</div>
                        <h1 class="text-uppercase">cooking with the power of sun</h1>
                        <p>{{ heroContent }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
  name: 'Hero',
  data() {
    return {
      mainProps: {
        center: true,
        fluidGrow: true,
        blank: true,
        class: 'w-100',
      },
      imageBackground: 'https://images.pexels.com/photos/21014/pexels-photo.jpg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260',
      image: 'https://images.pexels.com/photos/5202011/pexels-photo-5202011.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260',
      heroContent: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque lobortis, lectus ac sodales iaculis, nisl erat eleifend leo, pulvinar vehicula eros tortor ac erat. Proin imperdiet magna et convallis dignissim.',
    };
  },
};
</script>
<style lang="scss" scoped>
    @import '../styles/main';
    .hero{
        position: relative;
        &__bg-img{
            position: relative;
            background-repeat: no-repeat;
            background-size: cover;
            background-position: center;
            min-height: 315px;
            height: 100%;
            margin-bottom: 30px;
            &:after{
                content: '';
                position: absolute;
                bottom: 0;
                width: 100%;
                height: 20%;
                background: linear-gradient(to bottom, rgba(255,0,0,0) 20%, rgba(white,0.8) 140%);
            }
        }
        &__body{
            position: relative;
            text-align: left;
            @include flexbox();
            @include align-items(flex-end);
            &--img{
                max-width: 285px;
                margin-right: 20px;
                img{
                    border-radius: 12px;
                }
            }
            button{
                position: relative;
                top: -18px;
                left: 11px;
                border-radius: 50px;
                min-width: 60px;
                height: 60px;
                padding: 0;
                background-color: #4b8ee6;
                border: none;
                @include flexbox();
                @include align-items(center);
                @include justify-content(center);
                svg{
                    width: 24px;
                    height: 24px;
                }
            }
            @include media-breakpoint-down(md){
                margin: -180px 0 26px;
            }
        }
        &__content{
            h1{
                font-size: 36px;
                font-weight: 400;
                margin-bottom: 18px;
            }
            p{ margin-bottom: 0; }
            @include media-breakpoint-down(md){
                border-bottom: 1px solid #A3A5A7;
                .small-text{ margin-bottom: 7px; }
                h1{ font-size: 26px; }
                p{
                    font-size: 11px;
                    line-height: 18px;
                    margin-bottom: 40px;
                }
            }
        }
    }
</style>
