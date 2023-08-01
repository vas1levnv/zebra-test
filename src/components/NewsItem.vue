<script>
export default {
  name: "NewsItem",
  props: ['item'],
  data() {
    return {
      date: null,
      day: null,
      month: null,
      year: null,
    }
  },
  mounted() {
    this.date = new Date(this.item.date * 1000)
    this.day = this.date.getDate()
    this.month = this.date.toLocaleString('en-GB', {month: 'long'});
    this.year = this.date.getFullYear()
  }
}

</script>

<template>
  <div class="item">
    <div class="item-img" v-if="item.image">
      <img :src="item.image" alt="">
    </div>
    <div class="item-wrapper">
      <div class="item-date">
        <div class="item-date-day">{{ day }}</div>
        <div>
          <div>{{ month }}</div>
          <div>{{ year }}</div>
        </div>
      </div>
      <a :href="item.link" @click.prevent class="item-name">
        {{ item.name }}
      </a>
      <div class="item-text">
        <span v-html="item.previewText"></span>
      </div>
      <div class="item-type-wrapper">
        <div class="item-type">
          {{ item.type.value }}
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "@/assets/css/vars";

.item {
  border-radius: 1rem;
  border: 1px solid #0F62FE;
  overflow: hidden;
  min-height: 577px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;

  &-wrapper {
    padding: 3rem 2rem;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    flex: 1 1 0;
  }

  &-img {
    margin-bottom: -1rem;
  }

  &-date {
    color: $grey;
    display: flex;
    align-items: center;
    font-size: 15px;
    font-weight: 700;
    line-height: 100%;

    &-day {
      font-weight: 400;
      font-size: 2.25rem;
      margin-right: 0.25rem;
      line-height: 100%;
    }
  }

  &-name {
    margin-top: 1rem;
    font-size: 1.375rem;
    line-height: 120%;
    color: $linkDefault;

    &:hover {
      color: #0029A9;
    }
  }

  &-text {
    margin-top: 1rem;
    font-size: 1.25rem;
    line-height: 130%;
    margin-bottom: 2.5rem;
  }

  &-type {
    border-radius: 1rem;
    padding: 0.25rem 1rem;
    background: $backgroundWhite;

    &-wrapper {
      display: flex;
      width: fit-content;
      align-items: end;
      flex: 1 1 0;
    }
  }
}
</style>