<script setup lang="ts">
import English from "@/assets/images/flags/English.jpg.webp"
import Spanish from "@/assets/images/flags/Spanish.jpg.webp"
import French from "@/assets/images/flags/French.jpg.webp"
import German from "@/assets/images/flags/German.jpg.webp"
import Italian from "@/assets/images/flags/Italian.jpg.webp"
import Portuguese from "@/assets/images/flags/Portuguese.jpg.webp"
import Japanese from "@/assets/images/flags/Japanese.jpg.webp"
import Chinese from "@/assets/images/flags/Chinese.jpg.webp"
import Arabic from "@/assets/images/flags/Arabic.jpg.webp"
import Dutch from "@/assets/images/flags/Dutch.jpg.webp"
import Korean from "@/assets/images/flags/Korean.jpg.webp"
import Swedish from "@/assets/images/flags/Swedish.jpg.webp"
import Norwegian from "@/assets/images/flags/Norwegian.jpg.webp"
import Greek from "@/assets/images/flags/Greek.jpg.webp"
import Hebrew from "@/assets/images/flags/Hebrew.jpg.webp"
import More from "@/assets/images/flags/More-1.jpg.webp"
const flags = [
  {name: 'English', src: English},
  {name: 'Spanish', src: Spanish},
  {name: 'French', src: French},
  {name: 'German', src: German},
  {name: 'Italian', src: Italian},
  {name: 'Portuguese', src: Portuguese},
  {name: 'Japanese', src: Japanese},
  {name: 'Chinese', src: Chinese},
  {name: 'Arabic', src: Arabic},
  {name: 'Dutch', src: Dutch},
  {name: 'Korean', src: Korean},
  {name: 'Swedish', src: Swedish},
  {name: 'Norwegian', src: Norwegian},
  {name: 'Greek', src: Greek},
  {name: 'Hebrew', src: Hebrew},
  {name: 'More-14', src: More},
]
</script>

<template>
 <div class="border border-gray-200 min-h-[410px]">
   <h2>Which language do you want to learn?</h2>
   <div class="flex flex-wrap justify-center gap-14 p-5">
     <div v-for="x in flags" class="cursor-pointer flex flex-wrap items-center justify-center w-[90px] h-[90px] rounded-[20px] ">
      <img :src="x.src" :alt="x.name" class="border rounded-[20px] hover:w-[90px] hover:h-[90px] transition-all duration-480 w-[78px] h-[78px]">
      <div>{{x.name}}</div>
     </div>
   </div>
 </div>
</template>

<style scoped>

</style>