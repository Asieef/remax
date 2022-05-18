<template>
  <div>
    <MobileHeader class="hidedesktop" @custom-search="searchs" />
    <Header @custom-search="searchs" class="hidemobile" />
    <Nuxt />
    <Footer />
  </div>
</template>

<script>
export default {
  data() {
    return {
      showSearch: false,
      mydata: "",
    };
  },
  created() {
    this.$nuxt.$on("customSearch", ($event) => this.searchs($event));
  },
  methods: {
    searchs(event) {
      console.log(event);
      this.$router.push({ path: `/search/${event}` });
    },

    test(e) {
      console.log(e);
    },
  },
};
</script>

<style scoped>
.font-display {
  font-family: "Nunito", sans-serif;
}

@media (max-width: 768px) {
  .hidemobile {
    display: none;
  }
}

@media (min-width: 768px) {
  .hidedesktop {
    display: none;
  }
}
</style>
