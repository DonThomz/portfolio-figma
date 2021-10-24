<template>
  <header>
    <h1><span>{{ firstName }}</span><span>{{ lastName }}</span></h1>
    <ul>
      <li><a href="#about">About</a></li>
      <li><a href="#passions">Passions</a></li>
      <li><a href="#portfolio">Portfolio</a></li>
      <li class="link-primary">
        Contact Us
      </li>
    </ul>
    <div class="burger-menu">
      <span></span><span></span><span></span>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
  props: {
    firstName: {
      type: String,
      default: ''
    },
    lastName: {
      type: String,
      default: ''
    }
  }
}
</script>

<style scoped lang="scss">
header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  h1 {
    font-size: 25px;
    span:first-child {
      font-weight: 700;
    }
    span:last-child {
      font-weight: 400;
    }
  }
}
ul {
  display: flex;
  align-items: center;
  justify-content: center;
  list-style: none;
  li {
    font-family: Poppins;
    font-style: normal;
    font-weight: normal;
    font-size: 25px;
    margin: 0 24px;
    a {
      text-decoration: none; /* no underline */
      color: black;
    }
  }
  @media (max-width: $mobile-breakpoint) {
    display: none;
  }
}
.burger-menu {
  display: block;
  width: 25px;
  height: 25px;
  position: relative;
  cursor: pointer;
  span {
    position: absolute;
    width: 100%;
    background-color: black;
    height: 3px;
    top: 0;
    transform: translateX(-50%);
    border-radius: 20px;
    &:first-child {
      top: 8px;
    }
    &:last-child {
      top: 16px;
    }
  }
  @media (min-width: $mobile-breakpoint) {
    display: none;
  }
}
</style>
