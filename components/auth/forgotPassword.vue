<template>
    <div class="min-h-screen">
        <div class=" bg-white flex items-center  justify-center p-6">
            <div class="w-full max-w-lg rounded-[16px] p-6 ">
                <div class="flex relative items-center justify-center mt-8 mb-6">
                    <img src="../../assets/images/svg/key.svg" class="" />
                </div>
                <h1 class="text-4xl font-bold text-gray-800 mb-2 text-center">Forgot Password?</h1>
                <p class="text-gray-600 mb-8 text-center">You don’t need to worry, We will send a reset instructions</p>
                <form @submit.prevent="handleSubmit" class="space-y-4 ">
                    <div class="">
                        <label for="email" class="block text-sm font-medium  text-gray-700 mb-1">Email address</label>
                        <input v-model="email" type="email" placeholder="e.g. 123@kiru.com"
                            class="w-full bg-gray-100 mb-6 border border-gray-300 rounded-[8px] py-3 px-4 text-gray-900 placeholder-gray-500 outline-none focus:ring-2 focus:ring-[#8B5CF6]"
                            required />
                    </div>
                    <button type="submit"
                        class="w-full bg-[#8726E1] text-white rounded-full py-3 px-4 font-medium hover:bg-[#7C3AED] transition-colors">
                        Log In
                    </button>
                </form>
                <div class="flex justify-center mt-8">
                    <a href="/auth/login" class="text-[#8B5CF6] font-bold  hover:text-[#7C3AED]">&larr; Back to login
                        page</a>
                </div>

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