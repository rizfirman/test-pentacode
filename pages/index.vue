<template>
  <div>
    <AllProductPage />

    <AboutUsSection />
    <div class="col-span-12 border border-black">
      <div class="flex h-[calc(100vh-83px)] items-center justify-center">
        <p>Section Below</p>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
  definePageMeta({
    layout: 'main-layouts',
  })
</script>
