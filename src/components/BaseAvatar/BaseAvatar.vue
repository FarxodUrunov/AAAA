<script setup lang="ts">
const props = withDefaults(
  defineProps<{
    src?: string;
    alt?: string;
  }>(),
  {
    src: "",
    alt: "avatar",
  }
);
</script>

<template>
  <div class="relative">
    <img
      :class="$attrs.class || 'w-12 h-12 rounded-full'"
      :src="props.src"
      :alt="props.alt"
    />
  </div>
</template>
