<template>
  <div>
    <nav
      class="flex w-full items-center justify-between border border-black lg:h-[83px]"
    >
      <!-- Burger Menu for Mobile/Tablet -->
      <div
        class="flex h-[56px] w-[56px] items-center justify-center border-r border-black lg:hidden"
      >
        <button
          class="flex h-[50px] w-[50px] items-center justify-center"
          @click="toggleMenu"
        >
          <Icon name="material-symbols:menu" size="24" />
        </button>
      </div>

      <!-- Center Section (Desktop View) -->
      <div class="hidden lg:flex">
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

      <!-- Right Section (Desktop View) -->
      <div class="hidden lg:flex">
        <nuxt-link to="/">
          <div
            class="flex h-[83px] w-[180px] items-center justify-center border-l border-r border-black"
          >
            <p class="font-Gilroy text-base font-medium">Sign in</p>
          </div>
        </nuxt-link>

        <nuxt-link to="/">
          <div
            class="flex h-[83px] w-[180px] items-center justify-center border-black"
          >
            <p class="font-Gilroy text-base font-medium">Cart</p>
          </div>
        </nuxt-link>
      </div>

      <!-- Cart Icon for Mobile/Tablet -->
      <div
        class="flex h-[56px] w-[56px] items-center justify-center border-l border-black lg:hidden"
      >
        <nuxt-link to="/cart">
          <Icon name="material-symbols:shopping-cart" size="24" />
        </nuxt-link>
      </div>
    </nav>

    <!-- Burger Menu Dropdown -->
    <div
      v-if="isMenuOpen"
      class="absolute left-0 top-[60px] z-10 w-full border border-black bg-white lg:hidden"
    >
      <div class="flex flex-col items-center">
        <nuxt-link to="/" class="w-full border-b border-black py-4 text-center">
          Shop
        </nuxt-link>
        <nuxt-link to="/" class="w-full border-b border-black py-4 text-center">
          Contact
        </nuxt-link>
        <nuxt-link to="/" class="w-full border-b border-black py-4 text-center">
          Sign in
        </nuxt-link>
        <nuxt-link to="/" class="w-full border-b border-black py-4 text-center">
          Cart
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
  const isMenuOpen = ref(false)

  const toggleMenu = () => {
    isMenuOpen.value = !isMenuOpen.value
  }
</script>
