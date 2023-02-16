<script setup lang="ts">
import { ref } from "vue";

export interface TopicType {
  id: number;
  title: string;
  time: string;
  description: string;
}

defineProps<{
  lesson: { id: number; name: string };
  topic: TopicType[];
}>();

const isTopic = ref(2);

const handleTopic = (id: number) => {
  isTopic.value = id;
};
</script>

<template>
  <div class="mb-4">
    <button
      class="w-full text-left font-semibold text-lg rounded-xl px-4 py-1 text-[#ffffffe6] bg-[#ffffff0f]"
    >
      {{ lesson.name }}
    </button>
    <ul>
      <li
        v-for="item in topic"
        :key="item.id"
        :class="
          isTopic === item.id ? 'bg-[#ffffff0f] pl-4 py-4 rounded-xl' : ''
        "
        class="pl-4 my-5 cursor-pointer duration-200"
        @click="handleTopic(item.id)"
      >
        <div
          class="flex justify-between items-center font-medium text-lg text-[#ffffffe6] pr-3"
        >
          <h3>{{ `${item.id}. ${item.title}` }}</h3>
          <span class="font-semibold text-[15px] text-[#ffffff4d]">{{
            item.time
          }}</span>
        </div>
        <p v-if="isTopic === item.id" class="mt-4 font-medium text-[#ffffff80]">
          {{ item.description }}
        </p>
      </li>
    </ul>
  </div>
</template>
