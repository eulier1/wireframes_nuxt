<script setup lang="ts">
import { defineProps } from 'vue'
const props = defineProps<{ active?: string }>()

const items = [
  { label: 'Discover', icon: 'i-mdi-silverware-fork-knife', active: props.active === 'Discover' || !props.active },
  { label: 'Favorites', icon: 'i-material-symbols-favorite', active: props.active === 'Favorites' },
  { label: 'Orders', icon: 'i-material-symbols-lab-profile-outline', active: props.active === 'Orders' },
  { label: 'Profile', icon: 'i-heroicons-user', active: props.active === 'Profile' }
]
</script>

<template>
  <nav class="fixed bottom-0 left-0 w-full bg-white border-t z-20 shadow-sm">
    <div class="flex justify-between px-2 py-1">
      <button
        v-for="item in items"
        :key="item.label"
        class="flex flex-col items-center flex-1 py-1 focus:outline-none"
        :class="item.active ? 'text-black' : 'text-gray-400'"
      >
        <UIcon :name="item.icon" class="text-xl mb-0.5" />
        <span class="text-xs">{{ item.label }}</span>
        <div v-if="item.active" class="w-6 h-0.5 bg-black rounded-full mt-1"/>
      </button>
    </div>
  </nav>
</template> 