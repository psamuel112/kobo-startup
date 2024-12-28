<template>
    <div class="overflow-x-auto">
      <table class="w-full">
        <!-- Table Header -->
        <thead>
          <tr class="border-b border-gray-800">
            <th class="py-4 px-2 text-left text-sm font-medium">Description</th>
            <th class="py-4 px-2 text-left text-sm font-medium">Type</th>
            <th class="py-4 px-2 text-left text-sm font-medium">Date created</th>
            <th class="py-4 px-2 text-left text-sm font-medium">Progress</th>
            <th class="py-4 px-4 text-left text-sm font-medium">Action</th>
          </tr>
        </thead>
  
        <!-- Table Body -->
        <tbody>
          <tr v-for="(campaign, index) in campaigns" :key="index" class="border-b border-gray-800">
            <td class="py-4 px-2 ">{{ campaign.description }}</td>
            <td class="py-4 px-2 ">{{ campaign.type }}</td>
            <td class="py-4 px-2 ">{{ campaign.dateCreated }}</td>
            <td class="py-4 px-2">
              <div class="flex items-center gap-2">
                <div class="flex-1 h-2 bg-[#F0F2F5] rounded-full overflow-hidden">
                  <div 
                    class="h-full bg-[#DCA332] rounded-full"
                    :style="{ width: `${(campaign.current / campaign.total) * 100}%` }"
                  ></div>
                </div>
                <span class="text-sm ">{{ campaign.current }}/{{ campaign.total }}</span>
              </div>
            </td>
            <td class="py-4 px-4">
              <button class=" hover:text-gray-300">
                <MoreVerticalIcon class="w-5 h-5" />
              </button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </template>
  
  <script setup>
  import { MoreVerticalIcon } from 'lucide-vue-next'
  
  // Sample data - replace with actual data source
  const campaigns = [
    {
      description: 'Sign Up on our Website',
      type: 'Engagement Video',
      dateCreated: '18-10-2024',
      current: 100,
      total: 300
    },
    {
      description: 'Sign Up on our Website',
      type: 'Engagement Video',
      dateCreated: '18-10-2024',
      current: 300,
      total: 300
    },
    {
      description: 'Sign Up on our Website',
      type: 'Engagement Video',
      dateCreated: '18-10-2024',
      current: 300,
      total: 300
    }
  ]
  </script>
  
  <style scoped>
  /* Ensure smooth progress bar transitions */
  .bg-gradient-to-r {
    transition: width 0.3s ease-in-out;
  }
  </style>