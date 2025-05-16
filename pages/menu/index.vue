<template>
  <div class="flex flex-col min-h-screen bg-white">
    <!-- Header -->
    <div class="flex items-center px-4 py-4 bg-white">
      <span class="font-semibold text-lg">48 Florentin St</span>
      <UButton icon="i-heroicons-chevron-down" variant="ghost" class="ml-2" />
      <div class="ml-auto flex gap-2">
        <div class="flex gap-2">
          <UButton
            color="primary"
            variant="solid"
            size="lg"
            class="rounded-full !p-0 w-8 h-8 flex items-center justify-center shadow bg-accented"
            aria-label="Map"
          >
            <UIcon name="i-ix-map-alt-1" class="text-white text-xl" />
          </UButton>
          <UButton
            color="primary"
            variant="solid"
            size="lg"
            class="rounded-full !p-0 w-8 h-8 flex items-center justify-center shadow bg-accented"
            aria-label="Location"
          >
            <UIcon name="i-raphael-question" class="text-white text-md" />
          </UButton>
        </div>
      </div>
    </div>
    <!-- Search -->
    <div class="flex items-center gap-2 px-4 mb-4 w-full">
      <!-- Search Input -->
      <UInput
        icon="i-heroicons-magnifying-glass"
        placeholder="Search"
        color="neutral" 
        variant="subtle"
        class="flex-1"
        size="lg"
        rounded="md"
      />
      <!-- Filter Button -->
      <div class="relative inline-block">
        <UButton
          color="primary"
          variant="ghost"
          size="lg"
          class="w-10 h-10 flex items-center justify-center "
          aria-label="Filter"
        >
          <UIcon name="i-heroicons-adjustments-horizontal" class="text-black text-xl" />
        </UButton>
        <span
          class="absolute -top-1 -right-1 bg-black text-white text-xs font-bold rounded-full w-5 h-5 flex items-center justify-center border-2 border-white"
        >
          {{ 3 }}
        </span>
      </div>
    </div>
    <!-- Lista de restaurantes -->
    <div class="flex-1 overflow-y-auto px-4 pb-24">
      <RestaurantCard
        v-for="r in restaurants"
        :key="r.id"
        :restaurant="r"
        class="mb-4"
      />
    </div>
    <!-- Sticky Bottom Navigation -->
    <BottomNav active="Discover" />
  </div>
</template>

<script setup lang="ts">
import RestaurantCard from '~/components/RestaurantCard.vue'
import BottomNav from '~/components/BottomNav.vue'

const restaurants = [
  {
    id: 1,
    name: 'PizzaCrafters Co.',
    desc: 'Handcrafted dough and premium ingredients',
    rating: 5.0,
    reviews: 70,
    hours: '11AM-12PM',
    price: '14.99',
    minOrder: 'from 150 ILS',
    delivery: '30-40 min',
    cost: '$$$$$'
  },
  {
    id: 2,
    name: 'VeggieVista Pizza',
    desc: 'Garden-fresh, veggie-packed pizza',
    rating: 4.8,
    reviews: 954,
    hours: '10AM-10PM',
    price: '7.99',
    minOrder: 'from 50 ILS',
    delivery: '20-30 min',
    cost: '$$$$'
  }
]
</script> 