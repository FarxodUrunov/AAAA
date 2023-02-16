<script setup lang="ts">
import BaseAvatar from "@/components/BaseAvatar/BaseAvatar.vue";

export interface CommentaryUser {
  name: string;
  avatar: string;
  description: string;
  date: string;
}

export interface Answer {
  name?: string;
  status?: string;
  avatar?: string;
  description?: string;
  date?: string;
}

withDefaults(
  defineProps<{
    commentaryUser: CommentaryUser;
    isAnswer?: boolean;
    answers?: Answer[];
  }>(),
  {
    isAnswer: false,
    answers: () => [
      {
        name: "",
        status: "",
        avatar: "",
        description: "",
        date: "",
      },
    ],
  }
);
</script>

<template>
  <div>
    <div class="flex items-center gap-5">
      <BaseAvatar :src="commentaryUser.avatar" alt="avatar" />
      <div>
        <b class="block text-white font-medium">{{ commentaryUser.name }}</b>
        <span class="text-[#ffffff80] font-medium text-base tracking-[-0.4px]">
          {{ commentaryUser.date }}
        </span>
      </div>
    </div>
    <div class="ml-[68px] mt-2">
      <p class="text-[#ffffffe6] font-medium max-w-2xl">
        {{ commentaryUser.description }}
      </p>
      <div v-if="isAnswer" class="md:hidden mt-4">
        <b class="text-[#ffffffe6] font-medium">Ответить</b>
        <span class="text-[#ffffff80] font-medium text-base tracking-[-0.4px]">
          - {{ answers?.length }} ответ</span
        >
      </div>
    </div>
    <div v-if="isAnswer" class="mt-8 ml-16">
      <div v-for="answer in answers" :key="answer?.name">
        <div class="flex items-center gap-5">
          <BaseAvatar class="w-9 h-9" :src="answer?.avatar" alt="avatar" />
          <div>
            <b class="block text-white font-medium">{{
              `${answer?.name} - ${answer?.status}`
            }}</b>
            <span
              class="text-[#ffffff80] font-medium text-base tracking-[-0.4px]"
            >
              {{ answer?.date }}
            </span>
          </div>
        </div>
        <p class="text-[#ffffffe6] ml-[58px] mt-2 max-w-2xl">
          {{ answer?.description }}
        </p>
      </div>
    </div>
  </div>
</template>
