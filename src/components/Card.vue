<template>
  <div class="card">
    <img :src="img" :alt="alt">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: {
    img: {
      type: String,
      default: ''
    },
    alt: {
      type: String,
      default: ''
    },
  },
}
</script>

<style scoped lang="scss">
.card {
  width: 347px;
  height: 280px;
  background: #FFFFFF;
  box-shadow: 0 5px 26px 5px rgba(0, 0, 0, 0.17);
  border-radius: 13px;
  padding: 20px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  img {
    padding: 20px 20px;
  }
}
</style>
