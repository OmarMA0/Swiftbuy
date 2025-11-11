<script setup>
import { onMounted, ref } from 'vue';
import ProductCard from './ProductCard.vue';
const data = ref(null)
const isloading = ref(true)
const error = ref(null)

onMounted(async()=>{
try{
    const res = await fetch('https://fakestoreapi.com/products')
    if(!res.ok) throw Error('Network Error')
    data.value = await res.json()
}catch (err){
    error.value = err.message
}finally {
    isloading.value = false 
}
})

</script>

<template>
    <p v-if="isloading">loading ...</p>
    <p v-else-if="error"> Error {{ error }}</p>
    <div class="flex flex-wrap m-5 "  v-else>
        <div 
        v-for="product in data" :key="product.id ">
            <ProductCard :product="product"></ProductCard>
        </div>
    </div>
    
</template>