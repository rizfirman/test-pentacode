<template>
  <div>
    <div class="hidden h-screen grid-cols-12 xl:grid">
      <div class="col-span-6">
        <div class="border-t border-black">
          <div class="grid content-start p-16">
            <div class="font-Gilroy">
              <p class="text-[50px] font-semibold">To Contact Us</p>
              <p class="mt-5 text-[15px] font-medium">We will call you back</p>
              <div class="mt-5 flex items-center gap-2">
                <!-- eslint-disable-next-line vue/html-self-closing -->
                <input
                  type="number"
                  class="h-[56px] w-[272px] border border-gray-500 pl-5"
                  placeholder="+380 XX XXX XX XX"
                />
                <button class="h-[56px] w-[272px] border bg-black text-white">
                  BOOK A CALL
                </button>
              </div>
            </div>
          </div>
        </div>

        <div class="border-b border-t border-black">
          <div class="font-Gilroy grid h-[65px] grid-cols-12">
            <div
              class="col-span-6 flex items-center justify-center border-r border-black"
            >
              <p class="text-[38px] font-medium">Phone</p>
            </div>
            <div class="col-span-6 flex items-center justify-center">
              <p class="text-[38px] font-medium">Address</p>
            </div>
          </div>
        </div>

        <div class="font-Gilroy grid h-full grid-rows-2">
          <div class="grid grid-cols-12">
            <div
              class="col-span-6 flex items-center justify-center border-r border-black"
            >
              <div>
                <div class="flex items-center justify-center">
                  <Icon name="material-symbols:phone-enabled" size="16" />

                  <p class="text-center text-base font-semibold">
                    +380980099777
                  </p>
                </div>
                <div class="mt-5 flex items-center justify-center">
                  <Icon name="material-symbols:phone-enabled" size="16" />

                  <p class="text-center text-base font-semibold">
                    +380980099111
                  </p>
                </div>
              </div>
            </div>
            <div
              class="col-span-6 flex items-center justify-center border-r border-black"
            >
              <div>
                <p class="text-center text-sm font-medium uppercase">
                  opening hours: 8 to 11 p.m.
                </p>

                <div class="mt-5 flex items-center justify-center">
                  <Icon name="material-symbols:file-map" size="18" />

                  <p class="text-center text-base font-semibold">
                    15/4 Khreshchatyk Street, Kyiv
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="col-span-6 grid h-full grid-rows-2">
        <div class="row-span-2 border border-black">
          <nuxt-img src="images/contact-us.png" class="h-full" />
        </div>

        <div class="border border-black">
          <div class="font-Gilroy grid h-[65px] grid-cols-12">
            <div
              class="col-span-6 flex items-center justify-center border-r border-black"
            >
              <p class="text-[38px] font-medium">Follow us</p>
            </div>
            <div class="col-span-6 flex items-center justify-center gap-5">
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

    <div>
      <div class="col-span-12 grid xl:hidden">
        <nuxt-img src="images/contact-us.png" class="h-full w-full" />
      </div>

      <div class="font-Gilroy hidden h-[65px] grid-cols-12 lg:grid">
        <div
          class="col-span-6 flex items-center justify-center border-r border-black"
        >
          <p class="text-[38px] font-medium">Follow us</p>
        </div>
        <div class="col-span-6 flex items-center justify-center gap-5">
          <Icon name="hugeicons:instagram" size="18" />
          <Icon name="hugeicons:pinterest" size="18" />
          <Icon name="iconoir:facebook" size="18" />
          <Icon name="hugeicons:twitter" size="18" />
          <Icon name="hugeicons:telegram" size="18" />
        </div>
      </div>

      <div class="font-Gilroy p-5 lg:hidden">
        <p class="text-[38px] font-medium">Follow us</p>
        <div class="mt-5 flex gap-5">
          <Icon name="hugeicons:instagram" size="18" />
          <Icon name="hugeicons:pinterest" size="18" />
          <Icon name="iconoir:facebook" size="18" />
          <Icon name="hugeicons:twitter" size="18" />
          <Icon name="hugeicons:telegram" size="18" />
        </div>
      </div>

      <div class="border-t border-black">
        <div class="grid content-start p-5 lg:p-16">
          <div class="font-Gilroy">
            <p class="text-[34px] font-semibold lg:text-[50px]">
              To Contact Us
            </p>
            <p class="mt-5 text-[18px] font-medium lg:text-[15px]">
              We will call you back
            </p>
            <div class="mt-5 items-center gap-2 md:flex">
              <!-- eslint-disable-next-line vue/html-self-closing -->
              <input
                type="number"
                class="h-[56px] w-[272px] border border-gray-500 pl-5"
                placeholder="+380 XX XXX XX XX"
              />
              <button
                class="mt-5 h-[56px] w-[272px] border bg-black text-white md:mt-auto"
              >
                BOOK A CALL
              </button>
            </div>
          </div>
        </div>
      </div>

      <div class="hidden lg:block">
        <div class="border-b border-t border-black">
          <div class="font-Gilroy grid h-[65px] grid-cols-12">
            <div
              class="col-span-6 flex items-center justify-center border-r border-black"
            >
              <p class="text-[38px] font-medium">Phone</p>
            </div>
            <div class="col-span-6 flex items-center justify-center">
              <p class="text-[38px] font-medium">Address</p>
            </div>
          </div>
        </div>

        <div class="font-Gilroy grid h-[384px] grid-cols-12">
          <div
            class="col-span-6 flex items-center justify-center border-r border-black"
          >
            <div>
              <div class="flex items-center justify-center">
                <Icon name="material-symbols:phone-enabled" size="16" />

                <p class="text-center text-base font-semibold">+380980099777</p>
              </div>
              <div class="mt-5 flex items-center justify-center">
                <Icon name="material-symbols:phone-enabled" size="16" />

                <p class="text-center text-base font-semibold">+380980099111</p>
              </div>
            </div>
          </div>
          <div
            class="col-span-6 flex items-center justify-center border-r border-black"
          >
            <div>
              <p class="text-center text-sm font-medium uppercase">
                opening hours: 8 to 11 p.m.
              </p>

              <div class="mt-5 flex items-center justify-center">
                <Icon name="material-symbols:file-map" size="18" />

                <p class="text-center text-base font-semibold">
                  15/4 Khreshchatyk Street, Kyiv
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="block lg:hidden">
        <div class="border-b border-t border-black p-5">
          <p class="text-[38px] font-medium">Phone</p>
        </div>

        <div class="p-5">
          <div class="flex items-center">
            <Icon name="material-symbols:phone-enabled" size="16" />

            <p class="text-center text-base font-semibold">+380980099777</p>
          </div>
          <div class="mt-5 flex items-center">
            <Icon name="material-symbols:phone-enabled" size="16" />

            <p class="text-center text-base font-semibold">+380980099111</p>
          </div>
        </div>
      </div>

      <div class="block lg:hidden">
        <div class="border-b border-t border-black p-5">
          <p class="text-[38px] font-medium">Address</p>
        </div>

        <div class="p-5">
          <p class="text-base font-semibold">opening hours: 8 to 11 p.m.</p>

          <div class="mt-5 flex items-center">
            <Icon name="material-symbols:file-map" size="18" />

            <p class="text-base font-semibold">
              15/4 Khreshchatyk Street, Kyiv
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
