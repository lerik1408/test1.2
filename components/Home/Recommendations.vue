<template>
  <div class="conteiner">
    <section class="info">
      <div class="info-platform">
        <h3 class="info-headline">Trusted by 800+ agencies and blogers, featured at:</h3>
        <div class="companies">
          <div class="companies-item twitch">
              
          </div>
          <div class="companies-item hulu">
              
          </div>
          <div class="companies-item primevideo">
              
          </div>
          <div class="companies-item sling">
              
          </div>
          <div class="companies-item xbox">
              
          </div>
          <div class="companies-item youtube">
              
          </div>
        </div>
      </div>
      <div class="social">
        <div class="google">
        </div>
        <div class="social-rating">
          <p>{{google.rating}}</p>
          <IconStar v-for="n in Math.ceil(google.rating)" :key="n" />
        </div>
        <div class="social-reviews">
          <p>{{google.reviews}} reviews</p>
        </div>
      </div>
      <div class="social">
        <div class="facebook">
        </div>
        <div class="social-rating">
          <p>{{facebook.rating}}</p>
          <IconStar v-for="n in Math.ceil(facebook.rating)" :key="n" />
        </div>
        <div class="social-reviews">
          <p>{{facebook.reviews}} reviews</p>
        </div>
      </div>
    </section>
    <section class="text">
      <div class="text-wrap">
        <h3><span>1,000</span>s of engagements generated every day</h3>
        <p>See examples of <span>real</span> comments generated from customers’ Sprizzy promotions.</p>
      </div>
    </section>
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
        :perPageCustom="[[300, 1], [700, 2], [1366, 3]]"
      >
      <slide v-for="item in data" :key="item.id" class="slide">
        <div class="slide-padding">
          <div class="slide-content">
            <div class="slide-wrap">
              <img :src="item.img" alt="user photo" class="slide-photo">
              <div class="text">
                <p class="text-name">{{item.name}}</p>
                <p class="text-time">{{item.time}}</p>
                <p class="text-text">{{item.text}}</p>
              </div>
            </div>
            <div class="slide-control">
              <p>{{item.comments}}</p>
              <IconComments />
              <IconMore />
            </div>
            <div class="slide-youtube">
              View on <IconYoutube class="slide-youtube--icon"/>Youtube
            </div>
          </div>
        </div>
      </slide>
    </carousel>
  </div>
</template>

<script>
// import { Carousel, Slide } from 'vue-carousel';
import IconComments from '@/components/icons/IconComments.vue';
import IconMore from '@/components/icons/IconMore.vue';
import IconYoutube from '@/components/icons/IconYoutube-red.vue';
import IconStar from '@/components/icons/IconStar-blue.vue';
export default{
  components: {
    IconComments,
    IconMore,
    IconYoutube,
    IconStar,
  },
  data() {
      return {
        data: [
          {
            id: 1,
            img: 'https://www.placecage.com/200/300',
            name: 'Mr. Ludophobia',
            time: '3 month ago',
            text: 'The one ad I don’t regret clicking one! Nice video dude!',
            comments: 1,
          },
          {
            id: 2,
            img: 'https://www.placecage.com/200/300',
            name: 'Mr. Ludophobia',
            time: '3 month ago',
            text: 'The one ad I don’t regret clicking one! Nice video dude!',
            comments: 2,
          },
          {
            id: 3,
            img: 'https://www.placecage.com/200/300',
            name: 'Mr. Ludophobia',
            time: '3 month ago',
            text: 'The one ad I don’t regret clicking one! Nice video dude!',
            comments: 1,
          },
          {
            id: 4,
            img: 'https://www.placecage.com/200/300',
            name: 'Mr. Ludophobia',
            time: '3 month ago',
            text: 'The one ad I don’t regret clicking one! Nice video dude!',
            comments: 2,
          },
          {
            id: 5,
            img: 'https://www.placecage.com/200/300',
            name: 'Mr. Ludophobia',
            time: '3 month ago',
            text: 'The one ad I don’t regret clicking one! Nice video dude!',
            comments: 1,
          },
          {
            id: 6,
            img: 'https://www.placecage.com/200/300',
            name: 'Mr. Ludophobia',
            time: '3 month ago',
            text: 'The one ad I don’t regret clicking one! Nice video dude!',
            comments: 2,
          },
        ],
        google: {
          rating: '4.8',
          reviews: '47',
        },
        facebook: {
          rating: '4.7',
          reviews: '88',
        }
      };
    },
}
</script>

<style lang="scss" scoped>
.conteiner{
  margin-top: 90px;
}
.info{
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  margin-bottom: 60px;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  @include for-desktop {
    flex-direction: row;
  }
  .info-platform {
    display: flex;
    flex-direction: column;
    align-items: center;
    .info-headline {
      font-weight: 800;
      font-size: 24px;
      @include for-mobile {
        width: 80%;
      }
    }
    .companies {
      display: flex;
      justify-content: center;
      height: 60px;
      @include for-mobile {
        flex-wrap: wrap;
        margin-bottom: 100px
      }
      .companies-item {
        width: 76px;
        height: 60px;
        margin-left: 20px;
        flex-basis: 33%;
      }
      .twitch {
        background: url("~@/assets/img/twitch.png") no-repeat center;
        margin-left: 0px;
      }
      .hulu {
        background: url("~@/assets/img/hulu.png") no-repeat center;
      }
      .primevideo {
        background: url("~@/assets/img/primevideo.png") no-repeat center;
      }
      .sling {
        background: url("~@/assets/img/sling.png") no-repeat center;
      }
      .xbox {
        background: url("~@/assets/img/xbox.png") no-repeat center;
      }
      .youtube {
        background: url("~@/assets/img/youtube.png") no-repeat center;
      }
    }
  }
  .social {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-left: 0;
    margin-top: 20px;
    @include for-desktop {
      margin-left: auto;
    }
    .google {
      width: 180px;
      height: 60px;
      background: url("~@/assets/img/google.png") no-repeat
    }
    .facebook {
      width: 180px;
      height: 60px;
      background: url("~@/assets/img/facebook.png") no-repeat center;
    }
    .social-rating {
      display: flex;
      align-items: center;
      align-self: center;
      @include for-desktop {
        align-self: flex-end;
      }
      p {
        margin-right: 10px;
        font-size: 26px;
        color: #2A3247;
      }
    }
    .social-reviews {
      align-self: center;
      @include for-desktop {
        align-self: flex-end;
      }
    }
  }
}
.text {
  display: flex;
  justify-content: flex-end;
  .text-wrap {
    width: 60%;
    height: 500px;
    padding: 40px;
    background-color: #F7FAFD;
    border-radius: 107px 0 0 107px;
    @include for-mobile{
      width: 90%;
      height: 350px;
    }
    @include for-desktop {
      padding-top: 85px;
      padding-left: 200px;
    }
    h3 {
      line-height: 80px;
      font-size: 56px;
      @include for-mobile{
        font-size: 24px;
        line-height: 40px;
      }
      @include for-tablet{
        line-height: 60px;
      }
      span {
        color:#3074E4;
      }
    }
    p {
      font-size: 20px;
      span {
        font-weight: 900;
      }
    }
  }
}
.carousel {
  top: -100px;
  .slide-padding {
    height: 190px;
    border-radius: 20px;
    box-shadow: 0px 0px 6px 5px rgba(22, 34, 78, 0.06);
    margin: 10px 10px;
    box-sizing: border-box;
    @include for-mobile {
      margin-bottom: 20px;
    }
    @include for-tablet {
      margin-bottom: 30px;
    }
    @include for-desktop {
      margin-bottom: 55px;
    }
    .slide-content{
      padding: 25px 35px;
      height: 100%;
      display: flex;
      justify-content: space-around;
      flex-direction: column;
      .slide-photo {
        width: 46px;
        height: 46px;
        border-radius: 50%;
      }
      .slide-wrap {
        display: flex;
        justify-content: space-around;
        .text {
          width: calc(100% - 46px - 10px);
          display: flex;
          flex-wrap: wrap;
          .text-name {
            width: 50%;
            font-weight: 700;
          }
          .text-time {
            width: 50%;
            color: #939DB6;
          }
          .text-text {
            margin-top: 5px
          }
        }
      }
      .slide-control {
        width: 100%;
        display: flex;
        justify-content: space-around;
      }
      .slide-youtube {
        .slide-youtube--icon {
          margin: 0 10px;
        }
      }
    }
  }
  @include for-mobile{
    top: 10px;
    width: 90%;
    margin: 0 auto;
  }
  @include for-tablet {
    top: 50px;
  }
  @include for-desktop {
    max-width: 1460px;
    margin: 0 auto;
  }
}
</style>
