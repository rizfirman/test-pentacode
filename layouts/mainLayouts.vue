<template>
  <div>
    <!-- Navbar -->
    <nav
      class="sticky top-0 z-50 grid grid-cols-12 items-center border border-black bg-white lg:h-[83px]"
    >
      <!-- Left Section -->
      <div class="hidden lg:col-span-3 lg:grid">
        <div class="grid grid-cols-12">
          <div class="col-span-6">
            <nuxt-link to="/">
              <div
                class="grid h-[83px] items-center justify-center border-r border-black"
              >
                <p class="font-Gilroy text-base font-medium">Shop</p>
              </div>
            </nuxt-link>
          </div>
          <div class="col-span-6">
            <nuxt-link to="/">
              <div
                class="grid h-[83px] items-center justify-center border-r border-black"
              >
                <p class="font-Gilroy text-base font-medium">Contact</p>
              </div>
            </nuxt-link>
          </div>
        </div>
      </div>

      <!-- Center Section -->
      <div class="col-span-6" />

      <!-- Right Section -->
      <div class="hidden lg:col-span-3 lg:grid">
        <div class="grid grid-cols-12">
          <div class="col-span-6">
            <nuxt-link to="/">
              <div
                class="grid h-[83px] items-center justify-center border-l border-black"
              >
                <p class="font-Gilroy text-base font-medium">Sign in</p>
              </div>
            </nuxt-link>
          </div>
          <div class="col-span-6">
            <nuxt-link to="/">
              <div
                class="grid h-[83px] items-center justify-center border-l border-black"
              >
                <p class="font-Gilroy text-base font-medium">Cart</p>
              </div>
            </nuxt-link>
          </div>
        </div>
      </div>

      <!-- Mobile/Tablet View -->
      <div
        class="col-span-12 grid grid-cols-[auto,1fr,auto] items-center lg:hidden"
      >
        <!-- Burger Menu -->
        <button
          class="grid h-[50px] w-[50px] items-center justify-center border-r border-black"
          @click="toggleMenu"
        >
          <Icon name="material-symbols:menu" size="24" />
        </button>

        <!-- Center Section (Empty) -->
        <div />

        <!-- Cart Icon -->
        <nuxt-link to="/cart">
          <div
            class="grid h-[50px] w-[50px] items-center justify-center border-l border-black"
          >
            <Icon name="material-symbols:shopping-cart" size="24" />
          </div>
        </nuxt-link>
      </div>
    </nav>

    <!-- Dropdown Menu for Mobile/Tablet -->
    <div
      v-if="isMenuOpen"
      class="absolute left-0 top-[60px] z-10 w-full border border-black bg-white lg:hidden"
    >
      <nuxt-link
        to="/"
        class="grid w-full border-b border-black py-4 text-center"
      >
        Shop
      </nuxt-link>
      <nuxt-link
        to="/"
        class="grid w-full border-b border-black py-4 text-center"
      >
        Contact
      </nuxt-link>
      <nuxt-link
        to="/"
        class="grid w-full border-b border-black py-4 text-center"
      >
        Sign in
      </nuxt-link>
      <nuxt-link
        to="/"
        class="grid w-full border-b border-black py-4 text-center"
      >
        Cart
      </nuxt-link>
    </div>

    <!-- Body Slot -->
    <main>
      <slot />
    </main>
  </div>
</template>

<script setup>
  import { ref } from 'vue'

  const isMenuOpen = ref(false)

  const toggleMenu = () => {
    isMenuOpen.value = !isMenuOpen.value
  }
</script>
