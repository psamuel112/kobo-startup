<template>
    <section class="py-12 sm:py-16 bg-[#2A0B4D] text-white">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <!-- Header -->
        <div class="flex flex-col md:flex-row justify-between items-start md:items-center gap-4 md:gap-6 mb-8 md:mb-12">
          <div>
            <div class="inline-flex items-center gap-2 px-4 py-2 bg-white/10 rounded-full text-sm mb-4">
              <span>WHAT KOTOBASK DOES</span>
            </div>
            <h2 class="text-3xl md:text-4xl font-bold">Earn cool Cash</h2>
            <p class="mt-4 text-white/80 max-w-2xl">
              Nothing beats trying your ideas out to see if they work. So we made doing that as easy as possible. Create realistic prototypes in no time at all.
            </p>
          </div>
          <button class="bg-[#8B5CF6] px-6 py-3 rounded-lg hover:bg-[#7C3AED] transition-colors">
            Starting Earning
          </button>
        </div>
  
        <!-- Task Cards -->
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4 sm:gap-6">
          <div class="bg-white/5 rounded-2xl p-6 backdrop-blur-sm">
            <h3 class="text-xl font-semibold mb-4">Engagement Tasks</h3>
            <img 
            src="../../assets/images/png/rectangle-lg.png" 
              alt="Engagement task example" 
              class="w-full h-48 object-cover rounded-lg mb-4"
            />
            <p class="text-white/80">Create and participate in engaging tasks to earn rewards.</p>
          </div>
  
          <div class="bg-white/5 rounded-2xl p-6 backdrop-blur-sm">
            <h3 class="text-xl font-semibold mb-4">Promotion Tasks</h3>
            <img 
                          src="../../assets/images/png/rectangle-lg.png"  
              alt="Promotion task example" 
              class="w-full h-48 object-cover rounded-lg mb-4"
            />
            <p class="text-white/80">Help promote content and earn rewards for your efforts.</p>
          </div>
  
          <div class="bg-white/5 rounded-2xl p-6 backdrop-blur-sm">
            <h3 class="text-xl font-semibold mb-4">Creative Tasks</h3>
            <img 
                          src="../../assets/images/png/rectangle-lg.png"  
              alt="Creative task example" 
              class="w-full h-48 object-cover rounded-lg mb-4"
            />
            <p class="text-white/80">Use your creativity to complete tasks and earn rewards.</p>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  