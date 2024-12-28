<template>
    <div class="min-h-screen bg-white p-6">
      <div class="max-w-md mx-auto pt-16">
        <h1 class="text-4xl font-bold text-gray-800 mb-2">Get Started</h1>
        <p class="text-gray-600 mb-8">Create your account now</p>
  
        <!-- Google Sign In -->
        <button 
          class="w-full bg-gray-100 rounded-full py-3 px-4 flex items-center justify-center gap-2 mb-8 hover:bg-gray-50 transition-colors"
        >
          <img 
            src="https://www.google.com/favicon.ico" 
            alt="Google" 
            class="w-5 h-5"
          />
          <span class="text-gray-700">Continue with Google</span>
        </button>
  
        <form @submit.prevent="handleSubmit" class="space-y-4">
          <div>
            <label for="fullName" class="block text-sm font-medium text-gray-700 mb-1">Full name</label>
            <input
              id="fullName"
             data-allow-mismatch="" v-model="fullName"
              type="text"
              placeholder="John Doe"
              class="w-full border border-gray-300 rounded-[8px] py-3 px-4 text-gray-900 placeholder-gray-500 outline-none focus:ring-2 focus:ring-[#8B5CF6]"
              required
            />
          </div>
  
          <div>
            <label for="email" class="block text-sm font-medium text-gray-700 mb-1">Email address</label>
            <input
              id="email"
              v-model="email"
              type="email"
              placeholder="e.g. 123@kiru.com"
              class="w-full border border-gray-300 rounded-[8px] py-3 px-4 text-gray-900 placeholder-gray-500 outline-none focus:ring-2 focus:ring-[#8B5CF6]"
              required
            />
          </div>
  
          <div>
            <label for="password" class="block text-sm font-medium text-gray-700 mb-1">Password</label>
            <div class="relative">
              <input
                id="password"
                v-model="password"
                :type="showPassword ? 'text' : 'password'"
                placeholder="••••••••••"
                class="w-full border border-gray-300 rounded-[8px] py-3 px-4 text-gray-900 placeholder-gray-500 outline-none focus:ring-2 focus:ring-[#8B5CF6]"
                required
              />
              <button 
                type="button"
                @click="showPassword = !showPassword"
                class="absolute right-4 top-1/2 -translate-y-1/2 text-gray-500"
              >
                <EyeIcon v-if="!showPassword" class="w-5 h-5" />
                <EyeOffIcon v-else class="w-5 h-5" />
              </button>
            </div>
          </div>
  
          <div>
            <label for="confirmPassword" class="block text-sm font-medium text-gray-700 mb-1">Confirm Password</label>
            <div class="relative">
              <input
                id="confirmPassword"
                v-model="confirmPassword"
                :type="showConfirmPassword ? 'text' : 'password'"
                placeholder="••••••••••"
                class="w-full border border-gray-300 rounded-[8px] py-3 px-4 text-gray-900 placeholder-gray-500 outline-none focus:ring-2 focus:ring-[#8B5CF6]"
                required
              />
              <button 
                type="button"
                @click="showConfirmPassword = !showConfirmPassword"
                class="absolute right-4 top-1/2 -translate-y-1/2 text-gray-500"
              >
                <EyeIcon v-if="!showConfirmPassword" class="w-5 h-5" />
                <EyeOffIcon v-else class="w-5 h-5" />
              </button>
            </div>
          </div>
  
          <button 
            type="submit"
            class="w-full bg-[#8726E1] text-white rounded-full py-3 px-4 font-medium hover:bg-[#7C3AED] transition-colors"
          >
            Create an Account
          </button>
        </form>
  
        <p class="text-center mt-6 text-gray-600">
          Already own an account? 
          <a href="/auth/login" class="text-[#8B5CF6] hover:text-[#7C3AED]">Login</a>
        </p>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  import { EyeIcon, EyeOffIcon } from 'lucide-vue-next'
  
  const fullName = ref('')
  const email = ref('')
  const password = ref('')
  const confirmPassword = ref('')
  const showPassword = ref(false)
  const showConfirmPassword = ref(false)
  
  const handleSubmit = () => {
    if (password.value !== confirmPassword.value) {
      alert('Passwords do not match')
      return
    }
    // Handle form submission
    console.log('Form submitted:', {
      fullName: fullName.value,
      email: email.value,
      password: password.value
    })
  }
  </script>
  
  