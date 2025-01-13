<template>
    <div v-if="isOpen" class="fixed inset-0 z-50 overflow-y-auto">
      <!-- Backdrop -->
      <div 
        class="fixed inset-0 bg-black bg-opacity-50 transition-opacity"
        @click="close"
      ></div>
  
      <!-- Modal -->
      <div class="flex min-h-full items-center justify-center p-4">
        <div class="relative w-full max-w-2xl bg-white rounded-2xl shadow-xl">
          <!-- Header -->
          <div class="p-6">
            <div class="flex justify-between items-start">
              <div>
                <h2 class="text-2xl font-semibold text-gray-900">Campaign type</h2>
                <p class="mt-1 text-gray-600">What type of campaign would you like to create?</p>
              </div>
              <button 
                @click="close"
                class="text-gray-400 hover:text-gray-500"
              >
                <XIcon class="w-6 h-6" />
              </button>
            </div>
          </div>
  
          <!-- Content -->
          <div class="px-6 pb-6">
            <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-4">
              <!-- Promote Content Card -->
              <button 
                @click="selectType('content')"
                class="group p-6 bg-gray-50 rounded-xl hover:bg-gray-100 transition-colors text-left"
              >
                <div class="w-10 h-10 bg-[#8B5CF6] rounded-lg flex items-center justify-center mb-4">
                  <Megaphone class="w-5 h-5 text-white" />
                </div>
                <h3 class="text-lg font-medium text-gray-900 mb-2">Promote your Content</h3>
                <p class="text-gray-600 text-sm">Create task to be completed by users</p>
              </button>
  
              <!-- Promote Music Card -->
              <button 
                @click="selectType('music')"
                class="group p-6 bg-gray-50 rounded-xl hover:bg-gray-100 transition-colors text-left"
              >
                <div class="w-10 h-10 bg-[#8B5CF6] rounded-lg flex items-center justify-center mb-4">
                  <Megaphone class="w-5 h-5 text-white" />
                </div>
                <h3 class="text-lg font-medium text-gray-900 mb-2">Promote your Music</h3>
                <p class="text-gray-600 text-sm">Create task to be completed by users</p>
              </button>
  
              <!-- Promote Business Card -->
              <button 
                @click="selectType('business')"
                class="group p-6 bg-gray-50 rounded-xl hover:bg-gray-100 transition-colors text-left"
              >
                <div class="w-10 h-10 bg-[#8B5CF6] rounded-lg flex items-center justify-center mb-4">
                  <Megaphone class="w-5 h-5 text-white" />
                </div>
                <h3 class="text-lg font-medium text-gray-900 mb-2">Promote your Business</h3>
                <p class="text-gray-600 text-sm">Create task to be completed by users</p>
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { XIcon, Megaphone } from 'lucide-vue-next'
  
  const props = defineProps({
    isOpen: {
      type: Boolean,
      required: true
    }
  })
  
  const emit = defineEmits(['close', 'select'])
  
  const close = () => {
    emit('close')
  }
  
  const selectType = (type) => {
    emit('select', type)
    close()
  }
  </script>
  
  