<script>
export default {
  name: "Button"
}
</script>

<template>
  <button>
    <slot></slot>
  </button>
</template>

<style scoped lang="scss">
@import "@/assets/css/vars";

button {
  display: block;
  cursor: pointer;
  background: white;
  border-radius: 0.5rem;
  font-size: 1.25rem;
  font-weight: 600;
  padding: 1rem 2rem;
  color: $btnBlue;
  border: 1px solid $btnBlue;
  transition: $tr;

  &:hover {
    color: white;
    background: $btnBlue;
  }
}
</style>