<script setup>
defineProps({
  msg: {
    type: String,
    required: true
  }
})
</script>

<template>
  <div class="greetings">
    <h1 class="#000">{{ msg }}</h1>
  </div>
  <div class="rat">
    <v-row>
        <v-col cols="2" v-for="index3 in rating" :key="index3">
          <div @click = "changerat(index3)">
          <img src="../assets/estrela_cheia.svg" alt="Full star icon"  >
      </div>
    </v-col>
    <v-col cols="2" v-for="index2 in 5-rating" :key="index2">
      <div @click = "changerat(index2+rating)">
      <img src="../assets/estrela_vazia.svg" alt="Empty star icon">
      </div> 
    </v-col>
        </v-row>
  </div>
  <v-row>
    <v-col cols="2">

    </v-col>
    <v-col cols="3">
    <v-btn class="btn" style="color:#2CC6D0" variant="flat"
    >
      Pular
    </v-btn>
    </v-col>
    <v-col cols="6">
    <v-btn class="btn" style="color:#FFF" rounded="pill"
      :color="rating > 0 ? '#2CC6D0': '#C8C8C8'"
      :disabled="rating > 0 ? false : true"
      @click="sendrat()"
    >
      Confirmar
    </v-btn>
    </v-col>
    <v-col cols="1"/>
  </v-row>
</template>

<script>
import StarRating from 'vue-star-rating';


export default {
  data: () => ({ rating: 0, }),
  components: {
    StarRating
  },
  
  methods: {
    sendrat() {
      console.log(this.rating);
    },
    changerat(index){
      this.rating = index;
      console.log(this.rating);
    }
  }
}




</script>

<style scoped>
.btn {
  font-size: 16px;
  font-weight: bold;
}
.rat {
  margin: 24px 0 170px 35px;
}

h1 {
  
  width: 292px;
  height: 50px;
 
  font-family: 'Londrina Solid', cursive;
  font-style: normal;
  font-weight: 400;
  font-size: 40px;
  line-height: 42px;
  
  letter-spacing: 0.2px;
  color: #000000;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1{
  width: 297px; height: 84px; word-wrap: break-word;
  font-weight: 700;
}
.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: center;
  }
}
</style>
