<template>
    <div class="min-h-screen">
      <Navbar />
      <Hero />
      <EarnCash />
      <Process />
      <FAQ />
      <CreatorGallery />
      <Footer />
    </div>
  </template>
  
  <script setup>
  import Navbar from '../components/landingPage/navbar.vue'
  import Hero from '../components/landingPage/hero.vue'
  import EarnCash from '../components/landingPage/earnCash.vue'
  import Process from '../components/landingPage/process.vue'
  import FAQ from '../components/landingPage/faq.vue'
  import CreatorGallery from '../components/landingPage/creatorGallery.vue'
  import Footer from '../components/landingPage/footer.vue'

  definePageMeta({
  layout: 'clean',
});
  </script>
  
  