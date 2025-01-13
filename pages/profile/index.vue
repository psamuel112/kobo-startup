<template>
    <div class="flex flex-col lg:flex-row gap-8">
      <!-- Settings Sidebar -->
      <div class="w-full lg:w-64 lg:shrink-0">
        <h2 class="text-xl font-semibold mb-4">Settings</h2>
        <div class="flex lg:flex-col gap-2 lg:gap-1 overflow-x-auto lg:overflow-visible pb-4 lg:pb-0">
          <button 
            @click="currentView = 'profile'"
            :class="[
              'whitespace-nowrap px-4 py-2 rounded-lg text-left flex-shrink-0 lg:flex-shrink',
              currentView === 'profile' 
                ? 'text-[#8B5CF6] bg-[#8B5CF6]/10 hover:bg-[#8B5CF6]/20'
                : 'text-gray-700 hover:bg-gray-100'
            ]"
          >
            My Profile
          </button>
          <button 
            @click="currentView = 'security'"
            :class="[
              'whitespace-nowrap px-4 py-2 rounded-lg text-left flex-shrink-0 lg:flex-shrink',
              currentView === 'security' 
                ? 'text-[#8B5CF6] bg-[#8B5CF6]/10 hover:bg-[#8B5CF6]/20'
                : 'text-gray-700 hover:bg-gray-100'
            ]"
          >
            Security
          </button>
        </div>
        <button 
          @click="confirmDelete"
          class="w-full mt-4 lg:mt-8 px-4 py-2 text-left text-red-600 bg-red-50 rounded-lg hover:bg-red-100"
        >
          Delete Account
        </button>
      </div>
  
      <!-- Main Content -->
      <div class="flex-1">
        <Profile v-if="currentView === 'profile'" />
        <Security v-if="currentView === 'security'" />
      </div>
    </div>
  </template>
  <script setup>
  import { ref } from 'vue'
  import Profile from '~/components/profile/profile.vue'
  import Security from '~/components/profile/security.vue'
  
  const currentView = ref('profile')
  
  const confirmDelete = () => {
    if (confirm('Are you sure you want to delete your account? This action cannot be undone.')) {
      console.log('Delete account')
    }
  }
  </script>
  
  