<template>
  <div>
    <Promo></Promo>
    <div class="shop">
      <div class="breadcrumbs">
        <router-link class="link-back" to="/">Back</router-link>
      </div>
      <h1 class="title">Do you like to be dry, coffee and care for nature?</h1>
      <h2 class="subtitle">Then you are in the right place!</h2>

      <div class="products">
        <Product v-for="product in products" :key="product.id"></Product>
      </div>
    </div>
  </div>
</template>

<script>
import Promo from "@/components/Promo.vue";
import Product from "@/components/Product.vue";

export default {
  name: "shop",
  components: {
    Promo,
    Product
  },
  data() {
    return {
      products: [
        "White Rens",
        "White Rens",
        "White Rens",
        "White Rens",
        "White Rens",
        "White Rens",
        "White Rens",
        "White Rens"
      ]
    };
  }
};
</script>

<style>
.shop {
  max-width: 1024px;
  margin: 0 auto;
  padding: 20px;
}
.products {
  overflow: hidden;
  font-size: 0;
  line-height: 0;
  letter-spacing: -0.36em;
  word-spacing: -0.36em;
  margin: 0 -20px;
  padding: 20px 0;
}
.products .holder {
  display: inline-block;
  vertical-align: top;
  width: 25%;
  padding: 0 20px;
  text-align: center;
  margin: 0 0 60px;
  font-size: 14px;
  line-height: normal;
  letter-spacing: normal;
  word-spacing: normal;
}
.breadcrumbs {
  text-align: left;
  font-size: 15px;
}
.link-back {
  color: #000;
  text-decoration: none;
  transition: all ease 0.3s;
}
.link-back:hover {
  color: #f25f5c;
}

@media only screen and (max-width: 768px) {
  .products {
    margin: 0 -10px;
  }
  .products .holder {
    width: 50%;
    padding: 0 10px;
    margin: 0 0 40px;
  }
  .title {
    font-size: 24px;
  }
  .subtitle {
    font-size: 18px;
  }
}
</style>
