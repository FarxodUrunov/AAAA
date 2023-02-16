<script setup lang="ts">
import Header from "./components/Header.vue";
import MainLeftPage from "./components/MainLeftPage.vue";
import MainRightPage from "./components/MainRightPage.vue";
import Footer from "./components/Footer.vue";
</script>

<template>
  <div class="bg-[#1E1E1E] h-full">
    <div class="max-w-[1650px] mx-auto bg-[#1E1E1E] px-1 md:pt-7 pb-20">
      <Header />
      <div class="grid sm:grid-cols-7 gap-8 md:mt-10">
        <div class="col-span-5">
          <MainLeftPage />
        </div>
        <div class="col-span-2">
          <MainRightPage />
        </div>
      </div>
    </div>
    <div class="bg-[#ffffff0a]">
      <Footer />
    </div>
  </div>
</template>
