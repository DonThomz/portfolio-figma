<template>
  <footer :style="{ backgroundImage: 'url(wave.svg)' }">
    <p>Design By Rauliqbal</p>
  </footer>
</template>

<script>
export default {
  name: "Footer"
}
</script>

<style scoped lang="scss">
footer {
  position: relative;
  height: 400px;
  background-repeat: no-repeat;
  background-size: cover;
  display: flex;
  align-items: center;
  justify-content: center;
  p {
    color: white;
    position: absolute;
    bottom: 0;
    font-size: 35px;
    text-align: center;
  }
}
</style>
