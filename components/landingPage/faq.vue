<template>
    <section class="py-12 sm:py-16 bg-[#2A0B4D]">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 lg:gap-12">
          <!-- Left Column -->
          <div class="text-white">
            <h2 class="text-2xl sm:text-3xl font-bold mb-4">Check Our FAQs</h2>
            <p class="text-white/80 mb-6">
              Have any questions about our platform? Check our FAQ section first to get you covered with helpful information on all of our offerings.
            </p>
            <p class="text-white/80 mb-6">
              Do you have any questions or could not find what you're looking for?
            </p>
            <button class="border border-white/20 text-white px-6 py-3 rounded-lg hover:bg-white/10 transition-colors">
              Contact us
            </button>
          </div>
  
          <!-- Right Column - FAQ Accordion -->
          <div class="space-y-4">
            <div v-for="(faq, index) in faqs" :key="index" class="bg-white/5 rounded-lg overflow-hidden">
              <button
                @click="toggleFaq(index)"
                class="w-full flex justify-between items-center p-4 text-white text-left"
              >
                <span>{{ faq.question }}</span>
                <ChevronDownIcon 
                  class="w-5 h-5 transition-transform"
                  :class="{ 'rotate-180': faq.isOpen }"
                />
              </button>
              <div 
                v-show="faq.isOpen"
                class="p-4 pt-0 text-white/80"
              >
                {{ faq.answer }}
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  import { ChevronDownIcon } from 'lucide-vue-next'
  
  const faqs = ref([
    {
      question: 'How do I earn money?',
      answer: 'You can earn money by completing tasks posted by other users, such as promoting content, creating videos, or engaging with posts.',
      isOpen: false
    },
    {
      question: 'How do I post tasks?',
      answer: 'After creating an account, you can post tasks by clicking the "Create a Task" button and following the simple setup process.',
      isOpen: false
    },
    {
      question: 'How are payments handled?',
      answer: 'Payments are securely processed through our platform. Funds are held in escrow until tasks are completed and approved.',
      isOpen: false
    },
    {
      question: 'What types of tasks can I create?',
      answer: 'You can create various types of tasks including content promotion, music promotion, and brand awareness campaigns.',
      isOpen: false
    },
    {
      question: 'How long does task approval take?',
      answer: 'Task approval typically takes 24-48 hours after submission, ensuring quality and compliance with our guidelines.',
      isOpen: false
    }
  ])
  
  const toggleFaq = (index) => {
    faqs.value[index].isOpen = !faqs.value[index].isOpen
  }
  </script>
  
  