<template>
  <div>
    <nav class="flex h-[83px] items-center justify-between border border-black">
      <div class="flex">
        <nuxt-link to="/">
          <div
            class="flex h-[83px] w-[180px] items-center justify-center border-r border-black"
          >
            <p class="font-Gilroy text-base font-medium">Shop</p>
          </div>
        </nuxt-link>

        <nuxt-link to="/">
          <div
            class="flex h-[83px] w-[180px] items-center justify-center border-r border-black"
          >
            <p class="font-Gilroy text-base font-medium">Contact</p>
          </div>
        </nuxt-link>
      </div>
      <div class="flex">
        <nuxt-link to="/">
          <div
            class="flex h-[83px] w-[180px] items-center justify-center border-l border-r border-black"
          >
            <p class="font-Gilroy text-base font-medium">Sign in</p>
          </div>
        </nuxt-link>

        <nuxt-link to="/">
          <div
            class="flex h-[83px] w-[180px] items-center justify-center border-r border-black"
          >
            <p class="font-Gilroy text-base font-medium">Cart</p>
          </div>
        </nuxt-link>
      </div>
    </nav>
  </div>
</template>
