<template>
  <div class="container">
    <h3>Пример вывода данных, полученных из БД при помощи strapi API</h3>
    <ExampleProductItem v-for="product in allProducts.data" :product="product" />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { Context } from "@nuxt/types";

export default Vue.extend({
  name: 'IndexPage',
  async asyncData({ $axios }: Context): Promise<void | object> {
    const allProducts = await $axios.$get('http://localhost:1337/api/products?populate=*');
    const productById = await $axios.$get('http://localhost:1337/api/products/1?populate=*');
    const allCategoriesWithAllProducts = await $axios.$get('http://localhost:1337/api/categories?populate=*');
    return { allProducts, productById, allCategoriesWithAllProducts }
  }
})
</script>
