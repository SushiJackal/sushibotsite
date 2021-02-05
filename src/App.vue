<template>
  <div v-bind:style="{background: color}" id="wrapper">
    <Theme @toggleTheme="updateTheme($event)"/>
    <Begin v-bind:beginTheme="beginTheme"/>
    <div class="copyright">
      <p>Made with ❤ by Sushi⠀•⠀©2021</p>
    </div>
  </div>
</template>

<script>
import Begin from './components/Begin.vue'
import Theme from './components/Theme.vue'

export default {
  name: 'App',
  components: {
    Theme,
    Begin
  },
  data () {
    return {
      color: '#121717',
      beginTheme: '#ffffff'
    }
  },
  methods: {
    updateTheme(light) {
      if(light) {
        this.color = '#ffffff'
        this.beginTheme = '#333'
      }
      else {
        this.color = '#121717'
        this.beginTheme = '#ffffff'
      }
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

#wrapper {
  transition: background .35s;
}

#app {
  height: 100vh;
  width: 100vw;
  position: relative;
}

@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@200&display=swap');

.copyright {
  font-family: 'Montserrat', sans-serif;
  color: #333;
  position: absolute;
  bottom: 20px;
  left: 0;
  right: 0;
  text-align: center;
  font-size: 16px;
  transition: font-size .06s;
}

@media screen and (min-width: 768px) {
  .copyright {
    font-size: 22px;
  }
}

@media screen and (min-width: 1025px) {
  .copyright {
    font-size: 26px;
  }
}

@media screen and (min-width: 1921px) {
  .copyright {
    font-size: 30px;
  }
}
</style>
