<template>
  <div class="min-h-screen flex flex-col items-center justify-center bg-gray-50">
    <h1 class="text-2xl font-bold mb-4">Wireframes</h1>
    <UButton class="mt-8" @click="goToRestaurantMenu">Menu Dishes List</UButton>
    <UButton class="mt-8" @click="goToSignUp">Sign up Page</UButton>
    <UButton class="mt-8" @click="goToOrder">Order Page</UButton>
  </div>
</template>

<script setup lang="ts">
import { useRoute, useRouter } from 'vue-router'

const route = useRoute()
const router = useRouter()

const goToRestaurantMenu = () => {
  router.push('/menu')
}

const goToOrder = () => {
  router.push('/order')
}

const goToSignUp = () => {
  router.push('/signup')
}
</script>