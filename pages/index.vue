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
          v-for="(item, i) in mainItems" :key="i"
          
          :cols="3"
        >
          <v-card class="ma-2">
            <nuxt-link :to="'/item/' + item.id">
            <v-img
              :src="`http://api.comforde.co.kr/${item.Images[0].src}`"
              class="white--text align-end"
              gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
              height="200px"
            >
            
              <v-card-title></v-card-title>
            </v-img>
            </nuxt-link>
            <nuxt-link :to="'/item/' + item.id">
            <div class="textheight">
            <v-card-subtitle>{{item.title}}</v-card-subtitle>
            </div>
            </nuxt-link>
            
            <v-row align="center" class="ml-2">
              <v-rating
                :value="star"
                color="amber"
                dense
                half-increments
                readonly
                size="16"
              ></v-rating>

              <div class="pt-1 grey--text ms-1">{{star}} ({{usercount}})</div>
            </v-row>
            
            <v-card-actions>
              <v-btn class="white mt-0 pa-0 pb-2" elevation="0">
                <span>{{item.cost.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",")}}</span><span>원</span>
              </v-btn>
            </v-card-actions>
            
          </v-card>
        </v-col>
      </v-row>



    <v-row>
      <v-container fluid>
        <v-row>
          <v-col class="border-top-solid border-bottom-solid">
            <div class="d-flex justify-space-around" max-width="100%">
              <h5 class="inline-block"><nuxt-link to="/termsofuse">이용약관</nuxt-link></h5>
              <h5 class="inline-block"><nuxt-link to="/privacy">개인정보처리방침</nuxt-link></h5>
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
    mainItems(){
            return this.$store.state.posts.mainItems;
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
  fetch({store}){  //fetch는 보통 store 넣을때 많이 쓴다.
      return store.dispatch('posts/loadItems', { reset: true});
  },
  created() {
      this.$store.dispatch('posts/loadItems', { reset: true});
  },
  mounted(){
      this.star = 5.0;  
      
      this.usercount = 1;
      
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
.textheight{
  height:80px;
  
}
</style>