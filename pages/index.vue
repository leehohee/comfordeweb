<template>
    <div class="justify-center" :style="{ position: 'relative', width: '100vw' }">
  <v-container class="pa-0" :style="{ position: 'relative', width: '1170px' }">
    <v-carousel
      :show-arrows="false"
      height="400"
      hide-delimiter-background
      delimiter-icon="mdi-circle-medium"
    >
      <v-carousel-item
        v-for="(item, i) in items"
        :key="i"
        :src="item.src"
      ></v-carousel-item>
    </v-carousel>

    <v-row class="mt-5" dense>
        <v-col
          v-for="card in cards"
          :key="card.title"
          :cols="3"
        >
          <v-card class="ma-2">
            <v-img
              :src="card.src"
              class="white--text align-end"
              gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
              height="200px"
            >
              <v-card-title></v-card-title>
            </v-img>
            <v-card-title>상품준비중</v-card-title>
            <v-card-subtitle>상품준비중입니다.</v-card-subtitle>
            <v-card-text>0원</v-card-text>
            
          </v-card>
        </v-col>
      </v-row>

    <v-row>
      <v-container fluid>
        <v-row>
          <v-col class="border-top-solid border-bottom-solid">
            <div class="d-flex justify-space-around" max-width="100%">
              <h5 class="inline-block"><a href="#">서비스 소개</a></h5>
              <h5 class="inline-block"><a href="#">FAQ</a></h5>
              <h5 class="inline-block"> <nuxt-link to="/termsofuse">고객센터</nuxt-link></h5>
            </div>
          </v-col>
        </v-row>
        
      </v-container>
    </v-row>
  </v-container>
    </div>
</template>

<script>
export default {
  computed: {
    height() {
      switch (this.$vuetify.breakpoint.name) {
        case "xs":
          return 100;
        case "md":
          return 500;
        default:
          return 300;
      }
    },
  },
  data() {
    return {
        cards: [
        { title: 'Pre-fab homes', src: 'https://cdn.vuetifyjs.com/images/cards/house.jpg', flex: 3 },
        { title: 'Favorite road trips', src: 'https://cdn.vuetifyjs.com/images/cards/road.jpg', flex: 3 },
        { title: 'Best airlines', src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg', flex: 3 },
        { title: 'Best airlines', src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg', flex: 3 },
        { title: 'Best airlines', src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg', flex: 3 },
        { title: 'Best airlines', src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg', flex: 3 },
        { title: 'Best airlines', src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg', flex: 3 },
        { title: 'Best airlines', src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg', flex: 3 },
      ],
      items: [
        {
          src: "https://d2v80xjmx68n4w.cloudfront.net/assets/images/curated_contents/Au8Dj_curated_content_item_main_mobile_654.jpg",
        },
        {
          src: "https://d2v80xjmx68n4w.cloudfront.net/assets/images/curated_contents/YFwsc_curated_content_item_main_mobile_655.png",
        },
        {
          src: "https://d2v80xjmx68n4w.cloudfront.net/assets/images/curated_contents/Au8Dj_curated_content_item_main_mobile_654.jpg",
        },
        {
          src: "https://d2v80xjmx68n4w.cloudfront.net/assets/images/curated_contents/YFwsc_curated_content_item_main_mobile_655.png",
        },
      ],
      
    };
  },
  
};
</script>

<style scoped>
a {
  text-decoration: none !important;
  color: black !important;
}
.border-top-solid {
  border-top: solid #e6e6e6 1px !important;
}
.border-bottom-solid {
  border-bottom: solid #e6e6e6 1px !important;
}
</style>