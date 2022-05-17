<template>
    <div class="container mx-auto font-display py-16">
        <h3 class="px-6 font-semibold uppercase mt-8">Search Result For "{{ query }}"</h3>

        <div class="grid lg:grid-cols-4 grid-cols-1 gap-6 px-6 py-12" v-if="products != null">
            <div class="hover:shadow-2xl shadow-lg hover:-translate-y-2 hover:transition hover:duration-1000 duration-1000"
                v-for="product in products" :key="product.slug">
                <nuxt-link :to="`/product/${product.slug}`">
                    <img :src="product.thumbnail" alt="Casing" style="width:250px" />
                    <p class="text-rongtatext text-sm font-semibold px-8 py-2">{{ product.name }}</p>
                </nuxt-link>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            query: this.$route.params.data,
            products: [],
        };
    },

    watch: {
        "$route.params.data"(newSlug) {
            this.getData(newSlug);
        },
    },

    mounted() {
        this.getData(this.query);
    },

    methods: {
        getData(newSlug) {
            this.query = newSlug;
            this.$axios
                .get(`https://admindash.comcitybd.com/api/customsearch/Remax/${this.query}`)
                .then((response) => {
                    console.log(response.data);
                    this.products = response.data.data;
                });
        },
    },
};
</script>

<style scoped>
.font-display {
    font-family: 'Nunito', sans-serif;
    color: #333;
}
</style>