<script setup>
import ButtonComponent from '../common/ButtonComponent.vue';
const props = defineProps(['product'])


</script>

<template>
  <div class="border-4 rounded-xl p-5 m-2 w-128 h-80 bg-[#242423] border-[#f5cb5c] shadow-lg flex flex-col gap-3">
    <h1>{{ product.title }}</h1>
        <p>price :{{ product.price }}</p>
        <p>amount available : {{ product.rating.count }}</p>
        <img class="max-w-24 max-h-24 min-w-24 min-h-24" :src="product.image" alt="product"/>
    <ButtonComponent>add to cart</ButtonComponent>

  </div>

</template>

<style scoped></style>