<template>
  <nuxt-img :src="img" width="360" height="360" />
</template>

<script setup lang="ts">
  defineProps({
    img: {
      type: String,
      required: true,
    },
  })
</script>
