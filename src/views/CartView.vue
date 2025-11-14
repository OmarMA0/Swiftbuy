<script setup>
import CartedCard from '@/components/products/CartedCard.vue';
import { carted_products } from '@/stores/carted_products';
</script>

<template>
    <div class="hero h-screen w-screen text-white flex gap-10 bg-cover bg-center]"> 
    <div v-for="product in carted_products" class="flex flex-wrap">
        <CartedCard :product="product" ></CartedCard>
        </div>
    </div>
</template>