<template>
  <div class="justify-center" :style="{ position: 'relative', width: '100vw' }">
    <v-container
      class="text-center pa-0"
      :style="{ position: 'relative', width: '400px' }"
    >
      <v-row class="mb-6"> </v-row>
      <v-row>
        <LoginForm />
      </v-row>
      <v-row>
        <v-container>
          <v-card elevation="0">
            
          </v-card>
        </v-container>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import LoginForm from "~/components/LoginForm";
export default {
  
  components: {
    LoginForm,
  },
};
</script>

<style>
</style>