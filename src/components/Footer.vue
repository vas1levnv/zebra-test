<script>
import Logo from "@/components/Ui/Logo.vue";

export default {
  name: "Footer",
  components: {Logo},
  data() {
    return {
      text: {
        fontSize: '30px',
        marginLeft: '6px'
      },
      wrapper: {
        width: '33px',
        height: '33px'
      },
      word: {
        fontSize: '34px'
      }
    }
  }
}
</script>

<template>
  <div class="footer">
    <div class="container">
      <div class="footer-wrapper">
        <Logo :text="text"
              :wrapper="wrapper"
              :word="word"/>
        <div class="footer-copyrights">
          © alpha, 2023
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "@/assets/css/vars";

.footer {
  background: $backgroundWhite;

  &-wrapper {
    padding: 4rem 0;
  }

  &-copyrights {
    margin-top: 1rem;
    color: #81899D;
  }
}
</style>