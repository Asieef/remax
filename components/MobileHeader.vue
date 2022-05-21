<template>
  <div class="font-display">
    <div class="grid grid-cols-6 bg-black h-12">
      <div class="col-span-4 flex items-center">
        <NuxtLink to="/">
          <img src="/remax-logo.png" class="h-6 px-4" />
        </NuxtLink>
      </div>

      <div class="col-span-1 flex relative items-center justify-end">
        <img src="/search.png" class="h-6 w-6" @click="MobileToggle" />
      </div>

      <transition
        enter-active-class="transition ease-out duration-300"
        enter-class="transform opacity-0 scale-95"
        enter-to-class="transform opacity-100 scale-100"
        leave-active-class="transition ease-in duration-200"
        leave-class="transform opacity-100 scale-100"
        leave-to-class="transform opacity-0 scale-95"
      >
        <div class="absolute top-16 right-12 z-30" v-if="showSearch">
          <div>
            <form
              class="inline"
              @submit.prevent="$nuxt.$emit('customSearch', query)"
            >
              <input
                class="py-1 border border-gray-400 rounded px-2 text-sm"
                type="text"
                placeholder="Keyword.."
                v-model="query"
              />
              <span>
                <button
                  type="submit"
                  class="bg-[#fdd000] py-1 px-2 text-white text-sm"
                >
                  Search
                </button>
              </span>
            </form>
          </div>
        </div>
      </transition>

      <!-- Off Canvas  -->
      <div class="col-span-1 flex items-center justify-center text-sm">
        <div class="flex space-x-2">
          <div>
            <button
              class=""
              type="button"
              data-bs-toggle="offcanvas"
              data-bs-target="#offcanvasExample"
              aria-controls="offcanvasExample"
            >
              <img src="/ham.png" class="h-6" />
            </button>

            <div
              class="offcanvas offcanvas-end fixed bottom-0 flex flex-col max-w-full bg-white invisible bg-clip-padding shadow-sm outline-none transition duration-300 ease-in-out text-gray-700 top-0 right-0 border-none w-72"
              tabindex="-1"
              id="offcanvasExample"
              aria-labelledby="offcanvasExampleLabel"
            >
              <div
                class="offcanvas-header flex items-center justify-between p-4"
              >
                <h5
                  class="offcanvas-title mb-0 leading-normal font-semibold"
                  id="offcanvasExampleLabel"
                >
                  Product Categories
                </h5>
                <button
                  type="button"
                  class="btn-close box-content w-4 h-4 p-2 -my-5 -mr-2 text-black border-none rounded-none opacity-50 focus:shadow-none focus:outline-none focus:opacity-100 hover:text-black hover:opacity-75 hover:no-underline"
                  data-bs-dismiss="offcanvas"
                  aria-label="Close"
                ></button>
              </div>
              <div class="offcanvas-body flex-grow p-4 overflow-y-auto">
                <div>
                  <div class="accordion" id="accordionExample">
                    <div class="accordion-item bg-white border border-gray-200">
                      <h2 class="accordion-header mb-0" id="headingOne">
                        <button
                          class="accordion-button relative flex items-center w-full py-4 px-5 text-base text-gray-800 text-left bg-white border-0 rounded-none transition focus:outline-none"
                          type="button"
                          data-bs-toggle="collapse"
                          data-bs-target="#collapseOne"
                          aria-expanded="true"
                          aria-controls="collapseOne"
                        >
                          Creative Lifestyle
                        </button>
                      </h2>
                      <div
                        id="collapseOne"
                        class="accordion-collapse collapse show"
                        aria-labelledby="headingOne"
                        data-bs-parent="#accordionExample"
                      >
                        <div class="accordion-body py-4 px-5">
                          <div class="flex justify-center">
                            <ul class="bg-white rounded-lg w-96 text-gray-900">
                              <NuxtLink to="/selfiestick">
                                <li
                                  class="px-6 py-2 border-b border-gray-200 w-full rounded-t-lg"
                                >
                                  Selfie Stick
                                </li>
                              </NuxtLink>
                              <NuxtLink to="/laptopbag">
                                <li
                                  class="px-6 py-2 border-b border-gray-200 w-full"
                                >
                                  Laptop Bag
                                </li>
                              </NuxtLink>
                            </ul>
                          </div>
                        </div>
                      </div>
                    </div>
                    <div class="accordion-item bg-white border border-gray-200">
                      <h2 class="accordion-header mb-0" id="headingTwo">
                        <button
                          class="accordion-button collapsed relative flex items-center w-full py-4 px-5 text-base text-gray-800 text-left bg-white border-0 rounded-none transition focus:outline-none"
                          type="button"
                          data-bs-toggle="collapse"
                          data-bs-target="#collapseTwo"
                          aria-expanded="false"
                          aria-controls="collapseTwo"
                        >
                          Audio
                        </button>
                      </h2>
                      <div
                        id="collapseTwo"
                        class="accordion-collapse collapse"
                        aria-labelledby="headingTwo"
                        data-bs-parent="#accordionExample"
                      >
                        <div class="accordion-body py-4 px-5">
                          <div class="flex justify-center">
                            <ul class="bg-white rounded-lg w-96 text-gray-900">
                              <NuxtLink to="/bluetoothspeaker">
                                <li
                                  class="px-6 py-2 border-b border-gray-200 w-full rounded-t-lg"
                                >
                                  Bluetooth Speaker
                                </li>
                              </NuxtLink>

                              <NuxtLink to="/wiredheadphone">
                                <li
                                  class="px-6 py-2 border-b border-gray-200 w-full"
                                >
                                  Wired Headphone & Earphone
                                </li>
                              </NuxtLink>
                              <NuxtLink to="/btheadphone">
                                <li
                                  class="px-6 py-2 border-b border-gray-200 w-full"
                                >
                                  BT Headphone & Earphone
                                </li>
                              </NuxtLink>

                              <NuxtLink to="/voicerecorder">
                                <li
                                  class="px-6 py-2 border-b border-gray-200 w-full"
                                >
                                  Voice Recorder
                                </li>
                              </NuxtLink>

                              <NuxtLink to="/microphone">
                                <li class="px-6 py-2 w-full rounded-b-lg">
                                  Microphone
                                </li>
                              </NuxtLink>
                            </ul>
                          </div>
                        </div>
                      </div>
                    </div>
                    <div class="accordion-item bg-white border border-gray-200">
                      <h2 class="accordion-header mb-0" id="headingThree">
                        <button
                          class="accordion-button collapsed relative flex items-center w-full py-4 px-5 text-base text-gray-800 text-left bg-white border-0 rounded-none transition focus:outline-none"
                          type="button"
                          data-bs-toggle="collapse"
                          data-bs-target="#collapseThree"
                          aria-expanded="false"
                          aria-controls="collapseThree"
                        >
                          Protection
                        </button>
                      </h2>
                      <div
                        id="collapseThree"
                        class="accordion-collapse collapse"
                        aria-labelledby="headingThree"
                        data-bs-parent="#accordionExample"
                      >
                        <div class="accordion-body py-4 px-5">
                          <div class="flex justify-center">
                            <ul class="bg-white rounded-lg w-96 text-gray-900">
                              <NuxtLink to="/mobilecase">
                                <li
                                  class="px-6 py-2 border-b border-gray-200 w-full rounded-t-lg"
                                >
                                  Mobile Case
                                </li>
                              </NuxtLink>
                            </ul>
                          </div>
                        </div>
                      </div>
                    </div>

                    <div class="accordion-item bg-white border border-gray-200">
                      <h2 class="accordion-header mb-0" id="headingFour">
                        <button
                          class="accordion-button collapsed relative flex items-center w-full py-4 px-5 text-base text-gray-800 text-left bg-white border-0 rounded-none transition focus:outline-none"
                          type="button"
                          data-bs-toggle="collapse"
                          data-bs-target="#collapseFour"
                          aria-expanded="false"
                          aria-controls="collapseFour"
                        >
                          Energy
                        </button>
                      </h2>
                      <div
                        id="collapseFour"
                        class="accordion-collapse collapse"
                        aria-labelledby="headingFour"
                        data-bs-parent="#accordionExample"
                      >
                        <div class="accordion-body py-4 px-5">
                          <div class="flex justify-center">
                            <ul class="bg-white rounded-lg w-96 text-gray-900">
                              <NuxtLink to="/usbhub">
                                <li
                                  class="px-6 py-2 border-b border-gray-200 w-full rounded-t-lg"
                                >
                                  USB Hub
                                </li>
                              </NuxtLink>
                              <NuxtLink to="/wirelesscharger">
                                <li
                                  class="px-6 py-2 border-b border-gray-200 w-full"
                                >
                                  Wireless Charger
                                </li>
                              </NuxtLink>
                              <NuxtLink to="/powerstrip">
                                <li
                                  class="px-6 py-2 border-b border-gray-200 w-full"
                                >
                                  Power Strip
                                </li>
                              </NuxtLink>

                              <NuxtLink to="/usbcharger">
                                <li
                                  class="px-6 py-2 border-b border-gray-200 w-full"
                                >
                                  USB/PD Charger
                                </li>
                              </NuxtLink>

                              <NuxtLinkt to="/carcharger">
                                <li
                                  class="px-6 py-2 border-b border-gray-200 w-full"
                                >
                                  Car Charger
                                </li>
                              </NuxtLinkt>

                              <NuxtLink to="/powerbank">
                                <li
                                  class="px-6 py-2 border-b border-gray-200 w-full"
                                >
                                  Power Bank
                                </li>
                              </NuxtLink>

                              <NuxtLink to="/chargingcable">
                                <li
                                  class="px-6 py-2 border-b border-gray-200 w-full"
                                >
                                  Data & Charging Cable
                                </li>
                              </NuxtLink>
                            </ul>
                          </div>
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Ends Off Canvas -->
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showSearch: false,
      showMenu: false,
      query: "",
      data: [],
    };
  },

  methods: {
    MobileToggle() {
      this.showSearch = !this.showSearch;
    },

    ToggleMenu() {
      this.showMenu = !this.showMenu;
    },
  },
};
</script>

<style scoped>
.font-display {
  font-family: "Nunito", sans-serif;
}
</style>
