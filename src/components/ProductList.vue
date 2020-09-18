<template>
  <dir>
    <h1>Prodcut List</h1>
    <ul>
      <li v-for="product in products" :key="product.id">{{product.title}} - {{product.price}}</li>
    </ul>
  </dir>
</template>

<script>
import shop from "@/api/shop";

export default {
  data() {
    return {
      products: [],
    };
  },
  created() {
    shop.getProducts((products) => {
      this.products = products;
    });
  },
};
</script>

<style>
</style>