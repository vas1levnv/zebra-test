<script>
export default {
  name: "Logo",
  props: ['text', 'wrapper', 'word'],
  data() {
    return {}
  }
}
</script>

<template>
  <a href="/public" @click.prevent class="logo">
    <div class="wrapper" :style="wrapper">
      <div class="word" :style="word">α</div>
    </div>
    <div class="text" :style="text">
      alpha
    </div>
  </a>
</template>

<style lang="scss" scoped>
@import "@/assets/css/vars";

.logo {
  display: flex;
  align-items: center;
}

.wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  background: $blue;
  border-radius: 50%;
}

.word {
  position: relative;
  top: -2px;
  color: $green;
  line-height: 100%;
  font-weight: 600;
}

.text {
  color: $blue;
  font-weight: 900;
}

</style>