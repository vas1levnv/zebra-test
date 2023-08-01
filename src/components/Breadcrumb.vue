<script>
import image from '@/assets/img/breadcrumb.png'

export default {
  name: "Breadcrumb",
  data() {
    return {
      bg: image
    }
  }
}
</script>

<template>
  <div class="breadcrumb">
    <div class="bg">
      <img :src="bg" alt="bg">
    </div>
    <div class="container">
      <div class="breadcrumb-wrapper">
        <div class="breadcrumb-item">
          Новости
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.breadcrumb {
  position: relative;

  &-wrapper {
    position: relative;
    z-index: 5;
    padding: 14rem 0 3rem;
  }

  &-item {
    font-size: 2.5rem;
    font-weight: 700;
  }

  .bg {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    z-index: 1;

    & img {
      object-fit: cover;
      width: 100%;
      height: 100%;
    }
  }

}


</style>