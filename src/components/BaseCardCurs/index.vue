<script setup lang="ts">
defineProps<{
  cursData: {
    id: number;
    title: string;
    curs_info: string;
    description: string;
    img: string;
  };
}>();
</script>

<template>
  <div
    class="md:flex items-stretch gap-8 md:bg-[#ffffff0a] rounded-[10px] overflow-hidden h-[460px] md:max-h-56 md:min-w-[598px]"
  >
    <div
      :class="
        cursData.id % 2 === 0
          ? 'rounded-r-full'
          : 'md:rounded-tr-[40%] rounded-bl-[40%] md:rounded-bl-[0%]'
      "
      class="mb-8 md:mb-0 overflow-hidden"
    >
      <img
        class="w-full md:w-auto"
        width="250"
        height="337"
        :src="cursData.img"
        alt="image"
      />
    </div>
    <div class="ml-4 md:ml-0 my-auto">
      <h2 class="font-bold text-3xl text-[#ffffffe6]">
        {{ cursData.title }}
      </h2>
      <span class="font-medium text-[13px] text-[#ffffff66]">{{
        cursData.curs_info
      }}</span>
      <p class="font-normal text-[15px] text-[#ffffffe6] max-w-[248px]">
        {{ cursData.description }}
      </p>
    </div>
  </div>
</template>
