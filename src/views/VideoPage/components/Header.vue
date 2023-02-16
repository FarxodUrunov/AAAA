<script setup lang="ts">
import { ref } from "vue";
import BaseIcons from "@/components/BaseIcon/BaseIcon.vue";
import BaseAvatar from "@/components/BaseAvatar/BaseAvatar.vue";

const isShowInput = ref(false);
const handelInput = () => {
  isShowInput.value = !isShowInput.value;
};
</script>

<template>
  <header>
    <div class="hidden md:flex items-center justify-between">
      <div class="flex items-center">
        <img
          class=""
          src="src/assets/logo.svg"
          width="147.37"
          height="32"
          alt="logo"
        />
        <span class="inline-block w-12 h-[1px] bg-[#ffffff14] rotate-90" />
        <BaseAvatar src="src/assets/img/avatar.svg" alt="avatar" />
      </div>
      <div class="flex items-center gap-10">
        <div class="flex items-center gap-4">
          <input
            v-show="isShowInput"
            class="bg-white rounded-md outline-none px-4 py-1"
            placeholder=""
            type="search"
            name="search"
          />
          <button
            @click="handelInput"
            class="bg-transparent text-white p-1 flex items-center"
          >
            <BaseIcons class="w-4 h-4 mr-2" name="search" />
            <p>Поиск</p>
          </button>
        </div>
        <BaseAvatar src="src/assets/img/emoje.svg" alt="emoji" />
      </div>
    </div>
  </header>
</template>
