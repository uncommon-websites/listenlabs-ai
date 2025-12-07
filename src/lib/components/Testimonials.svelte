<script>
  // Testimonials Section
</script>

<section class="py-24 bg-white">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex flex-col items-center text-center mb-16">
      <h2 class="text-4xl font-semibold tracking-tight text-gray-900 mb-6">Don't just take our word for it.</h2>
      <button class="inline-flex items-center gap-2 bg-black text-white px-5 py-2.5 rounded-lg text-sm font-medium hover:bg-gray-800 transition-colors">
        See all customer stories
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path><polyline points="15 3 21 3 21 9"></polyline><line x1="10" y1="14" x2="21" y2="3"></line></svg>
      </button>
    </div>

    <div class="relative overflow-hidden">
        <!-- We will create a grid that looks like a carousel -->
        <div class="grid grid-cols-1 md:grid-cols-12 gap-6 items-center">
            
            <!-- Left Card (Partially Visible) -->
            <div class="hidden md:block md:col-span-3 opacity-50 scale-90 origin-right">
                <div class="relative rounded-2xl overflow-hidden aspect-[4/5]">
                    <img src="https://images.unsplash.com/photo-1540569014015-19a7be504e3a?auto=format&fit=crop&q=80&w=600" alt="Customer" class="w-full h-full object-cover" />
                    <div class="absolute bottom-0 left-0 right-0 p-6 bg-gradient-to-t from-black/80 to-transparent">
                         <button class="bg-gray-800/80 backdrop-blur text-white text-xs px-3 py-1.5 rounded">Read Customer Story</button>
                    </div>
                </div>
            </div>

            <!-- Center Card (Main Focus) -->
            <div class="col-span-1 md:col-span-6 z-10">
                <div class="relative rounded-2xl overflow-hidden aspect-video md:aspect-[16/10] group">
                    <img src="https://images.unsplash.com/photo-1573496359142-b8d87734a5a2?auto=format&fit=crop&q=80&w=1200" alt="Microsoft Customer" class="w-full h-full object-cover brightness-75 group-hover:brightness-90 transition-all duration-500" />
                    
                    <div class="absolute top-6 left-6">
                        <div class="flex items-center gap-2 text-white font-semibold text-lg">
                            <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor"><path d="M11.55 21H3v-8.55h8.55V21zM21 21h-8.55v-8.55H21V21zm-9.45-9.45H3V3h8.55v8.55zm9.45 0h-8.55V3H21v8.55z"/></svg>
                            Microsoft
                        </div>
                    </div>

                    <div class="absolute bottom-0 left-0 right-0 p-8 text-white">
                        <div class="mb-2 text-center w-full text-xs font-medium uppercase tracking-wider opacity-80">Everybody wants insights,</div>
                        <h3 class="text-2xl md:text-3xl font-medium leading-tight mb-6">"We were able to collect user stories within a day. Our leadership team was very thrilled."</h3>
                        
                        <div class="flex items-end justify-between">
                            <div>
                                <p class="font-medium">Romani Patel</p>
                                <p class="text-sm opacity-80">Research Lead, Microsoft</p>
                            </div>
                            <button class="bg-black text-white px-4 py-2 rounded-lg text-sm font-medium hover:bg-gray-900 transition-colors">Read Customer Story</button>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Right Card (Partially Visible) -->
            <div class="hidden md:block md:col-span-3 opacity-50 scale-90 origin-left">
                <div class="relative rounded-2xl overflow-hidden aspect-[4/5]">
                    <img src="https://images.unsplash.com/photo-1664575602276-acd073f104c1?auto=format&fit=crop&q=80&w=600" alt="Customer" class="w-full h-full object-cover" />
                    <div class="absolute top-6 left-6 text-white font-cursive text-xl font-bold">Canva</div>
                    <div class="absolute bottom-0 left-0 right-0 p-6 bg-gradient-to-t from-black/80 to-transparent">
                         <p class="text-white text-sm line-clamp-3 mb-4">"Listen enabled us to get feedback on our new speaking markets..."</p>
                         <p class="text-white/70 text-xs">Matt Harris, Research & Insights</p>
                    </div>
                </div>
            </div>

        </div>
    </div>
  </div>
</section>
