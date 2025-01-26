<script setup lang="ts">
import Slider from "~/pages/singlComponents/excellence/components/slider.vue";
const textBSlide = ref(`Wow It's really incredible. I can communicate and get feedback on my message. I recommend I've been using the app for less than a week, but I think I'll stick with it for a long time.`)
</script>

<template>
<div class="container min-h-[870px]">
  <h1>EXCELLENCE</h1>
  <slider/>
  <div class="bg-black py-14 px-8">
    <div class="text-center flex flex-col items-center">
      <h1 class=" text-white">LANGUAGE LEARNING EXCELLENCE</h1>
      <h4 class=" text-white">EASY PATH TO FLUENCY</h4>
    </div>
    <div class="flex justify-center">
      <div v-for="x in 3" class="text-white border border-gray-50 p-5 my-4 mx-2 w-[200px]">
        <div>1.5 million</div>
        <div>users</div>
      </div>
    </div>
    <slider :textBSlide="textBSlide" />
  </div>
</div>
</template>

<style scoped>

</style>