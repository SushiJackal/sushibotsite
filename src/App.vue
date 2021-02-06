<template>
  <div v-bind:style="{background: color}" id="wrapper">
    <Theme @toggleTheme="updateTheme($event)"/>

    <transition name="fade">
      <Begin key="ONE" v-show="showBegin" @begin="showBegin = false" v-bind:beginTheme="beginTheme"/>
    </transition>

    <transition name="fade">
      <Begin key="TWO" v-show="!showBegin"/>
    </transition>

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
      beginTheme: '#e6fffc',
      showBegin: true
    }
  },
  methods: {
    updateTheme(light) {
      if(light) {
        this.color = '#e6fffc'
        this.beginTheme = '#333'
      }
      else {
        this.color = '#121717'
        this.beginTheme = '#e6fffc'
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


.fade-leave-active {
  transition: all .4s cubic-bezier(.6,.45,.7,1);
}

.fade-enter-active {
  transition: all .65s cubic-bezier(0,0,.7,1);
}

.fade-leave-to {
  transform: translateX(-80%);
  opacity: 0;
}

.fade-enter-from {
  transform: translateX(90%);
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
