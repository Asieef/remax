<template>
    <div class="container mx-auto font-display py-16">
        <div class="flex flex-col items-center">
            <h2 class="text-3xl font-bold uppercase tracking-wider">Faq</h2>
        </div>

        <div class="px-12 mt-8">
            <!-- FAQ 1 -->
            <h2
                class="font-semibold text-lg text-rongtatext py-4 cursor-pointer"
                @click="toggleFaqOne"
            >Who is authorized distributor of Remax in Bangladesh?</h2>

            <transition
                enter-active-class="transition ease-out duration-300"
                enter-class="transform opacity-0 scale-95"
                enter-to-class="transform opacity-100 scale-100"
                leave-active-class="transition ease-in duration-75"
                leave-class="transform opacity-100 scale-100"
                leave-to-class="transform opacity-0 scale-95"
            >
                <h2
                    class="font-semibold text-gray-700 py-4"
                    v-if="showFaqOne"
                >- Computer City Technologies Limited is the authorized distributor of Remax in Bangladesh.</h2>
            </transition>

            <!-- FAQ 2 -->
            <h2
                class="font-semibold text-lg text-rongtatext py-4 cursor-pointer"
                @click="toggleFaqTwo"
            >How to Purchase from distributor?</h2>

            <transition
                enter-active-class="transition ease-out duration-300"
                enter-class="transform opacity-0 scale-95"
                enter-to-class="transform opacity-100 scale-100"
                leave-active-class="transition ease-in duration-75"
                leave-class="transform opacity-100 scale-100"
                leave-to-class="transform opacity-0 scale-95"
            >
                <h2
                    class="font-semibold text-gray-700 py-4"
                    v-if="showFaqTwo"
                >- - Contact 01938 858816</h2>
            </transition>

            <!-- FAQ 3 -->
            <h2
                class="font-semibold text-lg text-rongtatext py-4 cursor-pointer"
                @click="toggleFaqThree"
            >Does Remax products have warranty?</h2>

            <transition
                enter-active-class="transition ease-out duration-300"
                enter-class="transform opacity-0 scale-95"
                enter-to-class="transform opacity-100 scale-100"
                leave-active-class="transition ease-in duration-75"
                leave-class="transform opacity-100 scale-100"
                leave-to-class="transform opacity-0 scale-95"
            >
                <h2
                    class="font-semibold text-gray-700 py-4"
                    v-if="showFaqThree"
                >- - No, our Remax products do not have warranty</h2>
            </transition>
        </div>
    </div>
</template>

<script>

export default {
    data() {
        return {
            showFaqOne: false,
            showFaqTwo: false,
            showFaqThree: false,

        }
    },

    methods: {
        toggleFaqOne() {
            this.showFaqOne = !this.showFaqOne
        },

        toggleFaqTwo() {
            this.showFaqTwo = !this.showFaqTwo
        },

        toggleFaqThree() {
            this.showFaqThree = !this.showFaqThree
        },

    },

}

</script>

<style scoped>
.font-display {
    font-family: 'Nunito', sans-serif;
}
</style>