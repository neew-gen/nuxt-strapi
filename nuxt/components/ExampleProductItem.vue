<template>
  <div class="container">
    <div class="id">
      id: {{ product.id }}
    </div>
    <div class="title">
      Название: {{ product.attributes.title }}
    </div>
    <div class="cost">
      Цена: {{ product.attributes.cost }}
    </div>
    <div class="cost">
      Цена: {{ product.attributes.description }}
    </div>
    <div class="manufacture-date">
      Дата изготовления: {{ product.attributes.manufactureDate }}
    </div>
    <div class="manufacture-date">
      В продаже: {{ product.attributes.onSale }}
    </div>
    <div class="manufacture-date">
      Категория товара: {{ product.attributes.category.data.attributes.name }}
    </div>
    <div class="manufacture-date">
      Изображение: <img :src="'http://localhost:1337' + product.attributes.image.data.attributes.url" alt="123" :style="{'width' : '300px'}" />
    </div>
  </div>
</template>
<script lang="ts">
export default {
  name: 'ExampleProductItem',
  props: {
    product: {
      type: Object,
      required: true,
    }
  },
}
</script>
<style lang="css"></style>
