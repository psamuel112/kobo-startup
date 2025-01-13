<template>
    <div class="space-y-8">
        <!-- Balance Card -->
        <div class="bg-[#250F39] rounded-[8px] py-12 px-6">
            <div class="flex-none md:flex  items-center justify-between mb-2">
                <div class="flex items-center gap-2">
                    <h2 class="text-4xl font-bold text-white">₦1,000.00</h2>
                    <button class="text-white/70 hover:text-white">
                        <EyeIcon class="w-6 h-6" />
                    </button>
                </div>
                <button class="px-4 md:mt-0 mt-4 py-2 bg-white/10 text-white rounded-[56px] hover:bg-white/20 transition-colors">
                    Fund Wallet
                </button>
            </div>
            <p class="text-white/70">Advertising Balance</p>
        </div>

        <!-- Campaigns Section -->
        <div class="space-y-6">
            <h3 class="text-lg font-semibold">ONGOING CAMPAIGNS</h3>

            <!-- Show table if there are campaigns, otherwise show empty state -->
            <div v-if="hasCampaigns">
                <campaignTable />
            </div>

            <!-- Empty State -->
            <div v-else class="flex flex-col items-center justify-center py-16 px-4">
                <img src="../../assets/images/svg/Notask.svg" alt="No campaigns" class="w-20 h-20 mb-4 opacity-50" />
                <p class="text-gray-500 mb-6">You don't have any active campaign</p>
                <button class="flex items-center gap-2 text-[#8B5CF6] hover:text-[#7C3AED] transition-colors">
                    <PlusIcon class="w-5 h-5" />
                    <span>Create a campaign</span>
                </button>
            </div>
        </div>
        <createCampaign
      :is-open="isCreateModalOpen"
      @close="closeCreateModal"
      @select="handleCampaignTypeSelect"
    />
    </div>
</template>

<script setup>
import { ref } from 'vue'
import campaignTable from '~/components/dashboard/campaignTable.vue';
import { EyeIcon, PlusIcon } from 'lucide-vue-next'


const props = defineProps({
  showCampaigns: {
    type: Boolean,
    default: false
  }
})


const hasCampaigns = ref(false)
const isCreateModalOpen = ref(false)

const showCreateModal = () => {
  isCreateModalOpen.value = true
}

const closeCreateModal = () => {
  isCreateModalOpen.value = false
}

const handleCampaignTypeSelect = (type) => {
  console.log('Selected campaign type:', type)
  // Handle campaign type selection
  // You might want to navigate to a specific form based on the type
}
</script>