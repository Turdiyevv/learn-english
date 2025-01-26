<script setup lang="ts">
import { onMounted, onBeforeUnmount, ref } from "vue";

const props = {
  textBSlide: String,
}

const slider = ref<HTMLDivElement | null>(null);
const items = Array.from({ length: 12 }, (_, index) => `Item ${index + 1}`);
let animationId: number | undefined;
let position = 0; // Slider scroll pozitsiyasi

const startInfiniteScroll = () => {
  const scrollSpeed = 0.5; // Pixel/s
  const step = () => {
    if (slider.value) {
      position += scrollSpeed;
      if (position >= slider.value.scrollWidth / 2) {
        position = 0; // Birinchi nusxadan keyin boshiga qaytadi
      }
      slider.value.scrollLeft = position;
    }
    animationId = requestAnimationFrame(step);
  };
  step();
};

onMounted(() => {
  startInfiniteScroll();
});

onBeforeUnmount(() => {
  cancelAnimationFrame(animationId); // Animatsiyani to‘xtatish
});
</script>

<template>
  <div ref="slider" class="slider-wrapper h-24 py-4 flex overflow-hidden">
    <div
      v-for="(x, index) in [...items, ...items]"
      :key="index"
      class="slider-item rounded-lg cursor-pointer flex items-center bg-gray-400 h-full w-[324px] mx-3 flex-shrink-0"
    >
      slider{{ index + 1 }} {{props.textBSlide}}
    </div>
  </div>
</template>


<style scoped>
.slider-wrapper {
  display: flex;
  white-space: nowrap; /* Elementlar yonma-yon */
  overflow: hidden; /* Faqat gorizontal ko'rinish */
}

.slider-item {
  flex-shrink: 0; /* Elementlar kattalashmasligi uchun */
  transition: transform 1s ease; /* Animatsiya */
}
</style>
