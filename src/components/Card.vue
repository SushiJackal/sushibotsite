<template>
  <div class="Card">
    <div v-bind:style="cardStyles" class="inner">
      <div id="title"><h1><!--STEP {{step}}-->OFFLINE</h1></div>
      <div id="content">
        <Question/> <!-- ONLY PLACEHOLDER TO TEST, THIS HAS TO BE INSTANTIATED DYNAMICALLY PER CARD -->
      </div>
    </div>

  </div>
</template>

<script>
import Question from './Question.vue' //ONLY PLACEHOLDER TO TEST, THIS HAS TO BE IMPORTED DYNAMICALLY PER CARD

export default {
  name: 'Card',
  data() {
    return {
      
    }
  },
  components : {
    Question //ONLY PLACEHOLDER TO TEST, THIS HAS TO BE IMPORTED DYNAMICALLY PER CARD
  },
  methods: {
    
  },
  props: ['cardStyles', 'step']
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@200&display=swap');

.Card {
  position: fixed;
  width:100vw;
  height: 100vh;
  display: grid;
  grid-template-columns: 10% auto 10%;
  grid-template-rows: 13% 420px auto;
}

.inner {
  justify-self: center;
  align-self: center;
  grid-row: 2;
  grid-column: 2;
  width: 100%;
  height: 100%;
  background-color: #1d1e20;
  border: 0;
  border-radius: 25px;
  transition: background-color .35s, filter .35s;
  filter: drop-shadow(12px 12px 4px #111116);
}

@keyframes GradientFade {
    0%{background-position:0% 50%}
    50%{background-position:100% 50%}
    100%{background-position:0% 50%}
}

#title h1 {
  font-size: 32px;
  font-family: 'Montserrat', sans-serif;
  color: white;
  text-align: right;
  margin: 10px 15px;
  background-image: linear-gradient(to bottom right, #617de2, #54cad4);
  background-size: 400% 400%;
  animation: GradientFade 4s ease infinite;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  border-bottom: 3px solid #6195e2;
  float: right;
}


@media screen and (min-width: 768px) {
  .Card {
    grid-template-columns: 23% auto 23%;
    grid-template-rows: 15% 50% auto;
  }

  #title h1 {
    font-size: 40px;
    border-bottom: 3.5px solid #6195e2;
    margin: 14px 20px;
  }
}

@media screen and (min-width: 1025px) {
  .Card {
    grid-template-columns: 32% auto 32%;
    grid-template-rows: 15% 55% auto;
  }

  #title h1 {
    font-size: 48px;
    border-bottom: 4px solid #6195e2;
    margin: 18px 25px;
  }
}

@media screen and (min-width: 1921px) {
  .Card {
    grid-template-columns: 36.5% auto 36.5%;
    grid-template-rows: 15% 55% auto;
  }

  #title h1 {
    font-size: 56px;
    border-bottom: 4.5px solid #6195e2;
    margin: 22px 30px;
  }
}

</style>