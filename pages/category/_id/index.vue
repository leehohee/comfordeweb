<template>
<div class="justify-center" :style="{ zIndex: '101', width: '100vw' }">
    <v-container fluid :style="{ position: 'relative', zIndex: '100', width: '1170px' }">
      
      <v-row dense>
        <v-col
          v-for="card in cards"
          :key="card.title"
          :cols="card.flex"
        >
          <v-card class="ma-2">
            <v-img
              :src="card.src"
              class="white--text align-end"
              gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
              height="200px"
            >
            </v-img>
              <v-card-title>상품준비중</v-card-title>
              <v-card-subtitle>상품준비중입니다.</v-card-subtitle>
              <v-card-text>0원</v-card-text>
              
            

            
          </v-card>
        </v-col>
      </v-row>
    
    </v-container>
</div>  
</template>

<script>
import PostCard from '~/components/PostCard';
export default {
    layout: "webpagedefault",
    data: () => ({
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
    }),
    components:{
        PostCard,
    },
    computed: {
        
    },
    
}
</script>

<style>

</style>