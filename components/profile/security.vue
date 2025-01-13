<template>
    <div>
      <h1 class="text-2xl font-semibold mb-8">Security</h1>
  
      <div class="bg-white rounded-lg p-6">
        <div class="space-y-8">
          <!-- Change Password Section -->
          <div>
            <h2 class="text-lg font-semibold mb-4">Change Password</h2>
            <form @submit.prevent="changePassword" class="space-y-4 max-w-md">
              <div>
                <label class="block text-sm text-gray-600 mb-1">Current Password</label>
                <input 
                  type="password"
                  v-model="currentPassword"
                  class="w-full px-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-[#8B5CF6] focus:border-transparent"
                  required
                />
              </div>
              <div>
                <label class="block text-sm text-gray-600 mb-1">New Password</label>
                <input 
                  type="password"
                  v-model="newPassword"
                  class="w-full px-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-[#8B5CF6] focus:border-transparent"
                  required
                />
              </div>
              <div>
                <label class="block text-sm text-gray-600 mb-1">Confirm New Password</label>
                <input 
                  type="password"
                  v-model="confirmPassword"
                  class="w-full px-4 py-2 rounded-lg border border-gray-300 focus:ring-2 focus:ring-[#8B5CF6] focus:border-transparent"
                  required
                />
              </div>
              <button 
                type="submit"
                class="px-4 py-2 bg-[#8B5CF6] text-white rounded-lg hover:bg-[#7C3AED]"
              >
                Update Password
              </button>
            </form>
          </div>
  
          <!-- Two Factor Authentication -->
          <div>
            <h2 class="text-lg font-semibold mb-4">Two-Factor Authentication</h2>
            <p class="text-gray-600 mb-4">Add an extra layer of security to your account</p>
            <button 
              @click="setupTwoFactor"
              class="px-4 py-2 border border-[#8B5CF6] text-[#8B5CF6] rounded-lg hover:bg-[#8B5CF6] hover:text-white"
            >
              Setup 2FA
            </button>
          </div>
  
          <!-- Active Sessions -->
          <div>
            <h2 class="text-lg font-semibold mb-4">Active Sessions</h2>
            <div class="space-y-4">
              <div v-for="session in activeSessions" :key="session.id" class="flex items-center justify-between p-4 bg-gray-50 rounded-lg">
                <div>
                  <div class="font-medium">{{ session.device }}</div>
                  <div class="text-sm text-gray-600">{{ session.location }} • {{ session.lastActive }}</div>
                </div>
                <button 
                  @click="terminateSession(session.id)"
                  class="text-red-600 hover:text-red-800"
                >
                  Terminate
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  
  const currentPassword = ref('')
  const newPassword = ref('')
  const confirmPassword = ref('')
  
  const activeSessions = ref([
    {
      id: 1,
      device: 'Chrome on Windows',
      location: 'Lagos, Nigeria',
      lastActive: 'Active now'
    },
    {
      id: 2,
      device: 'Safari on iPhone',
      location: 'Lagos, Nigeria',
      lastActive: 'Last active 2 hours ago'
    }
  ])
  
  const changePassword = () => {
    if (newPassword.value !== confirmPassword.value) {
      alert('New passwords do not match')
      return
    }
    // Implement password change logic
    console.log('Changing password')
  }
  
  const setupTwoFactor = () => {
    // Implement 2FA setup logic
    console.log('Setting up 2FA')
  }
  
  const terminateSession = (sessionId) => {
    // Implement session termination logic
    console.log('Terminating session:', sessionId)
    activeSessions.value = activeSessions.value.filter(session => session.id !== sessionId)
  }
  </script>
  
  