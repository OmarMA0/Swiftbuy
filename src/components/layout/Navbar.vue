<script setup>
import ButtonComponent from '../common/ButtonComponent.vue';
import baseInput from '../common/baseInput.vue';
import { RouterLink} from 'vue-router'
import { useRouter } from 'vue-router'
import { ref } from 'vue';
import { username, clearUsername } from '@/stores/user'
import {search} from '@/stores/search'
const router = useRouter()
function Logout(){
    clearUsername()
    router.push('/')
}
</script>

<template>
    <div class="flex bg-[#e8eddf] justify-center gap-20 w-screen">
        <p v-if="username" class="justify-start"> Welcome back {{ username }}</p>
        <ButtonComponent><RouterLink to="/">Home</RouterLink></ButtonComponent>
<ButtonComponent v-if="username"> <RouterLink to="/CartView">Cart</RouterLink></ButtonComponent>
    <div class="flex gap-4">
        <ButtonComponent >
            search
        </ButtonComponent>
        <baseInput v-model="search"  placeholder="search ..."></baseInput>
        <p class="bg-[#e8eddf]"> {{ search }}</p>
    </div>
<ButtonComponent v-if="username" @click="Logout"> Logout </ButtonComponent>
        </div>
</template>