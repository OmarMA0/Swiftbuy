<script setup>
import ButtonComponent from '../common/ButtonComponent.vue';
import { carted_products , add_product } from '@/stores/carted_products';
import { username } from '@/stores/user';
const props = defineProps(['product'])
import { useRouter , RouterLink } from 'vue-router'
const router = useRouter()

function toCart(){
  add_product(props.product)
  router.push('/CartView')
}

</script>

<template>
  <div class="border-4 rounded-xl p-5 m-2 w-128 h-80 bg-[#242423] border-[#f5cb5c] shadow-lg flex flex-col gap-3">
    <h1>{{ product.title }}</h1>
        <p>price :{{ product.price }}</p>
        <p>amount available : {{ product.rating.count }}</p>
        <img class="max-w-24 max-h-24 min-w-24 min-h-24" :src="product.image" alt="product"/>
        <div class="w-full" v-if="username">
    <ButtonComponent class="w-full" @click="toCart">add to cart</ButtonComponent>
          </div>
          <div class="w-full" v-else>
    <ButtonComponent class="w-full"><RouterLink class="block w-full h-full"  to="/Signin"> Sign in </RouterLink></ButtonComponent>
          </div>

  </div>

</template>

<style scoped></style>