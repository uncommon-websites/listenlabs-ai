<script lang="ts">
  import Navbar from "$lib/components/Navbar.svelte";
  import Hero from "$lib/components/Hero.svelte";
  import Testimonials from "$lib/components/Testimonials.svelte";
  import UseCases from "$lib/components/UseCases.svelte";
  import Features from "$lib/components/Features.svelte";
  import Process from "$lib/components/Process.svelte";
  import Audience from "$lib/components/Audience.svelte";
  import Highlight from "$lib/components/Highlight.svelte";
  import Stats from "$lib/components/Stats.svelte";
  import Quote from "$lib/components/Quote.svelte";
  import Security from "$lib/components/Security.svelte";
  import PreFooter from "$lib/components/PreFooter.svelte";
  import Footer from "$lib/components/Footer.svelte";
</script>

<div class="min-h-screen bg-white font-sans text-gray-900 selection:bg-blue-100 selection:text-blue-900">
  <Navbar />
  <main>
    <Hero />
    <Testimonials />
    <UseCases />
    <Features />
    <Process />
    <Audience />
    <Highlight />
    <Stats />
    <Quote />
    <Security />
    <PreFooter />
  </main>
  <Footer />
</div>

