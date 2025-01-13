<template>
    <section class="pt-24 md:pt-32 pb-16 bg-gradient-to-br from-purple-50 to-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex flex-col lg:flex-row items-center gap-8 lg:gap-12">
          <!-- Content -->
          <div class="flex-1 text-center lg:text-left">
            <div class="inline-flex items-center gap-2 px-4 py-2 bg-purple-100 rounded-full text-sm text-purple-800 mb-6">
              <span>#1 Organic marketing platform in Nigeria</span> 
              <span>🎵</span>
            </div>
            
            <h1 class="text-3xl sm:text-4xl md:text-5xl lg:text-6xl font-bold text-[#2A0B4D] mb-4 sm:mb-6">
              Boost your <span class="text-[#8B5CF6]">Campaign</span>
            </h1>
            
            <p class="text-gray-600 text-lg mb-8 max-w-2xl">
              Elevate your music or brand by connecting with creators, or earn money by creating promotional videos for artistes and brands
            </p>
            
            <div class="flex flex-col sm:flex-row gap-3 sm:gap-4 justify-center lg:justify-start w-full sm:w-auto">
              <button class="bg-[#8B5CF6] text-white px-6 py-3 rounded-lg hover:bg-[#7C3AED] transition-colors">
                Create a Task
              </button>
              <button class="border border-[#8B5CF6] text-[#8B5CF6] px-6 py-3 rounded-lg hover:bg-purple-50 transition-colors">
                Perform a Task
              </button>
            </div>
          </div>
  
          <!-- Image -->
          <div class="flex-1 relative">
            <img 
            src="../../assets/images/png/hero.png" 
              alt="Person gesturing" 
              class="w-full h-auto rounded-2xl shadow-lg"
            />
            <!-- Engagement Indicators -->
            <div class="absolute top-4 right-4 bg-white p-3 rounded-xl shadow-lg flex items-center gap-2">
              <EyeIcon class="w-5 h-5 text-gray-600" />
              <span class="text-sm font-medium">640 views</span>
            </div>
            <div class="absolute bottom-4 right-4 bg-white p-3 rounded-xl shadow-lg flex items-center gap-2">
              <HeartIcon class="w-5 h-5 text-red-500" />
              <span class="text-sm font-medium">2,048 likes</span>
            </div>
            <div class="absolute bottom-4 left-4 bg-white p-3 rounded-xl shadow-lg">
              <span class="text-sm font-medium">Boost your engagement</span>
            </div>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script setup>
  import { EyeIcon, HeartIcon } from 'lucide-vue-next'
  </script>
  
  