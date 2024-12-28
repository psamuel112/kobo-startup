<template>
    <aside :class="[
      'fixed top-0 left-0 h-full w-64 bg-[#2A0B4D] z-40 flex flex-col transition-transform duration-300 ease-in-out',
      isSidebarOpen ? 'translate-x-0' : '-translate-x-full lg:translate-x-0'
    ]">
      <!-- Logo section -->
      <div class="p-4 flex items-center gap-2">
        <div class="w-8 h-8 bg-white/10 rounded-lg flex items-center justify-center">
          <img src="../../assets/images/svg/kobo-logo.svg" alt="Kobotask" class="w-5 h-5" />
        </div>
        <h1 class="text-white text-xl font-bold">KOBOTASK</h1>
      </div>
  
      <!-- Navigation -->
      <nav class="flex-1 px-2 py-4">
        <ul class="space-y-2">
          <li>
            <a 
              href="/" 
              class="flex items-center gap-3 px-4 py-2 rounded-lg text-white bg-white/10 hover:bg-white/20 transition-colors"
            >
              <HomeIcon class="w-5 h-5" />
              <span>Home</span>
            </a>
          </li>
          <li>
            <a 
              href="/profile" 
              class="flex items-center gap-3 px-4 py-2 rounded-lg text-white hover:bg-white/10 transition-colors"
            >
              <UserIcon class="w-5 h-5" />
              <span>Profile</span>
            </a>
          </li>
        </ul>
      </nav>
  
      <!-- Create Campaign Button -->
      <div class="px-4 mb-4">
        <button 
          @click="createCampaign"
          class="w-full flex items-center justify-center gap-2 px-4 py-3 rounded-lg bg-white/10 text-white hover:bg-white/20 transition-colors"
        >
          <PlusIcon class="w-5 h-5" />
          <span>Create a campaign</span>
        </button>
      </div>
  
      <!-- Logout Button -->
      <div class="px-4 mb-6">
        <button 
          @click="logout"
          class="w-full flex items-center justify-center gap-2 px-4 py-3 rounded-lg bg-red-50 text-red-600 hover:bg-red-100 transition-colors"
        >
          <LogOutIcon class="w-5 h-5" />
          <span>Log out</span>
        </button>
      </div>
    </aside>
  </template>
  
  <script setup>
  import { HomeIcon, UserIcon, PlusIcon, LogOutIcon } from 'lucide-vue-next'
  
  defineProps({
    isSidebarOpen: {
      type: Boolean,
      required: true
    }
  })
  
  const createCampaign = () => {
    // Implement create campaign logic here
    console.log('Creating a new campaign')
  }
  
  const logout = () => {
    // Implement logout logic here
    console.log('Logging out')
  }
  </script>
  
  