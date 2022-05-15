<template>
    <div class="font-display">

        <div style="background-image: url('nav-bg.png')" class="bg-cover bg-center h-16 z-20 absolute w-full">
            <div class="grid grid-cols-12">
                <div class="col-span-3 pt-4 pl-4">
                    <NuxtLink to="/">
                        <img src="/remax-logo.png" class="h-8" />
                    </NuxtLink>
                </div>

                <div class="col-span-6 text-sm text-white font-semibold">
                    <ul class="flex justify-between pt-2">
                        <li>
                            <NuxtLink to="/">Home</NuxtLink>
                        </li>

                        <!-- Cretive Lifestyle -->
                        <li @click="toggleMenuCL" class="relative">
                            <NuxtLink to>Creative Lifestyle</NuxtLink>

                            <transition enter-active-class="transition ease-out duration-300"
                                enter-class="transform opacity-0 scale-95"
                                enter-to-class="transform opacity-100 scale-100"
                                leave-active-class="transition ease-in duration-200"
                                leave-class="transform opacity-100 scale-100"
                                leave-to-class="transform opacity-0 scale-95">
                                <div class="bg-black bg-opacity-70 w-48 absolute top-[34px]" v-if="showMenuCL">
                                    <ul class="text-white text-sm font-semibold">
                                        <NuxtLink to="/SelfieStick">
                                            <li class="px-4 py-2 hover:bg-[#FDD000] opacity-100">Selfie Stick</li>
                                        </NuxtLink>
                                        <NuxtLink to="/LaptopBag">
                                            <li class="px-4 py-2 hover:bg-[#FDD000] opacity-100">Laptop Bag</li>
                                        </NuxtLink>
                                    </ul>
                                </div>
                            </transition>
                        </li>

                        <!-- Audio -->
                        <li @click="toggleMenuAD" class="relative">
                            <NuxtLink to>Audio</NuxtLink>

                            <transition enter-active-class="transition ease-out duration-300"
                                enter-class="transform opacity-0 scale-95"
                                enter-to-class="transform opacity-100 scale-100"
                                leave-active-class="transition ease-in duration-200"
                                leave-class="transform opacity-100 scale-100"
                                leave-to-class="transform opacity-0 scale-95">
                                <div class="bg-black bg-opacity-70 w-48 absolute top-[34px]" v-if="showMenuAD">
                                    <ul class="text-white text-sm font-semibold">
                                        <NuxtLink to="/BluetoothSpeaker">
                                            <li class="px-4 py-2 hover:bg-[#FDD000] opacity-100">Bluetooth Speaker
                                            </li>
                                        </NuxtLink>
                                        <NuxtLink to="/BTHeadphone">
                                            <li class="px-4 py-2 hover:bg-[#FDD000] opacity-100">BT Headphone &
                                                Earphone</li>
                                        </NuxtLink>
                                        <NuxtLink to="/WiredHeadphone">
                                            <li class="px-4 py-2 hover:bg-[#FDD000] opacity-100">Wired Headphone &
                                                Earphone</li>
                                        </NuxtLink>
                                        <NuxtLink to="/VoiceRecorder">
                                            <li class="px-4 py-2 hover:bg-[#FDD000] opacity-100">Voice Recorder</li>
                                        </NuxtLink>
                                        <NuxtLink to="/MicroPhone">
                                            <li class="px-4 py-2 hover:bg-[#FDD000] opacity-100">Microphone</li>
                                        </NuxtLink>
                                    </ul>
                                </div>
                            </transition>
                        </li>

                        <!-- Protection -->
                        <li @click="toggleMenuP" class="relative">
                            <NuxtLink to>Protection</NuxtLink>

                            <transition enter-active-class="transition ease-out duration-300"
                                enter-class="transform opacity-0 scale-95"
                                enter-to-class="transform opacity-100 scale-100"
                                leave-active-class="transition ease-in duration-200"
                                leave-class="transform opacity-100 scale-100"
                                leave-to-class="transform opacity-0 scale-95">
                                <div class="bg-black bg-opacity-70 w-48 absolute top-[34px]" v-if="showMenuP">
                                    <ul class="text-white text-sm font-semibold">
                                        <NuxtLink to="/MobileCase">
                                            <li class="px-4 py-2 hover:bg-[#FDD000] opacity-100">Mobile Case</li>
                                        </NuxtLink>
                                    </ul>
                                </div>
                            </transition>
                        </li>

                        <!-- Energy -->

                        <li @click="toggleMenuEN" class="relative">
                            <NuxtLink to>Energy</NuxtLink>

                            <transition enter-active-class="transition ease-out duration-300"
                                enter-class="transform opacity-0 scale-95"
                                enter-to-class="transform opacity-100 scale-100"
                                leave-active-class="transition ease-in duration-200"
                                leave-class="transform opacity-100 scale-100"
                                leave-to-class="transform opacity-0 scale-95">
                                <div class="bg-black bg-opacity-70 w-48 absolute top-[34px]" v-if="showMenuEN">
                                    <ul class="text-white text-sm font-semibold">
                                        <NuxtLink to="/UsbHub">
                                            <li class="px-4 py-2 hover:bg-[#FDD000] opacity-100">USB Hub
                                            </li>
                                        </NuxtLink>
                                        <NuxtLink to="/WirelessCharger">
                                            <li class="px-4 py-2 hover:bg-[#FDD000] opacity-100">Wireless Charger
                                            </li>
                                        </NuxtLink>
                                        <NuxtLink to="/WiredHeadphone">
                                            <li class="px-4 py-2 hover:bg-[#FDD000] opacity-100">Wired Headphone &
                                                Earphone</li>
                                        </NuxtLink>
                                        <NuxtLink to="/PowerStrip">
                                            <li class="px-4 py-2 hover:bg-[#FDD000] opacity-100">Power Strip</li>
                                        </NuxtLink>
                                        <NuxtLink to="/UsbCharger">
                                            <li class="px-4 py-2 hover:bg-[#FDD000] opacity-100">USB/PD Charger</li>
                                        </NuxtLink>

                                        <NuxtLink to="/CarCharger">
                                            <li class="px-4 py-2 hover:bg-[#FDD000] opacity-100">Car Charger</li>
                                        </NuxtLink>

                                        <NuxtLink to="/PowerBank">
                                            <li class="px-4 py-2 hover:bg-[#FDD000] opacity-100">Power Bank</li>
                                        </NuxtLink>

                                        <NuxtLink to="/ChargingCable">
                                            <li class="px-4 py-2 hover:bg-[#FDD000] opacity-100">Data & Charging
                                                Cable</li>
                                        </NuxtLink>
                                    </ul>
                                </div>
                            </transition>
                        </li>
                    </ul>
                </div>

                <!-- Search Box -->
                <div class="col-span-3 flex justify-center pt-2">
                    <NuxtLink to="">
                        <img src="/search.png" class="h-6 relative" @click="toggleSearch" />
                    </NuxtLink>


                    <transition enter-active-class="transition ease-out duration-300"
                        enter-class="transform opacity-0 scale-95" enter-to-class="transform opacity-100 scale-100"
                        leave-active-class="transition ease-in duration-200"
                        leave-class="transform opacity-100 scale-100" leave-to-class="transform opacity-0 scale-95">
                        <div class="absolute top-12 right-28" v-if="showSearch">
                            <div>
                                <form class="inline">
                                    <input class="py-1 px-2 text-sm" type="text" placeholder="Keyword.." />
                                    <span>
                                        <button type="submit" class="bg-[#fdd000] py-1 px-2 text-white text-sm">
                                            Search
                                        </button>
                                    </span>
                                </form>
                            </div>


                        </div>
                    </transition>
                </div>
            </div>
        </div>


    </div>
</template>


<script>
export default {
    data() {
        return {
            showMenuCL: false,
            showMenuAD: false,
            showMenuP: false,
            showMenuEN: false,
            showSearch: false,

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
        toggleMenuCL() {
            this.showMenuCL = !this.showMenuCL;

        },

        toggleMenuAD() {
            this.showMenuAD = !this.showMenuAD;
            this.showMenuCL = false;
            this.showMenuEN = false;
            this.showMenuP = false;
        },

        toggleMenuP() {
            this.showMenuP = !this.showMenuP;
            this.showMenuCL = false;
            this.showMenuEN = false;
            this.showMenuAD = false;
        },

        toggleMenuEN() {
            this.showMenuEN = !this.showMenuEN;
            this.showMenuCL = false;
            this.showMenuAD = false;
            this.showMenuP = false;
        },

        toggleSearch() {
            this.showSearch = !this.showSearch
        },


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