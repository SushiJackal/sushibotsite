<template>
  <div class="Theme">
    <img v-show="!lightTheme" @click="toggleTheme" src="../assets/light.png">
    <img v-show="lightTheme" @click="toggleTheme" src="../assets/dark.png">
  </div>
</template>

<script>
export default {
  name: 'Theme',
  data() {
    return {
      lightTheme: false
    }
  },
  methods: {
    toggleTheme() {
      this.lightTheme = !this.lightTheme
      this.$emit('toggleTheme', this.lightTheme)
    }
  }
}
</script>

<style>
.Theme {
  z-index: 1;
  position: absolute;
  right: 0;
}

.Theme img {
  height: 35px;
  width: 35px;
  padding: 15px;
}

@media screen and (min-width: 768px) {
  .Theme img {
    height: 45px;
    width: 45px;
    padding: 20px;
  }
}

@media screen and (min-width: 1025px) {
  .Theme img {
    height: 55px;
    width: 55px;
    padding: 25px;
  }
}

@media screen and (min-width: 1921px) {
  .Theme img {
    height: 65px;
    width: 65px;
    padding: 30px;
  }
}
</style>
