<template>
  <div
    ref="aboutUsSection"
    class="grid h-[calc(100vh-83px)] grid-cols-12 border border-black"
  >
    <!-- Left Section -->
    <div class="col-span-6 border-r border-black p-16">
      <p
        class="font-Gilroy text-[50px] font-semibold"
        :style="{ marginTop: `${marginTop}px` }"
      >
        About us
      </p>
    </div>

    <!-- Right Section -->
    <div class="col-span-6">
      <p>Section Below</p>
    </div>
  </div>
</template>

<script setup lang="ts">
  const marginTop = ref<number>(0)
  const aboutUsSection = ref<HTMLElement | null>(null)

  const handleScroll = () => {
    if (aboutUsSection.value) {
      const rect = aboutUsSection.value.getBoundingClientRect()

      const navbarHeight = 83
      const additionalOffset = 20
      const maxPadding = 450

      if (rect.top <= navbarHeight + additionalOffset && rect.bottom > 0) {
        const calculatedMarginTop = Math.min(
          window.scrollY -
            (aboutUsSection.value.offsetTop - navbarHeight) +
            additionalOffset,
          rect.height - 50,
        )

        marginTop.value = Math.min(calculatedMarginTop, maxPadding)
      } else if (rect.top > navbarHeight + additionalOffset) {
        marginTop.value = 0
      }
    }
  }

  onMounted(() => {
    window.addEventListener('scroll', handleScroll)
  })

  onBeforeUnmount(() => {
    window.removeEventListener('scroll', handleScroll)
  })
</script>
