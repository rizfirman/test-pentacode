<template>
  <div class="grid grid-cols-12" @wheel="handleScroll">
    <!-- Left Side -->
    <div
      class="left-side col-span-12 border border-b-0 border-black xl:col-span-6 xl:h-[calc(100vh-83px)]"
    >
      <div class="p-5 lg:px-16">
        <div>
          <p class="font-Gilroy text-[40px] xl:text-[67px] xl:font-semibold">
            Kyiv
          </p>
          <div class="flex">
            <p class="font-Gilroy text-[40px] xl:text-[67px] xl:font-semibold">
              LuxeBouquets
            </p>
            <span class="text-[40px]">®</span>
          </div>
          <p class="font-Gilroy text-[18px] font-normal italic text-[#121212]">
            Discover Uniquely Crafted Bouquets and Gifts for Any Occasion:
            Spread Joy with Our Online Flower Delivery Service
          </p>

          <div class="mt-4 h-[2px] w-full bg-black" />

          <div class="mt-5 grid grid-cols-12">
            <div class="col-span-6">
              <nuxt-img
                src="images/front-img.jpeg"
                class="h-[180px] w-[155.5pxpx] grayscale md:h-[256px] md:w-[256px]"
              />
            </div>
            <div class="col-span-6 flex flex-col border-l-2 border-black px-5">
              <div class="flex-grow" />

              <p class="font-Gilroy text-[11px] font-normal md:text-[14px]">
                Experience the joy of giving with our modern floral studio.
                Order online and send fresh flowers, plants and gifts today.
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Right Side -->
    <div
      ref="rightSide"
      class="right-side col-span-12 h-[calc(100vh-83px)] overflow-y-scroll border xl:col-span-6"
    >
      <div
        v-for="menuData in data"
        :key="menuData.id"
        class="grid grid-cols-12"
      >
        <div
          class="col-span-6 flex h-[360px] items-center justify-center border border-b-0 border-l-0 border-black"
        >
          <AllProductPageProductCard
            v-if="menuData.direction === 'img-right'"
            :name="menuData.name"
            :direction="menuData.direction"
          />
          <AllProductPageImageCard v-else :img="menuData.img" />
        </div>
        <div
          class="col-span-6 flex h-[360px] items-center justify-center border-t border-black"
        >
          <AllProductPageImageCard
            v-if="menuData.direction === 'img-right'"
            :img="menuData.img"
          />
          <AllProductPageProductCard
            v-else
            :name="menuData.name"
            :direction="menuData.direction"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
  const data = [
    {
      id: 1,
      name: 'Fresh Flowers',
      img: '/images/fresh-flower.jpeg',
      direction: 'img-right',
    },
    {
      id: 2,
      name: 'Dried Flowers',
      img: '/images/dried-flowers.png',
      direction: 'img-left',
    },
    {
      id: 3,
      name: 'Live Plants',
      img: '/images/live-plants.png',
      direction: 'img-right',
    },
    {
      id: 4,
      name: 'Aroma Candles',
      img: '/images/aroma-candles.png',
      direction: 'img-left',
    },
    {
      id: 5,
      name: 'Fresheners',
      img: '/images/freshener.png',
      direction: 'img-right',
    },
  ]

  // Refs untuk elemen scrolling
  const rightSide = ref<HTMLElement | null>(null)
  const nextSection = ref<HTMLElement | null>(null)

  // Status scrolling
  let rightSideDoneScrolling = false

  // Handle Scroll
  const handleScroll = (event: WheelEvent) => {
    if (rightSide.value && !rightSideDoneScrolling) {
      event.preventDefault() // Mencegah default scrolling behavior

      // Scroll right-side secara manual
      const delta = event.deltaY
      rightSide.value.scrollTop += delta

      // Cek apakah right-side selesai scrolling
      if (
        rightSide.value.scrollTop + rightSide.value.clientHeight >=
        rightSide.value.scrollHeight
      ) {
        rightSideDoneScrolling = true
      }
    } else if (rightSideDoneScrolling && nextSection.value) {
      // Izinkan scrolling ke section berikutnya
      nextSection.value.scrollIntoView({ behavior: 'smooth' })
    }
  }
</script>
