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
  position: absolute;
  right: 0;
}

.Theme img {
  height: 50px;
  width: 50px;
  padding: 20px;
}

@media screen and (min-width: 768px) {
  .Theme img {
    height: 60px;
    width: 60px;
    padding: 25px;
  }
}

@media screen and (min-width: 1025px) {
  .Theme img {
    height: 70px;
    width: 70px;
    padding: 30px;
  }
}

@media screen and (min-width: 1921px) {
  .Theme img {
    height: 80px;
    width: 80px;
    padding: 35px;
  }
}
</style>
