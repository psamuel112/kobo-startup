<template>
   <div class="bg-white p-6">
    <div class="min-h-screen bg-[#fbf6ff] p-6">
        <!-- Logo Section -->
        <div class="flex items-center gap-2 mb-20">
            <img src="../../assets/images/svg/kobo-logo.svg" />
        </div>

        <!-- Main Content -->
        <div class="max-w-3xl mx-auto">
            <h2 class="text-4xl font-bold text-gray-800 mb-6">
                Boost your Campaign
            </h2>
            <p class="text-lg text-gray-600 mb-16 max-w-2xl">
                Elevate your music or brand by connecting with creators, or earn money by creating promotional videos
                for artistes and brands
            </p>

            <!-- Testimonial Carousel -->
            <div class="relative overflow-hidden bg-[#290D43] rounded-2xl p-12">
                <div class="relative h-[200px]">
                    <transition-group name="fade" tag="div" class="absolute inset-0">
                        <div v-for="(testimonial, index) in testimonials" :key="testimonial.id"
                            v-show="currentIndex === index" class="w-full h-full flex flex-col justify-between">
                            <p class="text-white text-lg">
                                {{ testimonial.quote }}
                            </p>
                            <div class="flex items-center gap-4 mt-4">
                                <img :src="testimonial.avatar" :alt="`${testimonial.name}'s avatar`"
                                    class="w-12 h-12 rounded-full object-cover" />
                                <div>
                                    <h3 class="text-white font-medium">{{ testimonial.name }}</h3>
                                    <p class="text-gray-400 text-sm">{{ testimonial.title }}</p>
                                </div>
                            </div>
                        </div>
                    </transition-group>
                </div>
            </div>

            <!-- Pagination Dots -->
            <div class="flex justify-center gap-2 mt-8">
                <button v-for="(_, index) in testimonials" :key="index" @click="currentIndex = index"
                    class="w-2 h-2 rounded-full transition-all duration-300"
                    :class="currentIndex === index ? 'bg-[#8726E1] w-4' : 'bg-gray-300'"
                    :aria-label="`Go to slide ${index + 1}`" />
            </div>
        </div>
    </div>
   </div>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'
import image from '../../assets/images/svg/photo.svg'

const testimonials = ref([
    {
        id: 1,
        quote: "We've tried several restoration management tools, but this platform stands out. The real-time tracking and secure data storage have given us confidence and clarity. It's a must-have for any restoration professional looking to optimize their process",
        name: "Micheal",
        title: "Business owner",
        avatar: image
    },
    {
        id: 2,
        quote: "The platform has revolutionized how we handle our campaigns. The intuitive interface and powerful features make it a joy to use.",
        name: "Sarah",
        title: "Marketing Director",
        avatar: image
    },
    {
        id: 3,
        quote: "Outstanding support team and excellent results. We've seen a significant increase in engagement since using this platform.",
        name: "James",
        title: "Content Creator",
        avatar: image
    }
])

const currentIndex = ref(0)
let intervalId = null

const startAutoPlay = () => {
    intervalId = setInterval(() => {
        currentIndex.value = (currentIndex.value + 1) % testimonials.value.length
    }, 5000)
}

onMounted(() => {
    startAutoPlay()
})

onBeforeUnmount(() => {
    if (intervalId) clearInterval(intervalId)
})
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {}

.fade-enter-from,
.fade-leave-to {
    opacity: 0;
}
</style>