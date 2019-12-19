<template>
  <section>
    <div class="slider">
      <carousel
        class="carousel"
        paginationColor="#E8EAF4"
        paginationActiveColor="#649DFB"
        :loop="true"
        :autoplay="true"
        :autoplayHoverPause="true"
        :speed="2000"
        :autoplayTimeout="4000"
        :paginationPadding="4"
        :paginationSize="17"
        :scrollPerPage="true"
        :perPageCustom="[[300, 2], [700, 2], [1366, 2]]"
      >
        <slide v-for="(item, i) in reviews" :key="i" class="slide">
          <div class="slider-text">
            <h3>{{item.title}}</h3>
            <p>{{item.description}}</p>
          </div>
          <div class="slide-background">
            <div class="message">
              <img :src="item.user.photo" alt="user" class="message-photo">
              <div class="message-content">
                <p class="message-text">
                  {{item.user.message}}
                </p>
                <p class="message-time">
                  {{item.user.time}}
                </p>
              </div>
            </div>
          </div>
        </slide>
      </carousel>
    </div>
    <div class="info">
      <div class="info-content">
        <h3 class="info-headline">Better than buying stuff</h3>
        <p class="info-text">
          When you buy followers or likes, you risk getting spammed, wasting your money as IG deletes suspicious activities. 
          <br />
          You may even end up getting banned.
        </p>
        <p class="info-text">
          With Sprizzy you are safe. We’ve helped 10,000+ brands ainfluencers gain millions of followers.
        </p>
        <router-link to="" class="info-link">Start My Video Promotion Now</router-link>
      </div>
    </div>
  </section>
</template>

<script>
export default{
  data() {
    return {
      reviews: [
        {
          title: 'Paid Staff',
          description:'Useless likes & comments',
          user: {
            photo: 'https://www.placecage.com/200/300',
            message: 'Lolololo 1111111!!!',
            time: '5 minutes ago',
          }
        },
        {
          title: 'Sprizzy',
          description:'Meaningful engagements',
          user: {
            photo: 'https://www.placecage.com/200/300',
            message: 'I realy like your content! Keep it up!',
            time: '2 minutes ago',
          }
        },
        {
          title: 'Paid Staff',
          description:'Useless likes & comments',
          user: {
            photo: 'https://www.placecage.com/200/300',
            message: 'Lolololo 1111111!!!',
            time: '5 minutes ago',
          }
        },
        {
          title: 'Sprizzy',
          description:'Meaningful engagements',
          user: {
            photo: 'https://www.placecage.com/200/300',
            message: 'I realy like your content! Keep it up!',
            time: '2 minutes ago',
          }
        },
        {
          title: 'Paid Staff',
          description:'Useless likes & comments',
          user: {
            photo: 'https://www.placecage.com/200/300',
            message: 'Lolololo 1111111!!!',
            time: '5 minutes ago',
          }
        },
        {
          title: 'Sprizzy',
          description:'Meaningful engagements',
          user: {
            photo: 'https://www.placecage.com/200/300',
            message: 'I realy like your content! Keep it up!',
            time: '2 minutes ago',
          }
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
section {
  display: flex;
  flex-direction: column;
  @include for-desktop {
    flex-direction: row;
  }
  .slider {
    border-radius: 0px 107px 0px 0px;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100vw;
    height: 500px;
    background-color: #F7FAFD;
    // .VueCarousel-pagination { text-align: left; }
    @include for-desktop {
      width: 50vw;
    }
    @include for-mobile {
      height: 348px;
    }
    .carousel {
      width: 50%;
      min-width: 600px;
      @include for-mobile {
        min-width: 300px;
        width: 90%;
      }
      .slide{
        &:nth-child(odd) {
          @include for-tablet{
            .slide-background{
              background: url("~@/assets/img/BetterBackground/1.png") no-repeat center;
            }
          }
          @include for-mobile{
            .slide-background{
              background: url("~@/assets/img/BetterBackground/1_mobile.png") no-repeat center;
            }
          }
          .slider-text {
            &::before {
              background-image: url("~@/assets/img/BetterBackground/ellipse-red.png") ,url("~@/assets/img/BetterBackground/path.png");
              background-repeat: no-repeat;
              background-position: top center, center;
            }
            p {
              color: #FF6C73;
            }
            h3 {
              color: #FF6C73;
            }
          }
        }
        &:nth-child(even) {
          @include for-tablet{
            .slide-background {
              background: url("~@/assets/img/BetterBackground/2.png") no-repeat center;
            }
          }
          @include for-mobile {
            .slide-background {
              background: url("~@/assets/img/BetterBackground/2_mobile.png") no-repeat center;
            }
          }
          .slider-text {
            &::before {
              background-image: url("~@/assets/img/BetterBackground/ellipse-green.png") ,url("~@/assets/img/BetterBackground/path.png");
              background-repeat: no-repeat;
              background-position: top center, center;
            }
            p {
              color: #23D98C;
            }
            h3 {
              color: #23D98C;
            }
          }
        }
      }
      .slide {
        padding-right: 50px;
        box-sizing: padding-box;
        @include for-mobile {
          padding: 0 5px;
          display: flex;
          flex-direction: column;
          align-items: center;
        }
        .slider-text {
          position: relative;
          height: 100px;
          display: flex;
          flex-direction: column;
          align-items: center;
          @include for-mobile {
            width: 166px;
            align-items: flex-end;
          }
          @media screen and (max-width: 384px){
            width: 100%;
          }
          h3 {
            width: 120px;
            font-weight: 800;
            font-size: 24px;
            @include for-mobile{
              font-size: 18px;
            }
          }
          p {
            width: 120px;
            margin-top: 10px;
            @include for-mobile {
              font-size: 14px;
            }
          }
          &::before{
            content: '';
            position: absolute;
            top: 0;
            left: 30px;
            display: block;
            width: 18px;
            height: 100px;
            @include for-mobile {
              left: 9px;
            }
            @media screen and (max-width: 384px){
              left: 4px;
            }
          }
        }
        .slide-background {
          display: flex;
          justify-content: center;
          align-items: flex-end;
          width: 100%;
          height: 240px;
          border-radius: 20px;
          background-size: cover;
          @include for-mobile {
            // width: 100%;
            background-size: contain;
            width: 166px;
            height: 162px;
          }
          @media screen and (max-width: 384px){
            width: 100%;
          }
          .message {
            width: 80%;
            display: flex;
            height: 66px;
            padding: 10px 25px;
            background-color: #fff;
            margin-bottom: 20px;
            border-radius: 10px;
            box-shadow: 0px 10px 40px rgba(22, 34, 78, 0.06);
            @include for-mobile {
              // padding: 10px 10px;
              padding: 0;
              padding-left: 7px;
              align-items: center;
            }
            .message-photo {
              width: 38px;
              height: 38px;
              border-radius: 50%;
              @include for-mobile {
                width: 25px;
                height: 25px;
              }
            }
            .message-content{
              display: flex;
              flex-direction: column;
              justify-content: center;
              margin-left: 10px;
              @include for-mobile {
                display: block;
                margin-left: 4px;
              }
              .message-text{
                font-size: 10px;
                margin-bottom: 5px;
                @include for-mobile {
                  font-size: 8px;
                  margin-bottom: 0;
                }
              }
              .message-time{
                font-size: 10px;
                color: #939DB6;
                @include for-mobile {
                  font-size: 8px;
                }
              }
            }
          }
        }
      }
    }
  }
  .info {
    display: flex;
    justify-content: center;
    margin-bottom: 20px;
    min-width: 600px;
    order: -1;
    @include for-desktop {
      order: 2;
      margin-bottom: 0;
    }
    @include for-mobile {
      min-width: 300px;
    }
    .info-content {
      width: 100%;
      padding: 20px;
      @include for-desktop {
        width: 460px;
        padding: 0;
      }
      .info-headline {
        font-size: 36px;
        font-weight: 800;
        color: #282C46;
        margin-bottom: 30px;
        @include for-mobile {
          font-size: 24px;
          margin-bottom: 10px
        }
      }
      .info-text {
        font-weight: 300;
        font-size: 20px;
        line-height: 184%;
        margin-bottom: 20px;
        @include for-mobile {
          font-size: 14px;
        }
      }
      .info-link {
        color: #23D98C;
        margin-top: 50px;
      }
    }
  }
}
</style>
