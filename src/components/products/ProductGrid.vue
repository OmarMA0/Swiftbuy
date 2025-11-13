<script setup>
import { computed, onMounted, ref } from 'vue';
import {search} from '@/stores/search'
import ProductCard from './ProductCard.vue';
const data = ref(null)
const isloading = ref(true)
const error = ref(null)
const filtered_data = computed(()=>
(data.value|| []).filter(p=>p.title.toLowerCase().includes(search.value.toLowerCase()))
)
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
        v-for="product in filtered_data" :key="product.id ">
            <ProductCard :product="product"></ProductCard>
        </div>
    </div>
    
</template>