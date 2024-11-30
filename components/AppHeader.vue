<script setup lang="ts">
const isVisible = ref(false);
</script>

<template>
  <div class="relative">
    <div class="h-24 bg-blue-700 flex items-center">
      <h1 class="text-white ml-3 mr-auto">Logo</h1>
      <div class="flex mr-7">
        <button class="hidden md:block hover:bg-blue-600 text-white border border-white h-10 px-3 rounded-xl">Login</button>
        <button class="hover:bg-gray-100 mx-3 border border-white bg-white h-10 px-3 rounded-xl">Get started</button>
        <button class="hidden md:block hover:bg-blue-600 h-10 text-white px-3 rounded-xl">English</button>
        <button class="block md:hidden hover:bg-blue-600 h-10 text-white px-3 rounded-xl"
        @click="isVisible = !isVisible" >w</button>
      </div>
    </div>
    <transition :duration="{ enter: 500, leave: 500 }" name="nested">
      <div v-show="isVisible" class="absolute top-full left-0 w-full p-3 bg-gray-300">
        <div class="bg-gray-400 text-white p-2 m-3">test</div>
        <div class="bg-gray-400 text-white p-2 m-3">test</div>
        <div class="bg-gray-400 text-white p-2 m-3">test</div>
        <div class="bg-gray-400 text-white p-2 m-3">test</div>
      </div>
    </transition>
  </div>
</template>

<style scoped>
/* Animatsiya davomida max-height o'zgaradi */
.nested-enter-active,
.nested-leave-active {
  transition: max-height 0.3s ease-in-out, transform 0.3s ease-in-out, opacity 0.3s ease-in-out;
}

/* Ochilish jarayonida */
.nested-enter-from {
  max-height: 0;
  opacity: 0;
}

/* Yopilish jarayonida */
.nested-leave-to {
  max-height: 0;
  opacity: 0;
}

/* Balandlikning maksimal qiymati */
.nested-enter-to {
  height: auto;
  max-height: 300px; /* Kontentning maksimal balandligi */
  transform: translateY(0);
  opacity: 1;
}
</style>