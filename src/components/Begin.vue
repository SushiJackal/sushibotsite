<template>
  <div class="Begin">
    <button @click="displayMaintenance">{{ btntext }}</button>
    <span v-bind:style="{color: beginTheme}" v-show="showError">UNDER CONSTRUCTION</span>
  </div>
</template>

<script>
export default {
  name: 'Begin',
  data() {
    return {
      btntext: "Verify",
      showError: false,
    }
  },
  methods: {
    displayMaintenance () {
      this.btntext = 'Offline'
      this.showError = true;
    }
  },
  props: ['beginTheme']
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@500&display=swap');

.Begin {
  height: 100vh;
  display: grid;
  grid-template-columns: auto;
  grid-template-rows: 30% 60px auto;
}

@keyframes GradientFade {
    0%{background-position:0% 50%}
    50%{background-position:100% 50%}
    100%{background-position:0% 50%}
}

.Begin button {
  --btnwidth: 180px;
  --btnheight: 60px;
  --fontsize: 24px;
  transition: height .06s, width .06s, font-size .06s;
  justify-self: center;
  align-self: center;
  grid-row: 2;
  font-family: 'Montserrat', sans-serif;
  background-image: linear-gradient(to bottom right, #617de2, #54cad4);
  background-size: 400% 400%;
  animation: GradientFade 4s ease infinite;
  background-color: #7289DA;
  color: white;
  border: 0;
  border-radius: 100px;
  text-align: center;
  text-decoration: none;
  font-size: var(--fontsize);
  padding: 10px 28px;
  font-weight: bold;
  width: var(--btnwidth);
  height: var(--btnheight);
  outline: none;
}

.Begin button:active {
  width: calc(var(--btnwidth) - 12px);
  height: calc(var(--btnheight) - 4px);
  font-size: calc(var(--fontsize) - 2px);
}

.Begin span {
  transition: color .35s;
  justify-self: center;
  align-self: top;
  grid-row: 3;
  font-size: 16px;
  font-family: 'Montserrat', sans-serif;
  color: white;
  text-align: center;
  padding: 12px;
}

@media screen and (min-width: 768px) {
  .Begin {
    grid-template-rows: 30% 80px auto;
  }
  
  .Begin button {
    --btnwidth: 240px;
    --btnheight: 80px;
    --fontsize: 34px;
    width: var(--btnwidth);
    height: var(--btnheight);
    font-size: var(--fontsize);
    grid-template-rows: 30% 80px auto;
  }

  .Begin span {
    font-size: 22px;
  }
}

@media screen and (min-width: 1025px) {
  .Begin {
    grid-template-rows: 30% 100px auto;
  }

  .Begin button {
    --btnwidth: 300px;
    --btnheight: 100px;
    --fontsize: 44px;
    width: var(--btnwidth);
    height: var(--btnheight);
    font-size: var(--fontsize);
  }

  .Begin span {
    font-size: 28px;
  }
}

@media screen and (min-width: 1921px) {
  .Begin {
    grid-template-rows: 30% 120px auto;
  }

  .Begin button {
    --btnwidth: 360px;
    --btnheight: 120px;
    --fontsize: 54px;
    width: var(--btnwidth);
    height: var(--btnheight);
    font-size: var(--fontsize);
  }

  .Begin span {
    font-size: 34px;
  }
}
</style>
