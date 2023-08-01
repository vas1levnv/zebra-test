<script>
import NewsList from "@/components/NewsList.vue";
import Header from "@/components/Header.vue";
import Footer from "@/components/Footer.vue";
import Breadcrumb from "@/components/Breadcrumb.vue";


export default {
  components: {
    Breadcrumb,
    Header,
    NewsList,
    Footer
  },
  data() {
    return {}
  }
}
</script>

<template>
  <div class="app-wrapper">
    <Header/>
    <Breadcrumb/>
    <main>
      <NewsList/>
    </main>
    <Footer/>
  </div>
</template>

<style>
@import "https://fonts.googleapis.com/css2?family=Nunito+Sans:opsz,wght@6..12,400;6..12,600;6..12,700;6..12,900&display=swap";

.app-wrapper {
  min-height: 100vh;
  color: #222327;
  font-family: 'Nunito Sans', sans-serif;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

main {
  flex: 1 1 0;
}

.container {
  max-width: 1690px;
  padding: 0 15px;
  margin: 0 auto;
}

*,
*::before,
*::after {
  box-sizing: border-box;
}

ul[class],
ol[class] {
  padding: 0;
}

body,
h1,
h2,
h3,
h4,
p,
ul[class],
ol[class],
li,
figure,
figcaption,
blockquote,
dl,
dd {
  margin: 0;
}

body {
  min-height: 100vh;
  scroll-behavior: smooth;
  text-rendering: optimizeSpeed;
}

ul[class],
ol[class] {
  list-style: none;
}

a {
  color: inherit;
  text-decoration: none;
}

a:not([class]) {
  text-decoration-skip-ink: auto;
}

img {
  max-width: 100%;
  display: block;
}

article > * + * {
  margin-top: 1em;
}

input,
button,
textarea,
select {
  font: inherit;
}

@media (prefers-reduced-motion: reduce) {
  * {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}

</style>
