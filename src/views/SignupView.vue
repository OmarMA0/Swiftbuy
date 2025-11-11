<script setup>
import SContainer from '@/components/common/SContainer.vue';
import baseInput from '@/components/common/baseInput.vue';
import ButtonComponent from '@/components/common/ButtonComponent.vue';
import { RouterLink } from 'vue-router'
</script>

<template>
    <div class="hero h-screen w-screen bg-cover bg-center flex items-center justify-center text-white">
        <SContainer >
            <p>Username : <baseInput></baseInput></p>
            <p>Email : <baseInput type="email"></baseInput></p>
            <p>Password : <baseInput type="password"></baseInput></p>
            <ButtonComponent><router-link to="/Shopping">Sign in</router-link></ButtonComponent>
        </SContainer>
    </div>
</template>