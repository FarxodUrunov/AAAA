<script setup lang="ts">
import BaseIcon from "@/components/BaseIcon/BaseIcon.vue";
</script>

<template>
  <footer>
    <div class="max-w-[1650px] md:mx-auto">
      <div class="md:mx-24 pt-10 md:pt-20">
        <div
          class="flex flex-col md:flex-row items-center md:items-start justify-center md:justify-evenly"
        >
          <div
            class="text-center md:text-start flex flex-col items-center md:items-start"
          >
            <img
              src="src/assets/logo.svg"
              width="147.37"
              height="32"
              alt="logo"
            />
            <p
              class="text-base font-medium text-[#ffffff80] max-w-xs mt-3 mb-6 md:mb-10"
            >
              Онлайн курсы премиум качества от ведущих мастеров своей сферы
            </p>
            <div class="flex md:gap-4 gap-6">
              <BaseIcon name="facebook" viewBox="0 0 24 24" />
              <BaseIcon name="instagram" viewBox="0 0 24 24" />
              <BaseIcon name="telegram" viewBox="0 0 24 24" />
              <BaseIcon name="youtub" viewBox="0 0 24 24" />
            </div>
          </div>
          <ul
            class="flex flex-col gap-5 items-center md:items-start mt-12 md:mt-0"
          >
            <li class="text-base font-medium text-[#ffffff80]">Все курсы</li>
            <li class="text-base font-medium text-[#ffffffe6]">Все курсы</li>
            <li class="text-base font-medium text-[#ffffffe6]">Скоро</li>
            <li class="text-base font-medium text-[#ffffffe6]">Поиск</li>
            <li class="text-base font-medium text-[#ffffffe6]">Блог</li>
          </ul>

          <ul
            class="flex flex-col gap-5 items-center md:items-start mt-12 md:mt-0"
          >
            <li class="text-base font-medium text-[#ffffff80]">Формальности</li>
            <li class="text-base font-medium text-[#ffffffe6]">
              Условия использования
            </li>
            <li class="text-base font-medium text-[#ffffffe6]">
              Политикой конф.
            </li>
            <li class="text-base font-medium text-[#ffffffe6]">Контакты</li>
            <li class="text-base font-medium text-[#ffffffe6]">
              Чат с поддержкой
            </li>
            <li class="text-base font-medium text-[#ffffffe6]">Оплата</li>
          </ul>

          <ul
            class="w-full md:w-auto flex flex-col gap-5 items-center md:items-start mt-12 md:mt-0 text-center md:text-start"
          >
            <li class="text-base font-medium text-[#ffffff80]">Новости</li>
            <li class="text-2xl font-semibold italic max-w-xs text-[#ffffffe6]">
              Новости, анонсы и скидки в нашем телеграме
            </li>
            <li class="w-full md:w-auto">
              <a href="https://t.me/khasanshadiyarov">
                <button
                  class="w-full md:w-auto text-lg font-medium text-white flex items-center justify-center gap-2 bg-[#38A5E0] md:rounded-lg px-4 py-2.5 duration-300 hover:bg-[#2580b1]"
                >
                  <BaseIcon name="telegram" viewBox="0 0 24 24" />
                  Перейти
                </button>
              </a>
            </li>
          </ul>
        </div>
        <span
          class="hidden md:inline-block w-full h-[1px] bg-[#ffffff14] mt-12 mb-8"
        />
        <div class="hidden md:flex items-center gap-10 pb-10">
          <BaseIcon
            name="logoBlack"
            viewBox="0 0 111 24"
            class="w-[111px] h-6"
          />
          <p class="text-[#ffffff33] font-medium">© 2021 TopBreyns</p>
          <div class="flex items-center gap-2 text-[#ffffff33] font-medium">
            <BaseIcon name="clock" viewBox="0 0 20 20" />
            <p>Secured with SSL</p>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>
