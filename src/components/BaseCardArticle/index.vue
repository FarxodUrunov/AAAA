<script setup lang="ts">
import BaseIcon from "@/components/BaseIcon/BaseIcon.vue";

defineProps<{
  text: string;
  src: string;
}>();
</script>

<template>
  <div
    class="flex items-stretch justify-between w-full md:max-w-[440px] bg-[#ffffff0a] rounded-[10px]"
  >
    <div class="py-5 pl-6">
      <div class="flex items-center gap-1.5">
        <BaseIcon
          name="notes"
          viewBox="0 0 20 20"
          class="w-5 h-5 cursor-pointer"
        />
        <span class="text-sm font-medium text-[#ffffff66]">Статья</span>
      </div>
      <p
        class="overflow-hidden font-medium text-base text-[#ffffffe6] mt-2 max-w-[250px]"
      >
        {{ text }}
      </p>
    </div>
    <div class="flex py-2.5 pr-2.5">
      <img :src="src" width="118" height="94" alt="photo" />
    </div>
  </div>
</template>
