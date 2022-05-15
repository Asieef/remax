<template>
    <div class="font-display py-8">
        <div class="text-center text-3xl font-light">
            <h2>New Arrival</h2>
        </div>

        <template>
            <div class="container mx-auto">
                <div class="grid lg:grid-flow-col lg:grid-cols-4 grid-cols-1 gap-6 px-6 py-12" v-if="products != null">
                    <div class="hover:shadow-2xl shadow-lg hover:-translate-y-2 hover:transition hover:duration-1000 duration-1000 "
                        v-for="product in products" :key="product.slug">
                        <router-link :to="`/product/${product.slug}`">
                            <img :src="product.thumbnail" alt="Casing" style="width:250px" />
                            <p class="text-rongtatext text-sm font-semibold px-8 py-2">{{ product.name }}</p>
                        </router-link>
                    </div>
                </div>
            </div>
        </template>


    </div>
</template>


<style scoped>
.font-display {
    font-family: 'Nunito', sans-serif;
    color: #333;
}
</style>


<script>
export default {
    data() {
        return {
            products: [],
            category: "bluetooth-speaker",
            cat_id: [102],
        };
    },

    mounted() {
        this.getData();
    },
    methods: {
        getData() {
            this.$axios
                .get("https://admindash.comcitybd.com/api/brands/Remax/4", {
                    params: {
                        id: this.cat_id,
                    },
                })
                .then((response) => {
                    console.log(response.data);
                    this.products = response.data.data;
                });
        },
    },
};
</script>