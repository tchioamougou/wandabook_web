<template>
  <div class="relative overflow-auto  border-b bg-gray-100 w-60" style="height:60vh; ">
    <div class="flex flex-row relative " v-for="(it, i ) in CATEGORIES">
      <div
        class="flex w-full justify-between bg-gray-50 py-2 mt-0.5 px-2 cursor-pointer hover:opacity-50 hover:text-[#E01520] capitalize font-display"
        :class="i % 2 === 0 ? 'bg-gray-400 bg-opacity-10' : ''">
        <span> {{ it.name }} </span>

        <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960" width="24px" fill="#5f6368"
          v-if="it.subcategories && it.subcategories.length > 0">
          <path d="M504-480 320-664l56-56 240 240-240 240-56-56 184-184Z" />
        </svg>
      </div>


    </div>
  </div>


</template>

<script setup>
import { ref, onMounted } from "vue";
import { CATEGORIES } from "../view/products/categories";
const active1 = ref(true);


</script>

<style scoped>
.capitalize {
  text-transform: capitalize !important;
}
</style>