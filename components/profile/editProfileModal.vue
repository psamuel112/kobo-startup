<template>
    <div v-if="isOpen" class="fixed inset-0 z-50 overflow-y-auto">
      <!-- Backdrop -->
      <div 
        class="fixed inset-0 bg-black bg-opacity-50 transition-opacity"
        @click="close"
      ></div>
  
      <!-- Modal -->
      <div class="flex min-h-full items-center justify-center p-4">
        <div class="relative w-full max-w-md bg-white rounded-lg shadow-xl">
          <!-- Header -->
          <div class="flex items-center justify-between p-4 border-b">
            <h3 class="text-lg font-semibold">Edit Profile</h3>
            <button 
              @click="close"
              class="text-gray-400 hover:text-gray-500"
            >
              <XIcon class="w-5 h-5" />
            </button>
          </div>
  
          <!-- Form -->
          <form @submit.prevent="handleSubmit" class="p-4 space-y-4">
            <!-- Name Fields -->
            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
              <div>
                <label class="block text-sm font-medium text-gray-700 mb-1">
                  First name
                </label>
                <input 
                  v-model="form.firstName"
                  type="text"
                  class="w-full px-3 py-2 border rounded-lg focus:ring-2 focus:ring-[#8B5CF6] focus:border-transparent"
                  placeholder="John"
                />
              </div>
              <div>
                <label class="block text-sm font-medium text-gray-700 mb-1">
                  Last name
                </label>
                <input 
                  v-model="form.lastName"
                  type="text"
                  class="w-full px-3 py-2 border rounded-lg focus:ring-2 focus:ring-[#8B5CF6] focus:border-transparent"
                  placeholder="Doe"
                />
              </div>
            </div>
  
            <!-- Work Email -->
            <div>
              <label class="block text-sm font-medium text-gray-700 mb-1">
                Work Email
              </label>
              <input 
                v-model="form.email"
                type="email"
                class="w-full px-3 py-2 border rounded-lg focus:ring-2 focus:ring-[#8B5CF6] focus:border-transparent"
                placeholder="johndoe@company.com"
              />
            </div>
  
            <!-- Location -->
            <div>
              <label class="block text-sm font-medium text-gray-700 mb-1">
                Location
              </label>
              <input 
                v-model="form.location"
                type="text"
                class="w-full px-3 py-2 border rounded-lg focus:ring-2 focus:ring-[#8B5CF6] focus:border-transparent"
                placeholder="JohnDoe Company"
              />
            </div>
  
            <!-- Phone Number -->
            <div>
              <label class="block text-sm font-medium text-gray-700 mb-1">
                Phone number
              </label>
              <select 
                v-model="form.phone"
                class="w-full px-3 py-2 border rounded-lg focus:ring-2 focus:ring-[#8B5CF6] focus:border-transparent appearance-none bg-white"
              >
                <option value="1-10">1-10</option>
                <option value="11-20">11-20</option>
                <option value="21-30">21-30</option>
              </select>
            </div>
  
            <!-- Job Title -->
            <div>
              <label class="block text-sm font-medium text-gray-700 mb-1">
                Job Title
              </label>
              <select 
                v-model="form.jobTitle"
                class="w-full px-3 py-2 border rounded-lg focus:ring-2 focus:ring-[#8B5CF6] focus:border-transparent appearance-none bg-white"
              >
                <option value="Hr Specailist">Hr Specailist</option>
                <option value="Developer">Developer</option>
                <option value="Designer">Designer</option>
              </select>
            </div>
  
            <!-- Submit Button -->
            <button 
              type="submit"
              class="w-full py-2 px-4 bg-[#8B5CF6] text-white rounded-lg hover:bg-[#7C3AED] transition-colors"
            >
              Update Profile
            </button>
          </form>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  import { XIcon } from 'lucide-vue-next'
  
  const props = defineProps({
    isOpen: {
      type: Boolean,
      required: true
    },
    initialData: {
      type: Object,
      default: () => ({
        firstName: '',
        lastName: '',
        email: '',
        location: '',
        phone: '1-10',
        jobTitle: 'Hr Specailist'
      })
    }
  })
  
  const emit = defineEmits(['close', 'update'])
  
  const form = ref({ ...props.initialData })
  
  const close = () => {
    emit('close')
  }
  
  const handleSubmit = () => {
    emit('update', form.value)
    close()
  }
  </script>
  
  