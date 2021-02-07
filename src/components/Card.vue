<template>
  <div class="Card">
    <div v-bind:style="cardStyles" class="inner">

    </div>

  </div>
</template>

<script>
export default {
  name: 'Card',
  data() {
    return {
      
    }
  },
  methods: {
    
  },
  props: ['cardStyles']
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
  background-color: #222327;
  border: 0;
  border-radius: 25px;
  transition: background-color .35s, filter .35s;
  filter: drop-shadow(12px 12px 4px #111116);
}

@media screen and (min-width: 768px) {
  .Card {
    grid-template-columns: 23% auto 23%;
    grid-template-rows: 15% 50% auto;
  }
}

@media screen and (min-width: 1025px) {
  .Card {
    grid-template-columns: 32% auto 32%;
    grid-template-rows: 15% 55% auto;
  }
}

@media screen and (min-width: 1921px) {
  .Card {
    grid-template-columns: 38% auto 38%;
    grid-template-rows: 15% 55% auto;
  }
}

</style>