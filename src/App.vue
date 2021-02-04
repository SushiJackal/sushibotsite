<template>
  <div id="wrapper">
    <Begin/>
    <div class="copyright">
      <p>Made with ❤ by Sushi⠀•⠀©2021</p>
    </div>
  </div>
</template>

<script>
import Begin from './components/Begin.vue'

export default {
  name: 'App',
  components: {
    Begin
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

body {
  background: #121717;
}

#app {
  height: 100vh;
  width: 100vw;
}

#wrapper {
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
