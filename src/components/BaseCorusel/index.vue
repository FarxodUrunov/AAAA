<script setup lang="ts">
import BaseCardCurs from "@/components/BaseCardCurs/index.vue";
import BaseIcon from "@/components/BaseIcon/BaseIcon.vue";
import { cursData } from "@/data/commentary";
</script>

<template>
  <div class="relative md:max-w-[1082px] h-[460px] md:h-auto overflow-hidden">
    <div class="flex flex-col md:flex-row gap-8">
      <BaseCardCurs v-for="item in cursData" :key="item.id" :cursData="item" />
    </div>
    <button
      class="absolute top-80 md:top-40 left-[270px] md:left-[530px] rounded-full p-3 bg-[#ffffff1a]"
    >
      <BaseIcon name="play_in" viewBox="0 0 20 20" class="w-8 md:w-5" />
    </button>
  </div>
</template>
