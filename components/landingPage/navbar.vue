<template>
    <nav class="fixed top-0 left-0 right-0 bg-white z-50 border-b border-gray-100">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between h-16 items-center">
          <!-- Logo -->
          <div class="flex-shrink-0">
            <router-link to="/" class="flex items-center">
                <img src="../../assets/images/svg/kobo-logo.svg" alt="Kotobask" class="h-8 w-auto" />
            
            </router-link>
          </div>
  
          <!-- Navigation Links - Desktop -->
          <div class="hidden md:flex items-center space-x-8">
            <router-link to="/earn-money" class="text-gray-600 hover:text-gray-900">
              Earn Money
            </router-link>
            <router-link to="/perform-tasks" class="text-gray-600 hover:text-gray-900">
              Perform Tasks
            </router-link>
            <router-link to="/contact" class="text-gray-600 hover:text-gray-900">
              Contact Us
            </router-link>
          </div>
  
          <!-- Auth Buttons -->
          <div class="hidden md:flex items-center space-x-4">
            <router-link 
              to="/auth/login"
              class="text-[#8B5CF6] hover:text-[#7C3AED] px-4 py-2 rounded-lg"
            >
              Login
            </router-link>
            <router-link 
              to="/auth/register"
              class="bg-[#8B5CF6] text-white px-4 py-2 rounded-lg hover:bg-[#7C3AED]"
            >
              Sign Up
            </router-link>
          </div>
  
          <!-- Mobile Menu Button -->
          <div class="md:hidden flex items-center">
            <button 
              @click="isOpen = !isOpen"
              class="text-gray-500 hover:text-gray-600 p-2 -mr-2"
            >
              <MenuIcon v-if="!isOpen" class="h-6 w-6" />
              <XIcon v-else class="h-6 w-6" />
            </button>
          </div>
        </div>
      </div>
  
      <!-- Mobile Menu -->
      <div 
        v-if="isOpen" 
        class="md:hidden absolute top-16 left-0 right-0 bg-white border-b border-gray-100 shadow-lg"
      >
        <div class="px-4 py-3 space-y-2">
          <router-link 
            to="/earn-money"
            class="block px-3 py-2 rounded-md text-gray-600 hover:text-gray-900 hover:bg-gray-50"
          >
            Earn Money
          </router-link>
          <router-link 
            to="/perform-tasks"
            class="block px-3 py-2 rounded-md text-gray-600 hover:text-gray-900 hover:bg-gray-50"
          >
            Perform Tasks
          </router-link>
          <router-link 
            to="/contact"
            class="block px-3 py-2 rounded-md text-gray-600 hover:text-gray-900 hover:bg-gray-50"
          >
            Contact Us
          </router-link>
          <div class="px-4 py-3 space-y-2 border-t border-gray-100">
            <router-link 
              to="/auth/login"
              class="block text-[#8B5CF6] hover:text-[#7C3AED] px-3 py-2 rounded-lg"
            >
              Login
            </router-link>
            <router-link 
              to="/auth/register"
              class="block bg-[#8B5CF6] text-white px-3 py-2 rounded-lg hover:bg-[#7C3AED] text-center"
            >
              Sign Up
            </router-link>
          </div>
        </div>
      </div>
    </nav>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  import { MenuIcon, XIcon } from 'lucide-vue-next'
  
  const isOpen = ref(false)
  </script>
  
  