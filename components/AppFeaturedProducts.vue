<template>
  <section>
    <h2>
      <span>Featured Products</span>
    </h2>
    <div class="featureditems">
      <div class="item" :class="product.experience" v-for="product in featuredProducts" :key="product.id">
        <img :src="`/products/${product.img}`" class="prod-image
        "/>
        <h3 class="highlight-product">{{ product.name }}</h3>
        <h4 class="highlight-price">{{ product.price | dollar }}</h4>
        <NuxtLink :to="`/product/${product.id}`">
          <button class="multi-item">View Item ></button>
        </NuxtLink>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  computed: {
    featuredProducts() {
      return this.$store.getters.featuredProducts;
    }
  }
};
</script>

<style lang="scss" scoped>
section {
  margin-top: 60px;
}

.featureditems {
  width: 100%;
  margin: 20px 0 70px;
  .item {
    border: 1px solid #eee2dc;
    box-shadow: 0 3px 10px 0px #eee;
    border-radius: 40px;
    padding: 10px 20px 30px;
    min-height: 150px;
    justify-self: center;
    align-self: center;
    text-align: center;
  }
}

h4 {
  color: #000001;
  margin: 10px 0;
}

h2 {
  color: #000001;
  text-align: center;
  overflow: hidden;
}
h2 span {
  display: inline-block;
  position: relative;
}
h2 span:after,
h2 span:before {
  content: " ";
  display: block;
  height: 1px;
  width: 1000px;
  background: #dab0ef;
  position: absolute;
  top: 50%;
}
h2 span:before {
  left: -1010px;
}
h2 span:after {
  right: -1010px;
}

@media screen and (max-width: 699px) {
  .featureditems {
    width: 83vw;
    margin-left: 5vw;
    div {
      padding: 10px 20px;
      margin-bottom: 10px;
    }
  }

  img {
    width: initial;
  }
}

@media screen and (min-width: 700px) {
  .featureditems {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr;
    grid-template-rows: 1fr;
    grid-column-gap: 20px;
    grid-row-gap: 0px;
    div {
      padding: 40px 50px;
    }
  }

  img {
    width: 100%;
  }
}
</style>
