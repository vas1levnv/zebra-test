<script>
import NewsItem from "@/components/NewsItem.vue";
import Button from "@/components/Ui/Button.vue";

export default {
  name: "NewsList",
  components: {Button, NewsItem},
  data() {
    return {
      news: [],
      page: 1,
      totalPages: null,
      isLoading: false,
      url: 'http://flems.github.io/test/api/news'
    }
  },

  methods: {
    async fetchNews() {
      try {
        const response = await fetch(`${this.url}/${this.page}`)
            .then(response => response.json())
        this.totalPages = response.nav.total
        this.news = response.items
      } catch (e) {
        console.log(e)
      }
    },


    async loadMoreNews() {
      try {
        this.page += 1
        const response = await fetch(`${this.url}/${this.page}`)
            .then(response => response.json())
        this.news = [...this.news, ...response.items]
      } catch (e) {
        console.log(e)
      }
    },
  },

  mounted() {
    this.fetchNews()
  }
}

</script>

<template>
  <div class="news">
    <div class="container">
      <div class="news-wrapper">
        <div class="news-list">
          <NewsItem v-if="!isLoading" class="item" v-for="item in news" :item="item" :key="item.code"/>
        </div>
        <Button v-if="page < totalPages" @click="loadMoreNews">Загрузить еще</Button>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>

.news {
  &-wrapper {
    padding: 4rem 0 4.5rem;

    & button {

      margin: 0 auto;
    }
  }

  &-list {
    display: grid;
    grid-template-columns: repeat(1, 1fr);
    gap: 3rem;
    padding-bottom: 4.5rem;
  }
}

@media (min-width: 768px) {
  .news {
    &-list {
      grid-template-columns: repeat(2, 1fr);
    }
  }
}

@media (min-width: 1400px) {
  .news {
    &-list {
      grid-template-columns: repeat(3, 1fr);
    }
  }
}

</style>