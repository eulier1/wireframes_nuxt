<template>
  <div class="bg-gray-100 rounded-xl shadow flex flex-col h-screen">
    <!-- Header -->
    <div class="flex gap-4 p-4 items-center bg-white">
      <UButton
        color="primary"
        variant="solid"
        size="lg"
        class="rounded-full !p-0 w-8 h-8 flex items-center justify-center shadow bg-accented"
        aria-label="Map"
      >
        <UIcon name="i-heroicons-x-mark" class="text-grey text-xl" />
      </UButton>
      <div>
        <div class="text-md font-bold">Your order</div>
        <div class="text-md font-semibold text-gray-400">PizzaCrafters Co.</div>
      </div>
    </div>
    <!-- Product Row -->
    <div class="flex items-start gap-3 bg-white p-4 pt-4 pb-2 w-full">
      <!-- Image Placeholder -->
      <div
        class="w-1/5 h-24 bg-gray-200 rounded-lg flex items-center justify-center"
      >
        <UIcon name="i-heroicons-photo" class="text-gray-400 text-xl" />
      </div>
      <!-- Main Content -->
      <div class="flex-1 min-w-0 items-baseline bg-white">
        <div class="flex items-start justify-between">
          <div>
            <div class="font-semibold leading-tight mb-2">
              Thai Peanut (30.48 cm)
            </div>
            <div class="text-xs text-gray-400 truncate mb-2">
              Thai peanut sauce, chicken, bell peppers, ...
            </div>
          </div>
          <UButton
            icon="i-material-symbols-edit-square-outline-sharp"
            variant="ghost"
            size="sm"
            class="ml-2 text-xl text-black"
          />
        </div>
        <div class="flex items-center">
          <div
            class="flex w-2/3 justify-center items-center border border-gray-300 rounded-lg bg-white px-2 py-1"
          >
            <UButton
              icon="i-heroicons-minus"
              variant="ghost"
              size="xs"
              class="px-1 bg-white"
            />
            <span class="mx-2 text-sm font-semibold bg-gray-100 px-4 py-1"
              >1</span
            >
            <UButton
              icon="i-heroicons-plus"
              variant="ghost"
              size="xs"
              class="px-1 bg-white"
            />
          </div>
          <span class="ml-6 font-bold text-gray-800 text-base">139 ILS</span>
        </div>
      </div>
    </div>
    <!-- Add cutlery -->
    <div class="flex items-center bg-white p-4 mb-4">
      <label
        class="flex justify-center align-center content-center items-center cursor-pointer"
      >
        <div class="relative flex">
          <input
            v-model="isChecked"
            type="checkbox"
            class="peer appearance-none"
          />
          <div
            class="w-6 h-6 border border-gray-200 rounded-sm bg-gray-50 peer-checked:bg-white peer-focus:ring-2 peer-focus:ring-gray-200 transition-colors"
          />
          <svg
            v-show="isChecked"
            class="absolute bottom-0 left-1/2 transform -translate-x-1/2 -translate-y-1/2 w-3.5 h-3.5 text-gray-700"
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 20 20"
            fill="none"
            stroke="currentColor"
            stroke-width="2"
          >
            <path d="M4 10l4 4L16 6" />
          </svg>
        </div>
        <span class="ml-2 text-gray-700 font-bold">Add cutlery</span>
      </label>
    </div>

    <!-- Group order -->
    <div class="bg-white px-4 py-6 flex items-center justify-between mb-4">
      <span class="font-bold text-gray-700">Place a group order</span>
      <UButton variant="solid" color="primary" class="px-4 py-2 flex">
        <UIcon name="i-solar-user-plus-rounded-bold" class="text-2xl" />
        <span class="text-sm"> Invite people </span>
      </UButton>
    </div>

    <!-- Recommendations -->
    <div class="bg-white p-4 mb-2">
      <div class="font-bold text-gray-700 mb-2">Recommended for your order</div>
      <div class="flex gap-2 overflow-x-auto">
        <div
          v-for="item in recommended"
          :key="item.id"
          class="bg-white rounded-lg min-w-[110px] flex flex-col items-start"
        >
          <div
            class="relative w-full h-24 bg-gray-200 rounded-lg flex items-center justify-center mb-2"
          >
            <UIcon name="i-heroicons-photo" class="text-gray-400 text-xl" />
            <div class="rounded-full absolute bottom-2 right-2">
              <UButton
                icon="i-heroicons-plus"
                variant="solid"
                size="md"
                class="mt-1 text-black bg-white rounded-full"
              />
            </div>
          </div>
          <span class="text-xs font-semibold mb-2">{{ item.price }} ILS</span>
          <span class="text-xs font-semibold text-gray-500 text-center">{{
            item.name
          }}</span>
          <span class="text-xs text-gray-400 text-center">{{ item.desc }}</span>
        </div>
      </div>
    </div>

    <!-- Checkout (sticky footer) -->
    <div
      class="fixed bottom-0 left-0 w-full bg-white px-4 py-3 border-t flex flex-col gap-2 z-10"
    >
      <UButton
        class="w-full flex items-center justify-center gap-2 bg-black text-white font-semibold py-2 rounded-lg"
      >
        <span
          class="bg-white text-black rounded-full w-6 h-6 flex items-center justify-center text-xs font-bold mr-2"
          >1</span
        >
        Checkout <span class="ml-2">139 ILS</span>
      </UButton>
      <UButton
        class="w-full flex justify-center border border-gray-300 text-gray-700 font-semibold py-2 rounded-lg bg-white"
        >Add more items</UButton
      >
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

const isChecked = ref(false);

const recommended = [
  { id: 1, price: 10, name: "Coca Cola Zero,", desc: "0.25 ml" },
  { id: 2, price: 13, name: "Homemade Ice Tea,", desc: "0.35 ml" },
  { id: 3, price: 10, name: "Soda,", desc: "0.25 ml" },
];
</script>
