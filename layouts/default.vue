<template>
    <div class="flex min-h-screen bg-gray-100">
      <Sidebar :isSidebarOpen="isSidebarOpen" @close="closeSidebar" @campaignClick="handleCampaignClick" />
  
      <!-- Main content wrapper -->
      <div class="flex-1 flex flex-col lg:ml-64">
        <!-- Navbar -->
        <Navbar />
  
        <!-- Mobile menu button - always visible and above sidebar -->
        <button 
          @click="toggleSidebar"
          class="fixed top-4 left-4 z-50 lg:hidden bg-white p-2 rounded-lg shadow-md"
          :class="{ 'left-[17rem]': isSidebarOpen }"
        >
          <MenuIcon v-if="!isSidebarOpen" class="w-6 h-6 text-[#2A0B4D]" />
          <XIcon v-else class="w-6 h-6 text-[#2A0B4D]" />
        </button>
  
        <!-- Main content -->
        <main class="flex-1 p-6">
          <slot :showCampaigns="showCampaigns" />
        </main>
  
        <!-- Mobile sidebar backdrop -->
        <div 
          v-if="isSidebarOpen" 
          class="fixed inset-0 bg-black/50 z-30 lg:hidden"
          @click="closeSidebar"
        />
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  import { MenuIcon, XIcon } from 'lucide-vue-next'
  import Sidebar from '../components/common/sidebar.vue'
  import Navbar from '../components/common/navbar.vue'
  
  const isSidebarOpen = ref(false)
  const showCampaigns = ref(false)
  
  const toggleSidebar = () => {
    isSidebarOpen.value = !isSidebarOpen.value
  }
  
  const closeSidebar = () => {
    isSidebarOpen.value = false
  }
  
  const handleCampaignClick = () => {
    showCampaigns.value = true
  }
  </script>
  
  