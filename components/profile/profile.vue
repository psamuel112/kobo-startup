<template>
    <div>
      <h1 class="text-2xl font-semibold mb-8">My Profile</h1>
  
      <!-- Profile Picture Section -->
      <div class="flex flex-col sm:flex-row items-center gap-4 mb-8">
        <div class="relative">
          <img 
            :src="profilePicture || '/placeholder.svg?height=96&width=96'" 
            alt="Profile picture"
            class="w-24 h-24 rounded-full object-cover"
          />
        </div>
        <div class="flex flex-wrap justify-center sm:justify-start gap-2">
          <label class="cursor-pointer">
            <input 
              type="file" 
              class="hidden" 
              accept="image/*"
              @change="handleImageUpload"
            />
            <span class="inline-block px-4 py-2 bg-[#8B5CF6] text-white rounded-lg hover:bg-[#7C3AED]">
              Change Picture
            </span>
          </label>
          <button 
            @click="deletePicture"
            class="px-4 py-2 text-gray-600 hover:text-gray-800"
          >
            Delete Picture
          </button>
        </div>
      </div>
  
      <!-- Personal Information -->
      <div class="bg-white rounded-lg p-4 sm:p-6">
        <div class="flex flex-col sm:flex-row sm:items-center justify-between mb-6 gap-4">
          <h2 class="text-lg font-semibold">Personal Information</h2>
          <button 
            @click="showEditModal"
            class="text-[#8B5CF6] hover:text-[#7C3AED]"
          >
            Edit details
          </button>
        </div>
  
        <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 sm:gap-x-8 sm:gap-y-6">
          <!-- First Name -->
          <div>
            <label class="block text-sm text-gray-600 mb-1">First name</label>
            <div class="text-gray-900">{{ profileData.firstName }}</div>
          </div>
  
          <!-- Last Name -->
          <div>
            <label class="block text-sm text-gray-600 mb-1">Last name</label>
            <div class="text-gray-900">{{ profileData.lastName }}</div>
          </div>
  
          <!-- Email -->
          <div>
            <label class="block text-sm text-gray-600 mb-1">Email address</label>
            <div class="text-gray-900 break-all">{{ profileData.email }}</div>
          </div>
  
          <!-- Phone -->
          <div>
            <label class="block text-sm text-gray-600 mb-1">Phone number</label>
            <div class="text-gray-900">{{ profileData.phone }}</div>
          </div>
  
          <!-- Location -->
          <div>
            <label class="block text-sm text-gray-600 mb-1">Location</label>
            <div class="text-gray-900">{{ profileData.location }}</div>
          </div>
  
          <!-- Job Title -->
          <div>
            <label class="block text-sm text-gray-600 mb-1">Job Title</label>
            <div class="text-gray-900">{{ profileData.jobTitle }}</div>
          </div>
        </div>
      </div>
  
      <!-- Edit Profile Modal -->
      <EditProfileModal 
        :is-open="isEditModalOpen"
        :initial-data="profileData"
        @close="closeEditModal"
        @update="updateProfile"
      />
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  import EditProfileModal from './editProfileModal.vue'
  
  const profilePicture = ref(null)
  const isEditModalOpen = ref(false)
  
  const profileData = ref({
    firstName: 'Anthony',
    lastName: 'Modebe',
    email: 'anthony@abc.com',
    location: 'JohnDoe Company',
    phone: '1-10',
    jobTitle: 'Hr Specailist'
  })
  
  const handleImageUpload = (event) => {
    const file = event.target.files[0]
    if (file) {
      const reader = new FileReader()
      reader.onload = (e) => {
        profilePicture.value = e.target.result
      }
      reader.readAsDataURL(file)
    }
  }
  
  const deletePicture = () => {
    profilePicture.value = null
  }
  
  const showEditModal = () => {
    isEditModalOpen.value = true
  }
  
  const closeEditModal = () => {
    isEditModalOpen.value = false
  }
  
  const updateProfile = (newData) => {
    profileData.value = newData
  }
  </script>
  
  