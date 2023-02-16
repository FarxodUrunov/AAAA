<script setup lang="ts">
import BaseCursMenu from "@/components/BaseCursMenu/index.vue";
import BaseLessonStatistcsCard from "@/components/BaseLessonStatistcsCard/index.vue";
import { lesson, statistcsInfo } from "@/data/lesson";
</script>

<template>
  <div class="hidden md:block">
    <div id="scroll" class="h-[654px] overflow-y-scroll pr-1">
      <div v-for="item in lesson" :key="item.name">
        <BaseCursMenu
          :lesson="{ id: item?.id, name: item?.name }"
          :topic="item?.topic"
        />
      </div>
    </div>
    <div class="flex flex-wrap items-center gap-4">
      <BaseLessonStatistcsCard
        v-for="item in statistcsInfo"
        :key="item.id"
        :avatar="item?.avatar"
        :lesson="item.lesson"
        :lessons="item.lessons"
        :title="item.title"
      />
    </div>
  </div>
</template>

<style>
#scroll::-webkit-scrollbar-track {
  background-color: transparent; /*Цвет скролла*/
}
#scroll::-webkit-scrollbar-thumb {
  border-radius: 3.5px; /*Закругление ползунка*/
  background-color: #ffffff80; /*Цвет ползунка*/
}
#scroll::-webkit-scrollbar {
  width: 7px; /*Толщина скролла*/
}
</style>
