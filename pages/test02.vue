<template>
  <div class="detail">
    <header class="detail__header">
      <h1 class="detail__title">作品詳細</h1>
      <p class="detail__description">※左右の矢印キーで選択可能です。エンターキーで決定となります。</p>
    </header>
    <section class="detail__section">
      <div class="detail__productInfo">
        <h1>{{ product.name }}</h1>
        <img v-bind:src="product.img">
      </div>
      <nuxt-link to="/test01" class="detail__back">戻る</nuxt-link>
    </section>
  </div>
</template>

<script>

export default {
  data() {
    return {
      product: this.$store.state.product,
    };
  },
  created() {
    // BAD this.$el
    // OK  document
  },
  mounted() {
    this.$el.addEventListener('keydown', this.keydownHandler);
    this.$el.querySelector('.detail__back').focus();
  },
  methods: {
    keydownHandler(e) {
      switch(e.keyCode) {
        default:
          break;
      }
    }
  }
};

</script>

<style scoped lang="scss">
  .detail {
    &__header {
      display: block;
      width: 100%;
      height: 150px;
      background-color: rgb(46, 102, 255);
    }
    &__title {
      color: #fff;
      font-size: 50px;
      font-weight: normal;
    }
    &__description {
      color: #fff;
    }
    &__back {
      display: block;
      width: 200px;
      height: 50px;
      background-color: #333;
      color: #fff;
      text-align: center;
      line-height: 50px;
      &:hover {
        opacity: .7;
      }
    }
  }
</style>

