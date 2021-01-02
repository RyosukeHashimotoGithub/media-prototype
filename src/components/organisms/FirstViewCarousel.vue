<template>
  <swiper
    class="swiper py-6"
    :options="swiperOption"
    @click-slide="handleClickSlide"
    style="position: relative;"
  >
    <swiper-slide v-for="index in 12" :key="index">
      <v-card elevation="4" rounded="xl">
        <a href="#">
          <v-img
            src="../../assets/image.jpg"
            aspect-ratio="1"
            elevation="6"
            rounded="xl"
            class="rounded-xl elevation-6"
            style="position: relative;"
          >
            <div
              class="font-weight-bold white--text mr-6"
              style="position: absolute; right: 0; bottom: 0;"
            >
              <h2 style="font-size: 48px; line-height: 48px;">
                "HAKOIRI"
              </h2>
              <p style="font-size: 32px; line-height: 32px;">
                Historical Cars
              </p>
            </div>
          </v-img>
        </a>

        <v-card-text class="py-6 px-0">
          <v-container class="pa-0">
            <v-row no-gutters class="mx-4">
              <v-col v-for="n in 4" :key="`thumbs-${n}`" class="pa-0">
                <a href="#">
                  <v-img
                    src="../../assets/image.jpg"
                    aspect-ratio="4/3"
                    height="40"
                    contain
                  ></v-img>
                </a>
              </v-col>
              <v-col class="pa-0" style="position: relative;">
                <a href="#">
                  <v-img
                    src="../../assets/image.jpg"
                    aspect-ratio="4/3"
                    height="40"
                    contain
                    style="filter: blur(2px);"
                  ></v-img>
                  <p
                    class="font-weight-bold white--text"
                    style="position: absolute; top: 50%; left: 50%; transform: translateY(-50%) translateX(-50%);
  -webkit- transform: translateY(-50%) translateX(-50%); z-index: 5;"
                  >
                    +18
                  </p>
                </a>
              </v-col>
            </v-row>
          </v-container>
        </v-card-text>
      </v-card>
    </swiper-slide>

    <div class="swiper-pagination" slot="pagination"></div>
    <div
      class="swiper-button-prev swiper-navigation-btn"
      slot="button-prev"
    ></div>
    <div
      class="swiper-button-next swiper-navigation-btn"
      slot="button-next"
    ></div>
  </swiper>
</template>

<script>
import Vue from "vue";
import {
  Swiper as SwiperClass,
  Pagination,
  Mousewheel,
  Autoplay,
  Navigation,
} from "swiper/swiper.esm";
import getAwesomeSwiper from "vue-awesome-swiper/dist/exporter";
SwiperClass.use([Pagination, Mousewheel, Autoplay, Navigation]);
Vue.use(getAwesomeSwiper(SwiperClass));
const { Swiper, SwiperSlide } = getAwesomeSwiper(SwiperClass);
import "swiper/swiper-bundle.css";
import "swiper/components/pagination/pagination.min.css";

export default {
  name: "FirstViewCarousel",
  components: {
    Swiper,
    SwiperSlide,
  },
  data() {
    return {
      swiperOption: {
        slidesPerView: 1.1,
        spaceBetween: 12,
        centeredSlides: true,
        loop: true,
        // autoplay: {
        //   delay: 5000
        // },
        pagination: {
          el: ".swiper-pagination",
          type: "progressbar",
        },
        navigation: {
          nextEl: ".swiper-button-next",
          prevEl: ".swiper-button-prev",
        },
        breakpoints: {
          768: {
            slidesPerView: 3,
            spaceBetween: 12,
          },
          640: {
            slidesPerView: 2.2,
            spaceBetween: 12,
          },
          320: {
            slidesPerView: 1.1,
            spaceBetween: 12,
          },
        },
      },
    };
  },
  methods: {
    handleClickSlide(index, reallyIndex) {
      console.log("Click slide!", index, reallyIndex);
    },
  },
};
</script>

<style lang="scss">
.swiper-navigation-btn {
  border-radius: 50%;
  background-color: rgba(231, 32, 25, 0.9);
  width: 48px;
  height: 48px;
  color: white;

  &::after {
    font-size: 16px;
  }
}

.swiper-button-prev {
  left: 40px;
}
.swiper-button-next {
  right: 40px;
}

.swiper-pagination {
  top: initial !important;
  bottom: 0;
  height: 2px !important;
}

.swiper-pagination-progressbar {
  background: none;
}

.swiper-pagination-progressbar-fill {
  background-color: rgba(231, 32, 25, 1) !important;
}
</style>
