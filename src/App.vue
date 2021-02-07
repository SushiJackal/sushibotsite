<template>
  <div v-bind:style="{background: color}" id="wrapper">
    <Theme @toggleTheme="updateTheme($event)"/>

    <transition name="fade">
      <Begin v-show="showBegin" @begin="begin" v-bind:theme="theme"/>
    </transition>

    <transition name="fade">
      <Card v-show="!showBegin" v-bind:cardStyles="cardStyles" v-bind:step="step"/>
    </transition>

    <div class="copyright">
      <p>Made with ❤ by Sushi⠀•⠀©2021</p>
    </div>
  </div>
</template>

<script>
import Begin from './components/Begin.vue'
import Theme from './components/Theme.vue'
import Card from './components/Card.vue'

export default {
  name: 'App',
  components: {
    Theme,
    Begin,
    Card
  },
  data () {
    return {
      color: '#121717',
      theme: '#fff',
      showBegin: true,
      cardStyles: {
        backgroundColor: '#1d1e20'
      },
      step: 0
    }
  },
  methods: {
    updateTheme(light) {
      if(light) {
        this.color = '#fff'
        this.theme = '#333'
        this.cardStyles = {
          backgroundColor: '#f4f2f7',
          filter: 'drop-shadow(12px 12px 4px #dde)'
        }
      }
      else {
        this.color = '#121717'
        this.theme = '#fff'
        this.cardStyles = {
          backgroundColor: '#1d1e20',
          filter: 'drop-shadow(12px 12px 4px #111116)'
        }
      }
    },
    begin() {
      this.showBegin = false
      this.step = 1
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

.fade-leave-active {
  transition: all .35s cubic-bezier(.6,.45,.7,1);
}

.fade-enter-active {
  transition: all .5s cubic-bezier(0,0,.7,1);
}

.fade-leave-to {
  transform: translateX(-80%);
  opacity: 0;
}

.fade-enter-from {
  transform: translateX(130%);
  opacity: 0;
}

#wrapper {
  height: 100vh;
  width: 100vw;
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

  .fade-enter-active {
    transition: all .6s cubic-bezier(0,0,.7,1);
  }
}

@media screen and (min-width: 1025px) {
  .copyright {
    font-size: 26px;
  }

  .fade-enter-active {
    transition: all .55s cubic-bezier(0,0,.7,1);
  }
}

@media screen and (min-width: 1921px) {
  .copyright {
    font-size: 30px;
  }

  .fade-enter-active {
    transition: all .5s cubic-bezier(0,0,.7,1);
  }
}
</style>
