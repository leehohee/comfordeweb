<template>
  <div class="justify-center" :style="{ position: 'relative', width: '100vw' }" id="errorWrapper">
    <h1 v-if="error.statusCode === 404">Page not found {{error.statusCode}}</h1>
    <h1 v-else>불편을 드려 죄송합니다.</h1>
    <nuxt-link to="/">사이트로 돌아가기</nuxt-link>
  </div>
</template>

<script>
export default {
  props: ['error'],
  layout: 'errorLayout'
}
</script>

<style>
  #errorWrapper {
    font-size: 18px;
    text-align: center;
  }
</style>