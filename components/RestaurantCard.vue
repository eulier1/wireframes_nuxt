<template>
    <div class="bg-white rounded-xl shadow flex flex-col relative">
      <!-- Image Placeholder -->
      <div class="w-full h-32 bg-gray-200 flex items-center justify-center rounded-tl-xl rounded-tr-xl">
        <UIcon name="i-heroicons-photo" class="text-gray-400 text-3xl" />
      </div>
      <!-- Heart Icon -->
      <UButton
        icon="i-heroicons-heart"
        variant="ghost"
        size="xl"
        class="absolute top-2 right-2"
      />
      <!-- Restaurant Info -->
      <div class="p-2">
        <div class="flex items-center justify-between">
          <span class="font-semibold">{{ restaurant.name }}</span>
          <span class="flex items-center text-xs text-gray-500">
            <UIcon name="i-heroicons-star-solid" class="text-yellow-400 mr-1" />
            {{ restaurant.rating }} <span class="ml-1">({{ restaurant.reviews }})</span>
          </span>
        </div>
        <div class="text-sm text-gray-500">{{ restaurant.desc }}</div>
        <div class="flex flex-wrap justify-between gap-x-3 gap-y-1 mt-2 text-xs text-gray-400">
          <span><UIcon name="i-heroicons-clock" class="inline mr-1" />{{ restaurant.hours }}</span>
          <span class="flex items-center" ><UIcon name="i-fa-solid-dollar-sign" class="inline" /><UIcon name="i-fa-solid-dollar-sign" class="inline" /><UIcon name="i-fa-solid-dollar-sign" class="inline" />{{ restaurant.price }}</span>
        </div>
        <div class="flex flex-wrap items-center gap-x-3 gap-y-1 mt-2 text-xs text-gray-400">
                <UIcon name="i-fa6-solid-motorcycle" />
                <span> 15 ILS  </span>
                <UIcon name="i-fa-solid-circle" style="height: 6px;" />
                <span>{{ restaurant.delivery }}</span>
                <UIcon name="i-fa-solid-circle" style="height: 6px;" />
                <span> {{ restaurant.minOrder }}  </span>
        </div>
      </div>
    </div>
  </template>
  
  <script setup lang="ts">
  defineProps<{ restaurant: any }>()
  </script>