<template>
    <div class=" min-h-screen">
        <div class="flex relative justify-center mt-8 mb-6">
            <img src="../../assets/images/svg/kobo-logo.svg" class=""/>
        </div>
        <div class=" bg-white flex items-center  justify-center p-6">
            <div class="w-full max-w-lg rounded-[16px] border p-6 border-gray-300">
                <h1 class="text-4xl font-bold text-gray-800 mb-2 text-center">Welcome back!</h1>
                <p class="text-gray-600 mb-8 text-center">Login to your account to see all pending activities.</p>

                <!-- Social Login Buttons -->
                <div class="grid grid-cols-2 gap-4 mb-8">
                    <button
                        class="flex items-center justify-center gap-2 px-4 py-3 border border-gray-300 rounded-[8px] hover:bg-gray-50 transition-colors">
                        <img src="https://www.google.com/favicon.ico" alt="Google" class="w-5 h-5" />
                        <span class="text-gray-700 text-sm">Sign in with Google</span>
                    </button>

                    <button
                        class="flex items-center justify-center gap-2 px-4 py-3 border border-gray-300 rounded-[8px] hover:bg-gray-50 transition-colors">
                        <img src="https://facebook.com/favicon.ico" alt="Facebook" class="w-5 h-5" />
                        <span class="text-gray-700 text-sm">Sign in with facebook</span>
                    </button>
                </div>

                <div class="mb-6 flex item-center justify-center">
                    <div class="w-1/2 border-t border-gray-300"></div>
                </div>

                <form @submit.prevent="handleSubmit" class="space-y-4 ">
                    <div class="">
                        <label for="email" class="block text-sm font-medium  text-gray-700 mb-1">Username</label>
                        <input v-model="email" type="email" placeholder="e.g. 123@kiru.com"
                            class="w-full bg-gray-100 border border-gray-300 rounded-[8px] py-3 px-4 text-gray-900 placeholder-gray-500 outline-none focus:ring-2 focus:ring-[#8B5CF6]"
                            required />
                    </div>

                    <div>
                        <label for="password" class="block text-sm font-medium text-gray-700 mb-1">Password</label>
                        <div class="relative">
                            <input id="password" v-model="password" :type="showPassword ? 'text' : 'password'"
                                placeholder="••••••••••"
                                class="w-full border border-gray-300 rounded-[8px] py-3 px-4 text-gray-900 placeholder-gray-500 outline-none focus:ring-2 focus:ring-[#8B5CF6]"
                                required />
                            <button type="button" @click="showPassword = !showPassword"
                                class="absolute right-4 top-1/2 -translate-y-1/2 text-gray-500">
                                <EyeIcon v-if="!showPassword" class="w-5 h-5" />
                                <EyeOffIcon v-else class="w-5 h-5" />
                            </button>
                        </div>
                    </div>

                    <a href="/auth/forgotPassword" class="block text-[#8B5CF6] text-sm hover:text-[#7C3AED]">
                        Don't remember your Password?
                    </a>

                    <router-link to="/dashboard" class="text-gray-600 hover:text-gray-900"><button type="submit"
                        class="w-full bg-[#8726E1] text-white rounded-full py-3 px-4 font-medium hover:bg-[#7C3AED] transition-colors">
                        Log In
                    </button>
                </router-link> 
                </form>

                <p class="text-center mt-6 text-gray-600">
                    Don't have an account?
                    <a href="/auth/register" class="text-[#8B5CF6] hover:text-[#7C3AED]">Create an Account</a>
                </p>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'
import { EyeIcon, EyeOffIcon } from 'lucide-vue-next'

const email = ref('')
const password = ref('')
const showPassword = ref(false)

const handleSubmit = () => {
    // Handle form submission
    console.log('Form submitted:', {
        email: email.value,
        password: password.value
    })
}
</script>