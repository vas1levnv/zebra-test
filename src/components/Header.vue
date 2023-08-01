<script>
import Logo from "@/components/Ui/Logo.vue";

export default {
  name: "Header",
  components: {Logo},
  data() {
    return {
      text: {
        fontSize: '40px',
        marginLeft: '9px'
      },
      wrapper: {
        width: '43px',
        height: '43px'
      },
      word: {
        fontSize: '46px'
      }
    }
  }
}
</script>

<template>
  <header class="header">
    <div class="container">
      <div class="header-wrapper">
        <Logo :text="text"
              :wrapper="wrapper"
              :word="word"/>
      </div>
    </div>
  </header>
</template>

<style lang="scss" scoped>

.header {
  position: sticky;
  top: 0;
  box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.08);
  z-index: 1000;
  background: white;

  &-wrapper {
    padding: 2.5rem 0;
  }
}

</style>