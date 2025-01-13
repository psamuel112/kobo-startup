<template>
    <footer class="bg-[#2A0B4D] text-white py-8 sm:py-12">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8">
          <!-- Logo and Copyright -->
          <div class="col-span-1 sm:col-span-2 lg:col-span-1">
            <div class="flex items-center mb-4">
              <img src="../../assets/images/svg/kobo-logo.svg" alt="Kotobask" class="h-8 w-auto" />
      
            </div>
            <p class="text-white/60 text-sm">
              ©2024 All rights reserved
            </p>
          </div>
  
          <!-- Quick Links -->
          <div>
            <h3 class="font-semibold mb-4">Quick Links</h3>
            <ul class="space-y-2">
              <li>
                <router-link to="/dashboard" class="text-white/60 hover:text-white">
                  Dashboard
                </router-link>
              </li>
              <li>
                <router-link to="/category" class="text-white/60 hover:text-white">
                  Category
                </router-link>
              </li>
              <li>
                <router-link to="/login" class="text-white/60 hover:text-white">
                  Login
                </router-link>
              </li>
            </ul>
          </div>
  
          <!-- About Us -->
          <div>
            <h3 class="font-semibold mb-4">About Us</h3>
            <ul class="space-y-2">
              <li>
                <router-link to="/about" class="text-white/60 hover:text-white">
                  About Us
                </router-link>
              </li>
              <li>
                <router-link to="/pricing" class="text-white/60 hover:text-white">
                  Pricing
                </router-link>
              </li>
              <li>
                <router-link to="/blog" class="text-white/60 hover:text-white">
                  Blog
                </router-link>
              </li>
            </ul>
          </div>
  
          <!-- Contact Info -->
          <div>
            <h3 class="font-semibold mb-4">Contact Us</h3>
            <ul class="space-y-2">
              <li class="text-white/60">+234 567 890</li>
              <li class="text-white/60">info@kotobask.com</li>
            </ul>
            <!-- Social Links -->
            <div class="flex gap-4 mt-4">
              <a href="#" class="text-white/60 hover:text-white">
                <FacebookIcon class="w-5 h-5" />
              </a>
              <a href="#" class="text-white/60 hover:text-white">
                <TwitterIcon class="w-5 h-5" />
              </a>
              <a href="#" class="text-white/60 hover:text-white">
                <InstagramIcon class="w-5 h-5" />
              </a>
              <a href="#" class="text-white/60 hover:text-white">
                <LinkedinIcon class="w-5 h-5" />
              </a>
            </div>
          </div>
        </div>
      </div>
    </footer>
  </template>
  
  <script setup>
  import { FacebookIcon, TwitterIcon, InstagramIcon, LinkedinIcon } from 'lucide-vue-next'
  </script>
  
  