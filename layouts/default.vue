<template>
    <div class="flex min-h-screen bg-gray-100">
      <sidebar
      v-if="!isAuthPAge"
      :isSidebarOpen="isSidebarOpen" @close="closeSidebar" />
  
      <!-- Main content wrapper -->
      <div class="flex-1 flex flex-col lg:ml-64">
        <!-- Navbar -->
        <navbar v-if="!isAuthPage" />
  
        <!-- Mobile menu button - always visible and above sidebar -->
        <button 
          @click="toggleSidebar"
          class="fixed top-4 left-4 z-50 lg:hidden "
          :class="{ 'left-[17rem]': isSidebarOpen }"
        >
          <MenuIcon v-if="!isSidebarOpen" class="w-6 h-6 text-[#2A0B4D]" />
          <XIcon v-else class="w-6 h-6 text-[#2A0B4D]" />
        </button>
  
        <!-- Main content -->
        <main class="flex-1 p-6">
          <slot />
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
 import sidebar from '~/components/common/sidebar.vue'
  import navbar from '~/components/common/navbar.vue'
  const isSidebarOpen = ref(false)
  
  const toggleSidebar = () => {
    isSidebarOpen.value = !isSidebarOpen.value
  }
  
  const closeSidebar = () => {
    isSidebarOpen.value = false
  }
  </script>
  
  