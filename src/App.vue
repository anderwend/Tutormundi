<script setup>
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <v-container>
    <v-row>
      <v-col cols="12">
        <img alt="Vue logo" class="logo" src="./assets/livro.png" width="125" height="145" />
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12">
        <HelloWorld msg= "Como foi a ajuda do tutor?" />
      </v-col>
    </v-row>
  </v-container>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  
}
</style>
