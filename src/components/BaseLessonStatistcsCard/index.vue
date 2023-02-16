<script setup lang="ts">
import { computed } from "vue";
import BaseAvatar from "@/components/BaseAvatar/BaseAvatar.vue";

const props = withDefaults(
  defineProps<{
    avatar?: string;
    lessons?: number;
    lesson?: number;
    title?: string;
  }>(),
  {
    avatar: "",
    lessons: 0,
    lesson: 0,
    title: "",
  }
);

const progress = computed(() => (props.lesson * 100) / props.lessons);
</script>

<template>
  <div
    class="relative mt-12 rounded-xl bg-[#ffffff0a] overflow-hidden w-[208px] h-28"
  >
    <div class="p-4 bg-[#e7e7e70a] h-28" :style="{ width: progress + '%' }">
      <BaseAvatar v-if="avatar.length > 0" :src="avatar" alt="avatar" />
      <div v-else-if="lessons > 0" class="">
        <span class="font-semibold text-3xl text-[#ffffffe6]">{{
          lesson
        }}</span>
        <span class="ml-[2px] font-medium text-lg text-[#ffffff4d]"
          >/{{ lessons }}</span
        >
      </div>
      <h5 v-else class="font-semibold text-3xl text-[#ffffffe6]">
        {{ lesson }}
      </h5>
      <p class="absolute top-[75px] font-medium text-base text-[#ffffffe6]">
        {{ title }}
      </p>
    </div>
  </div>
</template>
