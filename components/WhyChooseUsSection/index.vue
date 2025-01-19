<template>
  <div>
    <div
      ref="whyYouChooseSection"
      class="hidden grid-cols-12 xl:grid"
      @wheel="handleScroll"
    >
      <!-- Left Side -->
      <div class="col-span-6 border-r border-black p-16">
        <p
          class="font-Gilroy text-[50px] font-semibold"
          :style="{ marginTop: `${marginTop}px` }"
        >
          Why choose us ?
        </p>
      </div>

      <div
        ref="rightSide"
        class="right-side col-span-12 h-screen overflow-y-scroll border lg:col-span-6"
      >
        <div v-for="item in listData" :key="item.id" class="grid grid-cols-12">
          <div class="col-span-12">
            <div class="font-Gilroy border-b border-black p-16">
              <p class="text-[38px] font-medium">{{ item.title }}</p>
              <p class="mt-2 text-base font-normal">{{ item.description }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="grid grid-cols-12 xl:hidden">
      <!-- Left Section -->
      <div class="col-span-12 border-b border-black p-10">
        <p class="font-Gilroy text-[34px] font-semibold md:text-[50px]">
          Why choose us ?
        </p>
      </div>

      <div class="right-side col-span-12 h-screen overflow-y-scroll border">
        <div v-for="item in listData" :key="item.id" class="grid grid-cols-12">
          <div class="col-span-12">
            <div class="font-Gilroy border-b border-black p-10">
              <p class="text-[38px] font-medium">{{ item.title }}</p>
              <p class="mt-2 text-base font-normal">{{ item.description }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
  const listData = [
    {
      id: 1,
      title: 'Stylish bouquets by florists',
      description:
        'At our floral studio, our professional florists craft the most elegant and stylish bouquets using only the freshest and highest quality materials available. We stay up-to-date with the latest floral design trends and offer unique arrangements that are sure to impress. Let us brighten up your day with our stunning bouquets and same-day delivery service.',
    },
    {
      id: 2,
      title: 'On-time delivery',
      description:
        'Never miss a moment with our on-time flower delivery service. Our couriers will deliver your bouquet personally, without boxes, to ensure it arrives in perfect condition. Trust us to deliver your thoughtful gift reliably.',
    },
    {
      id: 3,
      title: 'Safe payment',
      description:
        'You can feel secure when placing an order with us, as we use industry-standard security measures to protect your payment information. Your transaction will be safe and hassle-free, so you can shop with confidence.',
    },
    {
      id: 4,
      title: 'Subscription by your needs',
      description:
        "With our subscription service tailored to your specific needs, you can enjoy the convenience of having beautiful bouquets delivered straight to your door at regular intervals. Our flexible service is perfect for busy individuals or those who want to ensure they always have fresh flowers on hand. You'll save time and money with this hassle-free solution to your floral needs.",
    },
  ]

  const rightSide = ref<HTMLElement | null>(null)
  const nextSection = ref<HTMLElement | null>(null)
  const marginTop = ref<number>(0)
  const whyYouChooseSection = ref<HTMLElement | null>(null)

  // Status scrolling
  let rightSideDoneScrolling = false

  // Handle Scroll
  const handleScroll = (event: WheelEvent) => {
    if (rightSide.value && !rightSideDoneScrolling) {
      event.preventDefault()

      // Scroll secara manual
      const delta = event.deltaY
      rightSide.value.scrollTop += delta

      // Cek apakah scrolling selesai
      if (
        rightSide.value.scrollTop + rightSide.value.clientHeight >=
        rightSide.value.scrollHeight
      ) {
        rightSideDoneScrolling = true
      }
    } else if (rightSideDoneScrolling && nextSection.value) {
      // Scroll ke section berikutnya
      nextSection.value?.scrollIntoView({ behavior: 'smooth' })
    }
  }

  const handleScrollTitle = () => {
    if (whyYouChooseSection.value) {
      const rect = whyYouChooseSection.value.getBoundingClientRect()

      const navbarHeight = 83
      const additionalOffset = 20
      const maxPadding = 450

      if (rect.top <= navbarHeight + additionalOffset && rect.bottom > 0) {
        const calculatedMarginTop = Math.min(
          window.scrollY -
            (whyYouChooseSection.value.offsetTop - navbarHeight) +
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
    window.addEventListener('scroll', handleScrollTitle)
  })

  onBeforeUnmount(() => {
    window.removeEventListener('scroll', handleScrollTitle)
  })
</script>
