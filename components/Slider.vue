  <template>
    <div class="font-display h-[600px] 2xl:h-[900px]">
        <div class="absolute ">
            <div v-for="i in [currentIndex]" :key="i">
                <img :src="currentImg" />

                <!-- <div class="">
                    <a class="prev" @click="prev" href="#">&#10094; Previous</a>
                    <a class="next" @click="next" href="#">&#10095; Next</a>
                </div> -->
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {

            images: [
                "/slider-one.jpg",
                "/slider-two.jpg",
                "/slider-three.jpg",
            ],

            timer: null,
            currentIndex: 0,
        }
    },

    mounted: function () {
        this.startSlide();
    },

    methods: {

        startSlide: function () {
            this.timer = setInterval(this.next, 10000);
        },

        next: function () {
            this.currentIndex += 1;
        },
        prev: function () {
            this.currentIndex -= 1;
        }
    },


    computed: {
        currentImg: function () {
            return this.images[Math.abs(this.currentIndex) % this.images.length];
        }
    }
}

</script>

<style scoped>
.font-display {
    font-family: 'Nunito', sans-serif;
    color: #333;
}
</style>