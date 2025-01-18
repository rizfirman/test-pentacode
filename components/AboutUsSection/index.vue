<template>
  <div>
    <div
      ref="aboutUsSection"
      class="hidden h-[calc(100vh-83px)] grid-cols-12 border border-black lg:grid"
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
        <div class="font-Gilroy p-20">
          <p class="text-sm font-normal">OUR STORY</p>
          <p class="mt-5 text-[38px] font-medium">Kyiv LuxeBouquets</p>
          <p class="mt-5 text-base font-normal">
            We are a modern local floral studio, which specializes in the design
            and delivery of unique bouquets. We have the best florists who
            carefully select each look, our studio cooperates directly with
            farms for growing different flowers, so we always have fresh
            flowers, which are collected by our florists in exquisite bouquets.
            We have a collection of fresh bouquets, collections of dried
            bouquets, house plants, as well as fragrant candles from luxury
            brands to create the perfect atmosphere. Make someone's day amazing
            by sending flowers, plants and gifts the same or next day. Ordering
            flowers online has never been easier.
          </p>
          <button class="mt-5 border border-black px-10 py-2">
            LEARN MORE
          </button>
        </div>
      </div>
    </div>

    <div class="grid grid-cols-12 lg:hidden">
      <!-- Left Section -->
      <div class="col-span-12 border-y border-black p-16">
        <p class="font-Gilroy text-[50px] font-semibold">About us</p>
      </div>

      <!-- Right Section -->
      <div class="col-span-12 h-screen border-b border-black md:h-[559px]">
        <div class="font-Gilroy p-5 md:p-20">
          <p class="text-sm font-normal">OUR STORY</p>
          <p class="mt-5 text-[38px] font-medium">Kyiv LuxeBouquets</p>
          <p class="mt-5 text-base font-normal">
            We are a modern local floral studio, which specializes in the design
            and delivery of unique bouquets. We have the best florists who
            carefully select each look, our studio cooperates directly with
            farms for growing different flowers, so we always have fresh
            flowers, which are collected by our florists in exquisite bouquets.
            We have a collection of fresh bouquets, collections of dried
            bouquets, house plants, as well as fragrant candles from luxury
            brands to create the perfect atmosphere. Make someone's day amazing
            by sending flowers, plants and gifts the same or next day. Ordering
            flowers online has never been easier.
          </p>
          <button class="mt-5 border border-black px-10 py-2">
            LEARN MORE
          </button>
        </div>
      </div>
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
