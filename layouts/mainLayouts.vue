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

    <div class="hidden grid-cols-12 border border-black xl:grid">
      <div class="font-Gilroy col-span-3 border-r border-black">
        <div class="p-10">
          <p>
            Remember to offer beautiful flowers from Kyiv LuxeBouquets
            Valentines Day, Mothers Day, Christmas... Reminds you 7 days before.
            No spam or sharing your address
          </p>
          <!-- eslint-disable-next-line vue/html-self-closing -->
          <input
            type="email"
            class="mt-5 h-[56px] w-[272px] border border-gray-500 pl-5"
            placeholder="Your Email"
          />
          <button class="mt-2 h-[56px] w-[272px] border bg-black text-white">
            REMIND
          </button>
        </div>
      </div>
      <div class="font-Gilroy col-span-3 border-r border-black">
        <div class="p-10">
          <p class="text-[21px] font-medium text-[#808080]">Contact us</p>
          <div class="mt-5">
            <p class="text-sm font-normal text-[#808080]">Address</p>
            <p class="text-base font-medium">15/4 Khreshchatyk Street, Kyiv</p>
          </div>
          <div class="mt-5">
            <p class="text-sm font-normal text-[#808080]">Phone</p>
            <p class="text-base font-medium">+380980099777</p>
          </div>
          <div class="mt-5">
            <p class="text-sm font-normal text-[#808080]">General Enquiry:</p>
            <p class="text-base font-medium">Kiev.Florist.Studio@gmail.com</p>
          </div>
          <div class="mt-5">
            <p class="text-[21px] font-medium text-[#808080]">Follow us</p>
            <div class="mt-5 flex items-center gap-5">
              <Icon name="hugeicons:instagram" size="18" />
              <Icon name="hugeicons:pinterest" size="18" />
              <Icon name="iconoir:facebook" size="18" />
              <Icon name="hugeicons:twitter" size="18" />
              <Icon name="hugeicons:telegram" size="18" />
            </div>
          </div>
        </div>
      </div>
      <div class="font-Gilroy col-span-3 border-r border-black">
        <div class="p-10">
          <div>
            <p class="text-[21px] font-medium text-[#808080]">Shop</p>
            <div class="mt-5">
              <nuxt-link to="/all-product" class="text-base font-medium">
                All Product
              </nuxt-link>
              <p class="mt-1 text-base font-medium">Fresh Flowers</p>
              <p class="mt-1 text-base font-medium">Dried Flowers</p>
              <p class="mt-1 text-base font-medium">Live Plants</p>
              <p class="mt-1 text-base font-medium">Designer Vases</p>
              <p class="mt-1 text-base font-medium">Aroma Candles</p>
              <p class="mt-1 text-base font-medium">Freshener Diffuser</p>
            </div>
          </div>

          <div class="mt-5">
            <p class="text-[21px] font-medium text-[#808080]">Service</p>
            <div class="mt-5">
              <p class="text-base font-medium">Flower Subcription</p>
              <p class="mt-1 text-base font-medium">Wedding & Event Decor</p>
            </div>
          </div>
        </div>
      </div>
      <div class="font-Gilroy col-span-3 border-r border-black">
        <div class="p-10">
          <div>
            <p class="text-[21px] font-medium text-[#808080]">About us</p>
            <div class="mt-5">
              <p class="text-base font-medium">Our story</p>
              <p class="mt-1 text-base font-medium">Blog</p>
              <div class="mt-5">
                <p class="mt-1 text-base font-medium">Shipping & returns</p>
                <p class="mt-1 text-base font-medium">Terms & conditions</p>
                <p class="mt-1 text-base font-medium">Privacy policy</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- tablet -->

    <div
      class="grid-cols-12 border border-black sm:hidden md:grid lg:grid xl:hidden"
    >
      <div class="font-Gilroy col-span-6 border-b border-r border-black">
        <div class="p-10">
          <p>
            Remember to offer beautiful flowers from Kyiv LuxeBouquets
            Valentines Day, Mothers Day, Christmas... Reminds you 7 days before.
            No spam or sharing your address
          </p>
          <!-- eslint-disable-next-line vue/html-self-closing -->
          <input
            type="email"
            class="mt-5 h-[56px] w-[272px] border border-gray-500 pl-5"
            placeholder="Your Email"
          />
          <button class="mt-2 h-[56px] w-[272px] border bg-black text-white">
            REMIND
          </button>
        </div>
      </div>
      <div class="font-Gilroy col-span-6 border-r border-black">
        <div class="p-10">
          <p class="text-[21px] font-medium text-[#808080]">Contact us</p>
          <div class="mt-5">
            <p class="text-sm font-normal text-[#808080]">Address</p>
            <p class="text-base font-medium">15/4 Khreshchatyk Street, Kyiv</p>
          </div>
          <div class="mt-5">
            <p class="text-sm font-normal text-[#808080]">Phone</p>
            <p class="text-base font-medium">+380980099777</p>
          </div>
          <div class="mt-5">
            <p class="text-sm font-normal text-[#808080]">General Enquiry:</p>
            <p class="text-base font-medium">Kiev.Florist.Studio@gmail.com</p>
          </div>
          <div class="mt-5">
            <p class="text-[21px] font-medium text-[#808080]">Follow us</p>
            <div class="mt-5 flex items-center gap-5">
              <Icon name="hugeicons:instagram" size="18" />
              <Icon name="hugeicons:pinterest" size="18" />
              <Icon name="iconoir:facebook" size="18" />
              <Icon name="hugeicons:twitter" size="18" />
              <Icon name="hugeicons:telegram" size="18" />
            </div>
          </div>
        </div>
      </div>
    </div>
    <div
      class="grid-cols-12 border border-black sm:hidden md:grid lg:grid xl:hidden"
    >
      <div class="font-Gilroy col-span-6 border-b border-r border-black">
        <div class="p-10">
          <div>
            <p class="text-[21px] font-medium text-[#808080]">Shop</p>
            <div class="mt-5">
              <nuxt-link to="/all-product" class="text-base font-medium"
                >All Product</nuxt-link
              >
              <p class="mt-1 text-base font-medium">Fresh Flowers</p>
              <p class="mt-1 text-base font-medium">Dried Flowers</p>
              <p class="mt-1 text-base font-medium">Live Plants</p>
              <p class="mt-1 text-base font-medium">Designer Vases</p>
              <p class="mt-1 text-base font-medium">Aroma Candles</p>
              <p class="mt-1 text-base font-medium">Freshener Diffuser</p>
            </div>
          </div>

          <div class="mt-5">
            <p class="text-[21px] font-medium text-[#808080]">Service</p>
            <div class="mt-5">
              <p class="text-base font-medium">Flower Subcription</p>
              <p class="mt-1 text-base font-medium">Wedding & Event Decor</p>
            </div>
          </div>
        </div>
      </div>
      <div class="font-Gilroy col-span-6 border-r border-black">
        <div class="p-10">
          <div>
            <p class="text-[21px] font-medium text-[#808080]">About us</p>
            <div class="mt-5">
              <p class="text-base font-medium">Our story</p>
              <p class="mt-1 text-base font-medium">Blog</p>
              <div class="mt-5">
                <p class="mt-1 text-base font-medium">Shipping & returns</p>
                <p class="mt-1 text-base font-medium">Terms & conditions</p>
                <p class="mt-1 text-base font-medium">Privacy policy</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
  import { ref } from 'vue'

  const isMenuOpen = ref(false)

  const toggleMenu = () => {
    isMenuOpen.value = !isMenuOpen.value
  }
</script>
