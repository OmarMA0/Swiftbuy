<script setup>
import ButtonComponent from '../common/ButtonComponent.vue';
import baseInput from '../common/baseInput.vue';
import { RouterLink, RouterView } from 'vue-router'
import { ref } from 'vue';
var search_input = ref("")
</script>

<template>
    <div class="flex bg-[#e8eddf] justify-center justify-evenly gap-4 w-screen">
<ButtonComponent> <RouterLink to="/CartView">Cart</RouterLink></ButtonComponent>
    <div class="flex gap-4">
        <ButtonComponent >
            search
        </ButtonComponent>
        <baseInput v-model="search_input"  placeholder="search ..."></baseInput>
        <p class="bg-[#e8eddf]"> {{ search_input }}</p>
    </div>
<ButtonComponent> Your account </ButtonComponent>
        </div>
</template>