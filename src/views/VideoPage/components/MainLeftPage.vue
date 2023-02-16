<script setup lang="ts">
import { computed, ref } from "vue";
import BaseIcon from "@/components/BaseIcon/BaseIcon.vue";
import BaseCardArticle from "@/components/BaseCardArticle/index.vue";
import BaseAvatar from "@/components/BaseAvatar/BaseAvatar.vue";
import BaseCommentary from "@/components/BaseCommentary/index.vue";
import BaseCorusel from "@/components/BaseCorusel/index.vue";
import { commentaryUser, iconData } from "@/data/commentary";

const isAnswer = computed(() => {
  return (params: any) => (params.length !== 0 ? true : false);
});

const iconShow = computed(() => {
  return (params: string) => {
    if (params === "play") return "sm:hidden";
    if (params === "view") return "sm:hidden";
  };
});

const iconData1 = ref<any>(iconData);
</script>

<template>
  <section>
    <div class="rounded-lg mb-8 overflow-hidden">
      <video height="603" controls>
        <source
          src="src/assets/video/Лара Фабиан - Любовь, Похожая На Сон.mp4"
          type="video/mp4"
        />
        Your browser doesn't support HTML5 video tag.
      </video>
    </div>
    <div class="px-4 sm:px-0 sm:flex items-start justify-between">
      <div>
        <p
          class="text-[#F8A404] font-medium text-[15px] leading-5 tracking-[0.1px]"
        >
          Знакомство
        </p>
        <h3 class="mt-1 mb-3 text-2xl font-bold text-[#ffffffe6]">
          2. Тренды Продаж
        </h3>
        <p class="text-base font-medium text-[#ffffff80] max-w-md">
          Дэн представляет себя, класс, то, что вы узнаете, и объясняет, почему
          для всех.
        </p>
      </div>
      <div
        class="mt-10 sm:mt-3 flex items-center justify-between sm:justify-around sm:gap-4"
      >
        <div
          v-for="item in iconData1"
          :key="item.name"
          class="flex flex-col items-center"
        >
          <span
            :class="iconShow(item.name)"
            class="w-12 h-12 flex items-center justify-center rounded-full sm:bg-[#ffffff1a]"
          >
            <BaseIcon
              :name="item.name"
              :viewBox="item.viewBox"
              :class="item.classWH"
            />
          </span>
          <p class="sm:hidden text-xs font-medium text-[#ffffffe6] text-center">
            {{ item.description }}
          </p>
        </div>
      </div>
    </div>
  </section>

  <span class="inline-block w-full h-[1px] bg-[#ffffff14] mt-8 mb-4" />

  <section class="px-4 sm:px-0">
    <h4 class="hidden md:block text-xl text-[#ffffffe6] font-bold">
      Читайте также
    </h4>
    <h4 class="md:hidden text-lg text-[#ffffffe6] font-bold">Статьи</h4>
    <div class="mt-5 flex flex-wrap gap-6">
      <BaseCardArticle
        text="Прогнозы трендов продаж на ближайшие пять лет"
        src="src/assets/img/statistcs.png"
      />
      <BaseCardArticle
        text="Как себя вели тренды продаж прошедшие 10 лет"
        src="src/assets/img/blocnot.png"
      />
    </div>
  </section>

  <span class="inline-block w-full h-[1px] bg-[#ffffff14] mt-8 mb-4" />

  <section class="px-4 sm:px-0">
    <h4 class="text-xl text-[#ffffffe6] font-bold">32 Комментария</h4>
    <div class="flex items-center gap-5 mt-5 mb-10">
      <BaseAvatar src="src/assets/img/emoje.svg" alt="avatar" />
      <span class="text-[#ffffff66] font-medium text-base tracking-[-0.4px]"
        >Оставить отзыв...</span
      >
    </div>
    <div v-for="item in commentaryUser" :key="item.name" class="mb-8">
      <BaseCommentary
        :commentaryUser="item"
        :answers="item.answers"
        :isAnswer="isAnswer(item.answers)"
      />
    </div>
    <h5
      class="text-center md:text-left md:ml-5 font-medium text-lg text-[#ffffffe6]"
    >
      Показать ещё
    </h5>
  </section>

  <span class="inline-block w-full h-[1px] bg-[#ffffff14] mt-12 mb-4" />

  <section class="px-4 sm:px-0 relative">
    <h4 class="text-xl text-[#ffffffe6] font-bold">Курсы</h4>
    <p class="text-base font-medium text-[#ffffff80] max-w-md mt-2 mb-6">
      TopBreyns снимает курсы от ещё многих профессионалов, которые вам будут
      интересны
    </p>
    <BaseCorusel />
    <button
      class="md:hidden absolute top-[580px] md:top-40 left-1/2 -translate-x-1/2 md:left-[530px] z-50 rounded-full p-3 bg-[#dddcdc1a]"
    >
      <BaseIcon name="cursor" viewBox="0 0 36 36" class="w-9 h-9" />
    </button>
  </section>
</template>
