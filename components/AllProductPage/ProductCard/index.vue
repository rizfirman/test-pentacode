<template>
  <div class="flex h-[300px] flex-col items-center justify-between">
    <div class="flex-grow" />

    <p
      class="font-Gilroy max-w-[163px] text-center text-[26px] font-medium md:max-w-none md:text-[38px]"
    >
      {{ name }}
    </p>

    <div class="flex-grow" />

    <div class="mt-auto flex items-center justify-center">
      <Icon
        v-if="direction === 'img-left'"
        name="material-symbols:arrow-back"
        size="16"
      />
      <p class="font-Gilroy text-sm font-semibold">Shop Now</p>
      <Icon
        v-if="direction === 'img-right'"
        name="material-symbols:arrow-forward"
        size="16"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
  defineProps({
    name: {
      type: String,
      required: true,
    },
    direction: {
      type: String,
      default: 'img-right',
    },
  })
</script>
