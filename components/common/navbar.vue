<template>
  <nav class="h-16 px-6 flex items-center justify-between bg-white border-b border-gray-200">
    <h1 class="text-xl ml-10 lg:ml-0 font-semibold text-gray-900">Welcome - Digital Frontals</h1>
    
    <div class="flex items-center gap-3">
      <!-- Notification Avatar -->
      <div class="relative">
        <img 
          src="../../assets/images/svg/notification.svg?height=40&width=40" 
          alt="Notifications" 
          class="w-10 h-10 rounded-full object-cover"
        />
        <span class="absolute -top-1 -right-1 flex items-center justify-center w-5 h-5 bg-red-500 text-white text-xs font-medium rounded-full">5</span>
      </div>
      
      <!-- Profile Avatar -->
      <img 
        src="../../assets/images/svg/photo.svg?height=40&width=40" 
        alt="Profile" 
        class="w-10 h-10 rounded-full object-cover"
      />
    </div>
  </nav>
</template>

