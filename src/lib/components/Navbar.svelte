<script>
  import { onMount } from 'svelte';
  
  let isScrolled = false;

  onMount(() => {
    const handleScroll = () => {
      isScrolled = window.scrollY > 10;
    };
    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  });
</script>

<nav class="fixed top-0 left-0 right-0 z-50 transition-all duration-300 {isScrolled ? 'bg-white/90 backdrop-blur-md border-b border-gray-100 py-3' : 'bg-white py-5'}">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex items-center justify-between">
    <!-- Logo -->
    <div class="flex items-center gap-2">
      <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="text-black">
        <path d="M12 2C6.48 2 2 6.48 2 12C2 17.52 6.48 22 12 22C17.52 22 22 17.52 22 12C22 6.48 17.52 2 12 2ZM11 16H9V8H11V16ZM15 16H13V8H15V16Z" fill="currentColor"/>
      </svg>
      <span class="font-bold text-xl tracking-tight">Listen</span>
    </div>

    <!-- Links -->
    <div class="hidden md:flex items-center gap-8">
      <a href="#solutions" class="text-sm font-medium text-gray-600 hover:text-black">Solutions</a>
      <a href="#customers" class="text-sm font-medium text-gray-600 hover:text-black">Customers</a>
      <a href="#resources" class="text-sm font-medium text-gray-600 hover:text-black">Resources</a>
      <a href="#careers" class="text-sm font-medium text-gray-600 hover:text-black">Careers</a>
    </div>

    <!-- Actions -->
    <div class="flex items-center gap-6">
      <a href="#signin" class="text-sm font-medium text-gray-900 hover:text-black">Sign In</a>
      <a href="#demo" class="bg-blue-700 text-white px-5 py-2.5 rounded-lg text-sm font-medium hover:bg-blue-800 transition-colors">Request Demo</a>
    </div>
  </div>
</nav>
