<template>
  <div>
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

      <div class="col-span-1 flex items-center justify-center">
        <img src="/ham.png" class="h-6" @click="ToggleMenu" />
      </div>
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
