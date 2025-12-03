<script lang="ts">
	import { onMount } from 'svelte';

	// Icons
	const IconChevronRight = `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" class="w-4 h-4"><path stroke-linecap="round" stroke-linejoin="round" d="M8.25 4.5l7.5 7.5-7.5 7.5" /></svg>`;
	const IconExternalLink = `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" class="w-3 h-3"><path stroke-linecap="round" stroke-linejoin="round" d="M13.5 6H5.25A2.25 2.25 0 003 8.25v10.5A2.25 2.25 0 005.25 21h10.5A2.25 2.25 0 0018 18.75V10.5m-10.5 6L21 3m0 0h-5.25M21 3v5.25" /></svg>`;
	const IconPlay = `<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6"><path fill-rule="evenodd" d="M4.5 5.653c0-1.426 1.529-2.33 2.779-1.643l11.54 6.348c1.295.712 1.295 2.573 0 3.285L7.28 19.991c-1.25.687-2.779-.217-2.779-1.643V5.653z" clip-rule="evenodd" /></svg>`;
	
	// Logos (Simplified SVGs)
	const LogoListen = `<svg viewBox="0 0 100 24" fill="currentColor" class="h-6 w-auto"><path d="M10.8 2.4h-2.4v14.4h8.4v-2.4h-6V2.4zm4.8 2.4h2.4v12h-2.4v-12zm1.2-3.6c-.8 0-1.4.6-1.4 1.4s.6 1.4 1.4 1.4 1.4-.6 1.4-1.4-.6-1.4-1.4-1.4zm8.4 8.4c-1.2 0-2.4.4-3.2 1.2l1.6 1.6c.4-.4 1-.8 1.6-.8 1.2 0 2 .8 2 2v.4c-2.8 0-4.8 1.6-4.8 3.6 0 1.6 1.2 2.8 3.2 2.8 1.2 0 2.4-.8 2.8-1.6v1.2h2.4v-6.4c0-2.4-2-4-5.6-4zm.4 8.4c-.4.4-1 .8-1.6.8-1.2 0-1.6-.8-1.6-1.6 0-.8.8-1.6 2.4-1.6h.8v2.4zm10.8-6h-1.6v-2.4h-2.4v2.4h-1.2v2.4h1.2v4.8c0 2 1.2 3.2 3.2 3.2h.8v-2.4h-.4c-.8 0-1.2-.4-1.2-1.2v-4.4h1.6v-2.4zm6 2.4c-2.4 0-4 1.6-4 4s1.6 4 4 4 4.4-1.6 4.4-4.4h-2.4c0 1.2-.8 2-2 2-1.2 0-2-.8-2-2s.8-2 2-2c1.2 0 1.6.8 2 1.6h2.4c-.4-2-2.4-3.2-4.4-3.2zm10.8-2.4c-1.2 0-2.4.8-2.8 1.6v-1.2h-2.4v8.4h2.4v-4.4c0-1.2.8-2 2-2 1.2 0 1.6.8 1.6 2v4.4h2.4v-5.2c0-2.4-1.6-3.6-3.2-3.6z" /></svg>`;

</script>

<div class="min-h-screen bg-white font-sans text-[#111] antialiased selection:bg-blue-100 selection:text-blue-900">
	
	<!-- Navbar -->
	<nav class="fixed top-0 w-full z-50 bg-white/90 backdrop-blur-sm border-b border-gray-100/50">
		<div class="max-w-[1400px] mx-auto px-6 h-16 flex items-center justify-between">
			<div class="flex items-center gap-8">
				<a href="/" class="text-black hover:opacity-80 transition-opacity">
					<!-- Logo Placeholder -->
					<div class="flex items-center gap-2 font-bold text-xl tracking-tight">
						<svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor" class="text-black">
							<path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-1 14.5v-9l6 4.5-6 4.5z"/>
						</svg>
						Listen
					</div>
				</a>
				<div class="hidden md:flex items-center gap-6 text-[15px] font-medium text-gray-600">
					<a href="#solutions" class="hover:text-black transition-colors">Solutions</a>
					<a href="#customers" class="hover:text-black transition-colors">Customers</a>
					<a href="#resources" class="hover:text-black transition-colors">Resources</a>
					<a href="#careers" class="hover:text-black transition-colors">Careers</a>
				</div>
			</div>
			<div class="flex items-center gap-4">
				<a href="#signin" class="text-[15px] font-medium text-gray-600 hover:text-black transition-colors">Sign in</a>
				<a href="#demo" class="bg-[#0044EE] hover:bg-blue-700 text-white text-[15px] font-medium px-4 py-2 rounded-md transition-colors shadow-sm shadow-blue-200">
					Request Demo
				</a>
			</div>
		</div>
	</nav>

	<!-- Hero Section -->
	<section class="pt-32 pb-16 px-4 md:px-6 flex flex-col items-center text-center max-w-[1400px] mx-auto">
		<!-- Badge -->
		<a href="#news" class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full border border-gray-200 bg-white text-xs font-medium text-gray-600 hover:border-gray-300 transition-colors mb-8 shadow-sm">
			<span class="font-semibold text-gray-900">Listen raises $27M</span> to help companies understand their customers
			<span class="text-gray-400">•</span>
			<span class="text-[#0044EE]">Read more</span>
		</a>

		<!-- Headline -->
		<h1 class="text-5xl md:text-[64px] leading-[1.1] font-bold tracking-tight text-gray-900 max-w-4xl mb-6">
			AI interviews reveal what <br class="hidden md:block" /> people want, fast.
		</h1>

		<!-- Subheadline -->
		<p class="text-lg md:text-xl text-gray-500 max-w-3xl mb-10 leading-relaxed">
			Listen finds the right participants, conducts interviews, analyzes responses, and delivers actionable insights—with results in hours, not weeks.
		</p>

		<!-- Buttons -->
		<div class="flex items-center gap-3 mb-16">
			<button class="px-6 py-3 rounded-lg border border-gray-200 text-gray-700 font-medium hover:bg-gray-50 hover:border-gray-300 transition-all bg-white shadow-sm">
				Try for Free
			</button>
			<button class="px-6 py-3 rounded-lg bg-[#0044EE] text-white font-medium hover:bg-blue-700 transition-all shadow-md shadow-blue-200/50">
				Request Demo
			</button>
		</div>

		<!-- Hero Image (Browser Mockup) -->
		<div class="w-full max-w-5xl relative">
			<div class="rounded-xl border border-gray-200 bg-white shadow-2xl overflow-hidden">
				<!-- Browser Bar -->
				<div class="h-8 bg-gray-50 border-b border-gray-100 flex items-center px-4 gap-1.5">
					<div class="w-2.5 h-2.5 rounded-full bg-gray-200"></div>
					<div class="w-2.5 h-2.5 rounded-full bg-gray-200"></div>
					<div class="w-2.5 h-2.5 rounded-full bg-gray-200"></div>
					<div class="mx-auto w-1/3 h-4 bg-gray-100 rounded-md"></div>
				</div>
				<!-- Content -->
				<div class="aspect-[16/9] bg-[#FFF8E7] relative p-8 md:p-12 flex items-center justify-center overflow-hidden">
					<!-- Abstract UI Elements -->
					<div class="absolute inset-0 opacity-50 bg-[radial-gradient(circle_at_50%_50%,_rgba(255,255,255,0.8),_transparent)]"></div>
					
					<!-- Floating Cards -->
					<div class="relative w-full h-full max-w-3xl mx-auto">
						<!-- Center Chat Bubble -->
						<div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-full max-w-md">
							<!-- Input Field Mockup -->
							<div class="bg-white rounded-2xl shadow-lg p-2 flex items-center gap-3 border border-gray-100/50">
								<div class="w-8 h-8 rounded-full bg-gray-100 flex-shrink-0"></div>
								<div class="h-2 bg-gray-100 rounded w-full"></div>
							</div>
						</div>

						<!-- Card 1: Suggested Persona -->
						<div class="absolute top-1/4 left-0 md:-left-4 bg-white p-4 rounded-xl shadow-lg border border-gray-100 w-64 animate-float-slow">
							<div class="text-[10px] font-bold text-[#0044EE] uppercase tracking-wider mb-1">Suggested persona</div>
							<div class="font-semibold text-gray-900">The Non-Technical Manager</div>
							<div class="mt-3 flex items-center gap-2">
								<div class="w-6 h-6 rounded-full bg-orange-100 border border-white shadow-sm"></div>
							</div>
						</div>

						<!-- Card 2: Insight -->
						<div class="absolute top-1/3 right-0 md:-right-8 bg-white p-4 rounded-xl shadow-lg border border-gray-100 w-72 animate-float-delayed">
							<div class="text-[10px] font-bold text-[#0044EE] uppercase tracking-wider mb-1">Insight</div>
							<div class="font-medium text-gray-800 text-sm leading-snug">Millennials and women in marketing positions prefer video interviews</div>
						</div>

						<!-- Card 3: Themes -->
						<div class="absolute bottom-1/4 left-1/4 bg-white p-4 rounded-xl shadow-lg border border-gray-100 w-56 animate-float">
							<div class="text-[10px] font-bold text-[#0044EE] uppercase tracking-wider mb-1">Themes</div>
							<div class="font-semibold text-gray-900">Quick time to value</div>
						</div>
					</div>
				</div>
			</div>
		</div>

		<!-- Trusted By -->
		<div class="mt-20 mb-10 text-center">
			<p class="text-gray-500 font-medium mb-8">You're in safe hands <span class="font-normal text-gray-400">— we're trusted by industry leaders & innovators.</span></p>
			<div class="flex flex-wrap justify-center items-center gap-x-12 gap-y-8 opacity-60 grayscale hover:grayscale-0 transition-all duration-500">
				<!-- Logos (Text placeholders for now, would be SVGs) -->
				<span class="text-xl font-bold font-serif">Google</span>
				<span class="text-xl font-bold tracking-widest">SEQUOIA</span>
				<span class="text-xl font-bold font-serif italic">BCG</span>
				<span class="text-xl font-bold font-cursive">Canva</span>
				<span class="text-xl font-bold">SONY</span>
				<span class="text-xl font-bold font-serif">P&G</span>
				<span class="text-xl font-bold tracking-tight">perplexity</span>
				<span class="text-xl font-bold text-green-600">Robinhood</span>
			</div>
		</div>
	</section>

	<!-- Testimonials Section -->
	<section class="py-20 bg-white overflow-hidden">
		<div class="max-w-[1400px] mx-auto px-6">
			<div class="flex justify-between items-end mb-12">
				<h2 class="text-4xl font-bold text-gray-900 tracking-tight">Don't just take our word for it.</h2>
				<button class="bg-black text-white px-5 py-2.5 rounded-lg text-sm font-medium hover:bg-gray-800 transition-colors flex items-center gap-2">
					See all customer stories
					{@html IconExternalLink}
				</button>
			</div>

			<div class="grid grid-cols-1 md:grid-cols-3 gap-6">
				<!-- Card 1 (Partial) -->
				<div class="relative rounded-2xl overflow-hidden h-[500px] group">
					<img src="https://images.unsplash.com/photo-1596436889106-be35e843f974?auto=format&fit=crop&q=80&w=800" alt="Customer" class="absolute inset-0 w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" />
					<div class="absolute inset-0 bg-gradient-to-t from-black/80 via-transparent to-transparent"></div>
					<div class="absolute bottom-0 left-0 p-8 w-full">
						<button class="bg-white/20 backdrop-blur-md border border-white/30 text-white px-4 py-2 rounded-lg text-sm font-medium hover:bg-white/30 transition-colors">
							Read Customer Story
						</button>
					</div>
				</div>

				<!-- Card 2 (Microsoft - Featured) -->
				<div class="relative rounded-2xl overflow-hidden h-[500px] group col-span-1 md:col-span-1">
					<img src="https://images.unsplash.com/photo-1573496359142-b8d87734a5a2?auto=format&fit=crop&q=80&w=800" alt="Microsoft Customer" class="absolute inset-0 w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" />
					<div class="absolute inset-0 bg-black/40 group-hover:bg-black/30 transition-colors"></div>
					
					<!-- Microsoft Logo -->
					<div class="absolute top-8 left-8 flex items-center gap-2 text-white font-semibold text-lg">
						<div class="grid grid-cols-2 gap-0.5 w-5 h-5">
							<div class="bg-[#F25022] w-full h-full"></div>
							<div class="bg-[#7FBA00] w-full h-full"></div>
							<div class="bg-[#00A4EF] w-full h-full"></div>
							<div class="bg-[#FFB900] w-full h-full"></div>
						</div>
						Microsoft
					</div>

					<!-- Center Text -->
					<div class="absolute inset-0 flex items-center justify-center">
						<p class="text-white font-medium text-lg italic opacity-90">Everybody wants insights,</p>
					</div>

					<!-- Bottom Content -->
					<div class="absolute bottom-0 left-0 w-full bg-white p-8">
						<p class="text-lg font-medium text-gray-900 mb-4 leading-relaxed">
							"We were able to collect user stories within a day. Our leadership team was very thrilled."
						</p>
						<div class="flex items-end justify-between">
							<div>
								<div class="text-sm font-semibold text-gray-900">Romani Patel</div>
								<div class="text-sm text-gray-500">Research Lead, Microsoft</div>
							</div>
							<button class="bg-black text-white px-4 py-2 rounded-lg text-sm font-medium hover:bg-gray-800 transition-colors">
								Read Customer Story
							</button>
						</div>
					</div>
				</div>

				<!-- Card 3 (Canva) -->
				<div class="relative rounded-2xl overflow-hidden h-[500px] group">
					<img src="https://images.unsplash.com/photo-1531123897727-8f129e1688ce?auto=format&fit=crop&q=80&w=800" alt="Canva Customer" class="absolute inset-0 w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" />
					<div class="absolute inset-0 bg-gradient-to-t from-black/80 via-transparent to-transparent"></div>
					<div class="absolute top-8 left-8 text-white font-cursive text-2xl font-bold">Canva</div>
					<div class="absolute bottom-0 left-0 p-8 w-full">
						<p class="text-white text-lg font-medium mb-4 line-clamp-3">
							"Listen enabled us to get feedback on new features before launch..."
						</p>
						<div class="text-sm text-gray-300 mb-4">Matt Harris, Research & Insights</div>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Use Cases Section -->
	<section class="py-24 bg-[#FAFAFA]">
		<div class="max-w-[1400px] mx-auto px-6">
			<div class="mb-16">
				<div class="text-xs font-bold text-gray-500 uppercase tracking-widest mb-3">Use Cases</div>
				<h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6 tracking-tight">See Listen in action</h2>
				<p class="text-lg text-gray-500 max-w-3xl leading-relaxed">
					Listen is an end-to-end research platform. Our customers replace surveys, focus groups, and in-depth interviews with Listen's AI-moderated interviews.
				</p>
			</div>

			<div class="grid grid-cols-1 md:grid-cols-3 gap-x-8 gap-y-12 mb-12">
				<!-- Item 1 -->
				<div class="group cursor-pointer">
					<div class="w-12 h-12 bg-white rounded-xl border border-gray-200 flex items-center justify-center mb-6 shadow-sm group-hover:shadow-md transition-all">
						<svg class="w-6 h-6 text-gray-900" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5"><path stroke-linecap="round" stroke-linejoin="round" d="M19 11H5m14 0a2 2 0 012 2v6a2 2 0 01-2 2H5a2 2 0 01-2-2v-6a2 2 0 012-2m14 0V9a2 2 0 00-2-2M5 11V9a2 2 0 012-2m0 0V5a2 2 0 012-2h6a2 2 0 012 2v2M7 7h10" /></svg>
					</div>
					<div class="flex items-center justify-between mb-2">
						<h3 class="text-lg font-bold text-gray-900">Concept Testing</h3>
						<span class="opacity-0 group-hover:opacity-100 transition-opacity text-gray-400">→</span>
					</div>
					<p class="text-gray-500 text-sm leading-relaxed">Qualitative and quantitative feedback on new products or ideas.</p>
				</div>
				<!-- Item 2 -->
				<div class="group cursor-pointer">
					<div class="w-12 h-12 bg-white rounded-xl border border-gray-200 flex items-center justify-center mb-6 shadow-sm group-hover:shadow-md transition-all">
						<svg class="w-6 h-6 text-gray-900" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5"><path stroke-linecap="round" stroke-linejoin="round" d="M9.75 17L9 20l-1 1h8l-1-1-.75-3M3 13h18M5 17h14a2 2 0 002-2V5a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" /></svg>
					</div>
					<div class="flex items-center justify-between mb-2">
						<h3 class="text-lg font-bold text-gray-900">Landing Page Test</h3>
						<span class="opacity-0 group-hover:opacity-100 transition-opacity text-gray-400">→</span>
					</div>
					<p class="text-gray-500 text-sm leading-relaxed">Understand how people read your website and what they find confusing.</p>
				</div>
				<!-- Item 3 -->
				<div class="group cursor-pointer">
					<div class="w-12 h-12 bg-white rounded-xl border border-gray-200 flex items-center justify-center mb-6 shadow-sm group-hover:shadow-md transition-all">
						<svg class="w-6 h-6 text-gray-900" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5"><path stroke-linecap="round" stroke-linejoin="round" d="M19 11a7 7 0 01-7 7m0 0a7 7 0 01-7-7m7 7v4m0 0H8m4 0h4m-4-8a3 3 0 01-3-3V5a3 3 0 116 0v6a3 3 0 01-3 3z" /></svg>
					</div>
					<div class="flex items-center justify-between mb-2">
						<h3 class="text-lg font-bold text-gray-900">Foundational Research</h3>
						<span class="opacity-0 group-hover:opacity-100 transition-opacity text-gray-400">→</span>
					</div>
					<p class="text-gray-500 text-sm leading-relaxed">Uncover new opportunities through open-ended discussions.</p>
				</div>
				<!-- Item 4 -->
				<div class="group cursor-pointer">
					<div class="w-12 h-12 bg-white rounded-xl border border-gray-200 flex items-center justify-center mb-6 shadow-sm group-hover:shadow-md transition-all">
						<svg class="w-6 h-6 text-gray-900" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5"><path stroke-linecap="round" stroke-linejoin="round" d="M7 21a4 4 0 01-4-4V5a2 2 0 012-2h4a2 2 0 012 2v12a4 4 0 01-4 4zm0 0h12a2 2 0 002-2v-4a2 2 0 00-2-2h-2.343M11 7.343l1.657-1.657a2 2 0 012.828 0l2.829 2.829a2 2 0 010 2.828l-8.486 8.485M7 17h.01" /></svg>
					</div>
					<div class="flex items-center justify-between mb-2">
						<h3 class="text-lg font-bold text-gray-900">Brand Perception</h3>
						<span class="opacity-0 group-hover:opacity-100 transition-opacity text-gray-400">→</span>
					</div>
					<p class="text-gray-500 text-sm leading-relaxed">Understand how customers perceive your brand.</p>
				</div>
				<!-- Item 5 -->
				<div class="group cursor-pointer">
					<div class="w-12 h-12 bg-white rounded-xl border border-gray-200 flex items-center justify-center mb-6 shadow-sm group-hover:shadow-md transition-all">
						<svg class="w-6 h-6 text-gray-900" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5"><path stroke-linecap="round" stroke-linejoin="round" d="M12 19l9 2-9-18-9 18 9-2zm0 0v-8" /></svg>
					</div>
					<div class="flex items-center justify-between mb-2">
						<h3 class="text-lg font-bold text-gray-900">Creative Testing</h3>
						<span class="opacity-0 group-hover:opacity-100 transition-opacity text-gray-400">→</span>
					</div>
					<p class="text-gray-500 text-sm leading-relaxed">Find out how your ad and message makes people feel.</p>
				</div>
				<!-- Item 6 -->
				<div class="group cursor-pointer">
					<div class="w-12 h-12 bg-white rounded-xl border border-gray-200 flex items-center justify-center mb-6 shadow-sm group-hover:shadow-md transition-all">
						<svg class="w-6 h-6 text-gray-900" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5"><path stroke-linecap="round" stroke-linejoin="round" d="M15 15l-2 5L9 9l11 4-5 2zm0 0l5 5M7.188 2.239l.777 2.897M5.136 7.965l-2.898-.777M13.95 4.05l-2.122 2.122m-5.657 5.656l-2.12 2.122" /></svg>
					</div>
					<div class="flex items-center justify-between mb-2">
						<h3 class="text-lg font-bold text-gray-900">Usability Testing</h3>
						<span class="opacity-0 group-hover:opacity-100 transition-opacity text-gray-400">→</span>
					</div>
					<p class="text-gray-500 text-sm leading-relaxed">Try out new designs to make sure they're easy for people to use.</p>
				</div>
			</div>

			<!-- Personality Test Banner -->
			<div class="bg-white rounded-xl p-6 md:p-8 flex flex-col md:flex-row items-center justify-between border border-gray-200 shadow-sm gap-6">
				<div class="flex items-center gap-4">
					<div class="w-12 h-12 rounded-full bg-gray-100 flex items-center justify-center flex-shrink-0">
						<svg class="w-6 h-6 text-gray-900" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.5"><path stroke-linecap="round" stroke-linejoin="round" d="M14.828 14.828a4 4 0 01-5.656 0M9 10h.01M15 10h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z" /></svg>
					</div>
					<div>
						<h3 class="text-lg font-bold text-gray-900">Personality Test</h3>
						<p class="text-gray-500 text-sm">Try the Listen AI Interviewer and see how well it understands you.</p>
					</div>
				</div>
				<button class="bg-[#0044EE] text-white px-6 py-2.5 rounded-lg text-sm font-medium hover:bg-blue-700 transition-colors whitespace-nowrap shadow-sm shadow-blue-200">
					Try our AI Personality Test
				</button>
			</div>
		</div>
	</section>

	<!-- Platform Features Section -->
	<section class="py-24 bg-white">
		<div class="max-w-[1400px] mx-auto px-6">
			<div class="text-center mb-20">
				<h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6 tracking-tight">The AI-first research platform</h2>
				<p class="text-lg text-gray-500 max-w-2xl mx-auto">
					Replace manual research methods with AI-moderated customer interviews.
				</p>
			</div>

			<div class="grid grid-cols-1 md:grid-cols-6 gap-6">
				<!-- Card 1: AI-moderated interviews (Large) -->
				<div class="col-span-1 md:col-span-3 bg-gray-50 rounded-3xl p-8 md:p-10 flex flex-col justify-between h-[500px] overflow-hidden relative group border border-gray-100">
					<div class="relative z-10">
						<h3 class="text-xl font-bold text-gray-900 mb-2">AI-moderated interviews</h3>
						<p class="text-gray-500 text-sm max-w-xs">Probe deeper with an AI interviewer that conducts personalized interviews with each customer, at scale.</p>
					</div>
					<div class="mt-8 flex-grow relative">
						<!-- Mockup -->
						<div class="absolute top-0 left-1/2 -translate-x-1/2 w-full max-w-sm bg-white rounded-xl shadow-lg border border-gray-100 p-4 transition-transform duration-500 group-hover:-translate-y-2">
							<div class="flex gap-3 mb-4">
								<div class="w-8 h-8 rounded-full bg-pink-100"></div>
								<div class="bg-pink-50 rounded-2xl rounded-tl-none px-4 py-2 text-xs text-gray-600 max-w-[80%]">
									It took me 10 min to figure how to invite my team.
								</div>
							</div>
							<div class="flex gap-3 justify-end">
								<div class="bg-gray-100 rounded-2xl rounded-tr-none px-4 py-2 text-xs text-gray-600 max-w-[80%]">
									Generated question...
								</div>
								<div class="w-8 h-8 rounded-full bg-gray-200"></div>
							</div>
						</div>
					</div>
				</div>

				<!-- Card 2: Actionable results (Large) -->
				<div class="col-span-1 md:col-span-3 bg-gray-50 rounded-3xl p-8 md:p-10 flex flex-col justify-between h-[500px] overflow-hidden relative group border border-gray-100">
					<div class="relative z-10">
						<h3 class="text-xl font-bold text-gray-900 mb-2">Actionable results, instantly</h3>
						<p class="text-gray-500 text-sm max-w-md">Generate key takeaways, personas, and reveal top themes. Automatically.</p>
					</div>
					<div class="mt-8 flex-grow relative">
						<!-- Mockup -->
						<div class="absolute top-4 left-4 right-4 h-full bg-white rounded-t-xl shadow-lg border border-gray-100 p-6 transition-transform duration-500 group-hover:translate-y-2">
							<div class="flex gap-4">
								<div class="w-1/2 space-y-3">
									<div class="h-2 bg-gray-100 rounded w-1/3"></div>
									<div class="space-y-2">
										<div class="flex items-center gap-2 text-xs text-gray-600"><span class="w-2 h-2 rounded-full bg-blue-500"></span> The Non-Technical Manager</div>
										<div class="flex items-center gap-2 text-xs text-gray-600"><span class="w-2 h-2 rounded-full bg-purple-500"></span> The Remote Team Leader</div>
										<div class="flex items-center gap-2 text-xs text-gray-600"><span class="w-2 h-2 rounded-full bg-orange-500"></span> The Busy Executive</div>
									</div>
								</div>
								<div class="w-1/2 space-y-3">
									<div class="h-2 bg-gray-100 rounded w-1/3"></div>
									<div class="space-y-2">
										<div class="p-2 bg-blue-50 rounded text-[10px] text-blue-700 font-medium">Lengthy Tutorial</div>
										<div class="p-2 bg-purple-50 rounded text-[10px] text-purple-700 font-medium">Quick time to value</div>
									</div>
								</div>
							</div>
						</div>
					</div>
				</div>

				<!-- Card 3: Recruit participants -->
				<div class="col-span-1 md:col-span-2 bg-gray-50 rounded-3xl p-8 flex flex-col h-[320px] border border-gray-100 group">
					<h3 class="text-lg font-bold text-gray-900 mb-2">Recruit participants</h3>
					<p class="text-gray-500 text-xs mb-6">Use our pool of millions of participants (B2B and B2C), integrate with your provider, or recruit your own.</p>
					<div class="mt-auto flex justify-center">
						<div class="bg-white px-4 py-2 rounded-full shadow-sm border border-gray-200 flex items-center gap-2 transition-transform duration-300 group-hover:scale-105">
							<div class="w-8 h-8 rounded-full bg-gray-100 flex items-center justify-center text-gray-400">+</div>
							<div class="flex -space-x-2">
								<div class="w-8 h-8 rounded-full border-2 border-white bg-gray-200"></div>
								<div class="w-8 h-8 rounded-full border-2 border-white bg-gray-300"></div>
								<div class="w-8 h-8 rounded-full border-2 border-white bg-gray-400"></div>
							</div>
						</div>
					</div>
				</div>

				<!-- Card 4: Any language -->
				<div class="col-span-1 md:col-span-2 bg-gray-50 rounded-3xl p-8 flex flex-col h-[320px] border border-gray-100 group">
					<h3 class="text-lg font-bold text-gray-900 mb-2">Any language</h3>
					<p class="text-gray-500 text-xs mb-6">Translate and transcribe automatically between more than 50 languages.</p>
					<div class="mt-auto flex justify-center">
						<div class="bg-white px-6 py-3 rounded-xl shadow-sm border border-gray-200 flex items-center gap-3 transition-transform duration-300 group-hover:scale-105">
							<span class="text-gray-900 font-medium">Refinar</span>
							<span class="text-xl">🇵🇹</span>
						</div>
					</div>
				</div>

				<!-- Card 5: Test any stimuli -->
				<div class="col-span-1 md:col-span-2 bg-gray-50 rounded-3xl p-8 flex flex-col h-[320px] border border-gray-100 group">
					<h3 class="text-lg font-bold text-gray-900 mb-2">Test any stimuli</h3>
					<p class="text-gray-500 text-xs mb-6">Videos, images or Figma prototypes - we handle all types of stimuli.</p>
					<div class="mt-auto flex justify-center relative">
						<div class="w-32 h-20 bg-white rounded-lg shadow-sm border border-gray-200 flex items-center justify-center relative overflow-hidden transition-transform duration-300 group-hover:scale-105">
							<div class="absolute inset-0 bg-gray-50 border-2 border-dashed border-gray-200 m-2 rounded flex items-center justify-center">
								<div class="w-8 h-8 bg-green-100 rounded-full flex items-center justify-center text-green-600">
									<svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 16v1a3 3 0 003 3h10a3 3 0 003-3v-1m-4-8l-4-4m0 0L8 8m4-4v12" /></svg>
								</div>
							</div>
						</div>
					</div>
				</div>

				<!-- Card 6: Video, audio, or text (Wait, the screenshot has 6 cards total in this grid? No, 5 in the second row? Let's check the screenshot again) -->
				<!-- Actually the screenshot shows:
				Row 1: AI-moderated (Large), Actionable results (Large)
				Row 2: Recruit participants, Any language, Test any stimuli, Video audio or text.
				Wait, that's 4 small cards in the second row?
				Looking at the screenshot:
				Row 2 has: Recruit participants, Any language, Test any stimuli, Video audio or text.
				It looks like a 4-column grid for the second row, or they are wrapped.
				Let's look closely.
				"Recruit participants"
				"Any language"
				"Test any stimuli"
				"Video, audio, or text"
				They look equal width. So it's probably a 4-column grid row, or 2x2.
				In the screenshot, they are all in one row. So 4 columns.
				The top row has 2 large cards.
				So grid-cols-4?
				Top cards span 2 cols each.
				Bottom cards span 1 col each.
				Let's adjust the grid to `grid-cols-1 md:grid-cols-4`.
				-->
			</div>
			
			<!-- Correcting the grid for the last row -->
			<div class="grid grid-cols-1 md:grid-cols-4 gap-6 mt-6">
				<!-- Card 3: Recruit participants -->
				<div class="bg-gray-50 rounded-3xl p-6 flex flex-col h-[300px] border border-gray-100 group">
					<h3 class="text-base font-bold text-gray-900 mb-2">Recruit participants</h3>
					<p class="text-gray-500 text-[11px] mb-4 leading-relaxed">Use our pool of millions of participants (B2B and B2C), integrate with your provider, or recruit your own.</p>
					<div class="mt-auto flex justify-center">
						<div class="bg-white px-3 py-2 rounded-full shadow-sm border border-gray-200 flex items-center gap-2 scale-90">
							<div class="w-6 h-6 rounded-full bg-gray-100 flex items-center justify-center text-gray-400 text-xs">+</div>
							<div class="flex -space-x-2">
								<div class="w-6 h-6 rounded-full border border-white bg-gray-200"></div>
								<div class="w-6 h-6 rounded-full border border-white bg-gray-300"></div>
							</div>
						</div>
					</div>
				</div>

				<!-- Card 4: Any language -->
				<div class="bg-gray-50 rounded-3xl p-6 flex flex-col h-[300px] border border-gray-100 group">
					<h3 class="text-base font-bold text-gray-900 mb-2">Any language</h3>
					<p class="text-gray-500 text-[11px] mb-4 leading-relaxed">Translate and transcribe automatically between more than 50 languages.</p>
					<div class="mt-auto flex justify-center">
						<div class="bg-white px-4 py-2 rounded-xl shadow-sm border border-gray-200 flex items-center gap-2 scale-90">
							<span class="text-gray-900 font-medium text-sm">Refinar</span>
							<span class="text-lg">🇵🇹</span>
						</div>
					</div>
				</div>

				<!-- Card 5: Test any stimuli -->
				<div class="bg-gray-50 rounded-3xl p-6 flex flex-col h-[300px] border border-gray-100 group">
					<h3 class="text-base font-bold text-gray-900 mb-2">Test any stimuli</h3>
					<p class="text-gray-500 text-[11px] mb-4 leading-relaxed">Videos, images or Figma prototypes - we handle all types of stimuli.</p>
					<div class="mt-auto flex justify-center">
						<div class="w-24 h-16 bg-white rounded-lg shadow-sm border border-gray-200 flex items-center justify-center relative overflow-hidden">
							<div class="w-6 h-6 bg-green-100 rounded-full flex items-center justify-center text-green-600">
								<svg class="w-3 h-3" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 16v1a3 3 0 003 3h10a3 3 0 003-3v-1m-4-8l-4-4m0 0L8 8m4-4v12" /></svg>
							</div>
						</div>
					</div>
				</div>

				<!-- Card 6: Video, audio, or text -->
				<div class="bg-gray-50 rounded-3xl p-6 flex flex-col h-[300px] border border-gray-100 group">
					<h3 class="text-base font-bold text-gray-900 mb-2">Video, audio, or text</h3>
					<p class="text-gray-500 text-[11px] mb-4 leading-relaxed">Engage with customers through video recordings, audio chats, or text.</p>
					<div class="mt-auto flex justify-center">
						<div class="w-20 h-20 rounded-full overflow-hidden border-2 border-white shadow-sm">
							<img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?auto=format&fit=crop&q=80&w=200" alt="User" class="w-full h-full object-cover" />
						</div>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Process Section (Yellow) -->
	<section class="py-24 bg-[#FFEebb]">
		<div class="max-w-[1400px] mx-auto px-6">
			<div class="text-center mb-20">
				<h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6 tracking-tight">Customer research, streamlined</h2>
				<p class="text-lg text-gray-600 max-w-2xl mx-auto">
					Go from first question to comprehensive market report in hours, not weeks.
				</p>
			</div>

			<div class="grid grid-cols-1 md:grid-cols-3 gap-8">
				<!-- Step 1 -->
				<div class="bg-white/50 rounded-3xl p-8 border border-white/60">
					<div class="h-48 mb-8 flex items-center justify-center">
						<!-- Graphic 1 -->
						<div class="bg-white rounded-xl shadow-lg p-4 w-full max-w-[200px] transform -rotate-3">
							<div class="text-[10px] text-gray-400 mb-2">Quick Start</div>
							<div class="space-y-2">
								<div class="bg-[#0044EE] text-white text-sm font-medium p-2 rounded flex items-center gap-2">
									<svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z" /></svg>
									Create with AI
								</div>
								<div class="bg-gray-50 text-gray-400 text-sm p-2 rounded flex items-center gap-2">
									<svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 11a7 7 0 01-7 7m0 0a7 7 0 01-7-7m7 7v4m0 0H8m4 0h4m-4-8a3 3 0 01-3-3V5a3 3 0 116 0v6a3 3 0 01-3 3z" /></svg>
									Churn Interview
								</div>
								<div class="bg-gray-50 text-gray-400 text-sm p-2 rounded flex items-center gap-2">
									<svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2" /></svg>
									Concept Test
								</div>
							</div>
							<!-- Cursor -->
							<div class="absolute top-1/2 right-4 w-6 h-6">
								<svg viewBox="0 0 24 24" fill="black" class="drop-shadow-md"><path d="M5.5 3.21V20.8c0 .45.54.67.85.35l4.86-4.86a.5.5 0 0 1 .35-.15h6.87a.5.5 0 0 0 .35-.85l-12.48-12.48a.5.5 0 0 0-.8.4z"/></svg>
							</div>
						</div>
					</div>
					<h3 class="text-xl font-bold text-gray-900 mb-2">1. Select a template or upload a guide</h3>
					<p class="text-gray-600 text-sm leading-relaxed">
						Get started in seconds by choosing one of our proven, expert-vetted templates or uploading a discussion guide.
					</p>
				</div>

				<!-- Step 2 -->
				<div class="bg-white/50 rounded-3xl p-8 border border-white/60">
					<div class="h-48 mb-8 flex items-center justify-center relative">
						<!-- Graphic 2 -->
						<div class="bg-white rounded-xl shadow-lg p-4 w-full max-w-[220px]">
							<div class="flex items-center gap-2 mb-3 border-b border-gray-100 pb-2">
								<div class="w-4 h-4 rounded-full bg-gray-200"></div>
								<div class="text-[10px] text-gray-500">US 🇺🇸</div>
								<div class="text-[10px] text-gray-500">Marketing</div>
							</div>
							<div class="flex -space-x-2 justify-center mb-4">
								<div class="w-8 h-8 rounded-full border-2 border-white bg-gray-200"></div>
								<div class="w-8 h-8 rounded-full border-2 border-white bg-gray-300"></div>
								<div class="w-8 h-8 rounded-full border-2 border-white bg-gray-400"></div>
								<div class="w-8 h-8 rounded-full border-2 border-white bg-gray-500"></div>
								<div class="w-8 h-8 rounded-full border-2 border-white bg-red-100 flex items-center justify-center text-[10px] font-bold text-red-500">2k</div>
							</div>
							<button class="w-full bg-[#0044EE] text-white text-sm font-medium py-2 rounded">
								Add participants
							</button>
						</div>
					</div>
					<h3 class="text-xl font-bold text-gray-900 mb-2">2. Recruit participants</h3>
					<p class="text-gray-600 text-sm leading-relaxed">
						Use the Listen Labs panel, integrate any panel provider, or conveniently share with your own users with a link or in app. Listen takes it from here.
					</p>
				</div>

				<!-- Step 3 -->
				<div class="bg-white/50 rounded-3xl p-8 border border-white/60">
					<div class="h-48 mb-8 flex items-center justify-center overflow-hidden">
						<!-- Graphic 3 -->
						<div class="bg-white rounded-xl shadow-lg p-4 w-full max-w-[240px] transform rotate-2">
							<div class="grid grid-cols-3 gap-2 mb-3">
								<div class="bg-yellow-100 rounded p-1 text-center text-[8px] text-yellow-700 font-bold">Quotes</div>
								<div class="bg-gray-100 rounded p-1 text-center text-[8px] text-gray-500">Trends</div>
								<div class="bg-gray-100 rounded p-1 text-center text-[8px] text-gray-500">Objectives</div>
							</div>
							<div class="grid grid-cols-3 gap-2 mb-3">
								<div class="bg-gray-100 rounded p-1 text-center text-[8px] text-gray-500">Valuation</div>
								<div class="bg-[#0044EE] rounded p-1 text-center text-[10px] text-white font-bold shadow-md scale-110">See Report</div>
								<div class="bg-gray-100 rounded p-1 text-center text-[8px] text-gray-500">Recomm</div>
							</div>
							<div class="grid grid-cols-3 gap-2">
								<div class="bg-orange-100 rounded p-1 text-center text-[8px] text-orange-700 font-bold">Key Insights</div>
								<div class="bg-gray-100 rounded p-1 text-center text-[8px] text-gray-500">Top themes</div>
								<div class="bg-gray-100 rounded p-1 text-center text-[8px] text-gray-500">Person</div>
							</div>
						</div>
					</div>
					<h3 class="text-xl font-bold text-gray-900 mb-2">3. Explore your results</h3>
					<p class="text-gray-600 text-sm leading-relaxed">
						Within hours, our AI conducts and analyzes hundreds of interviews and generates a detailed and interactive report.
					</p>
				</div>
			</div>
		</div>
	</section>

	<!-- Personas Section -->
	<section class="py-24 bg-white">
		<div class="max-w-[1400px] mx-auto px-6">
			<div class="text-center mb-16">
				<h2 class="text-4xl md:text-5xl font-bold text-gray-900 tracking-tight">Get closer to your customer</h2>
			</div>

			<div class="grid grid-cols-1 md:grid-cols-3 gap-8">
				<!-- Card 1: Marketing -->
				<div class="group">
					<div class="bg-gray-50 rounded-2xl overflow-hidden mb-6 border border-gray-100 relative h-64 flex items-center justify-center">
						<!-- Graphic -->
						<div class="absolute inset-0 p-6 flex items-center justify-center">
							<div class="bg-white rounded-xl shadow-lg p-3 w-full max-w-[200px] flex items-center gap-3">
								<div class="w-10 h-10 rounded-full bg-gray-200 overflow-hidden">
									<img src="https://images.unsplash.com/photo-1494790108377-be9c29b29330?auto=format&fit=crop&q=80&w=100" alt="User" class="w-full h-full object-cover" />
								</div>
								<div class="flex-1">
									<div class="text-[8px] font-bold text-blue-600 uppercase mb-1">Insights</div>
									<div class="text-[10px] font-medium leading-tight">Millennials and women in marketing positions prefer video interviews</div>
								</div>
							</div>
						</div>
					</div>
					<h3 class="text-lg font-bold text-gray-900 mb-2">Marketing</h3>
					<p class="text-gray-500 text-sm leading-relaxed">Test advertising concepts or messaging. Understand brand values and what drives conversion.</p>
				</div>

				<!-- Card 2: Product managers -->
				<div class="group">
					<div class="bg-gray-50 rounded-2xl overflow-hidden mb-6 border border-gray-100 relative h-64 flex items-center justify-center">
						<!-- Graphic -->
						<div class="absolute inset-0 p-6 flex items-center justify-center">
							<div class="bg-white rounded-xl shadow-lg p-4 w-full max-w-[220px]">
								<div class="flex items-center gap-4 mb-3">
									<div class="w-12 h-12 rounded-full border-4 border-l-purple-500 border-t-purple-500 border-r-gray-200 border-b-gray-200 transform -rotate-45"></div>
									<div class="w-10 h-10 rounded-full overflow-hidden">
										<img src="https://images.unsplash.com/photo-1573496359142-b8d87734a5a2?auto=format&fit=crop&q=80&w=100" alt="PM" class="w-full h-full object-cover" />
									</div>
								</div>
								<div class="space-y-1">
									<div class="flex justify-between text-[8px] text-gray-500"><span>Unexpected fees</span> <span>31%</span></div>
									<div class="w-full bg-gray-100 h-1 rounded-full"><div class="bg-purple-500 h-1 rounded-full w-[31%]"></div></div>
									<div class="flex justify-between text-[8px] text-gray-500"><span>Feature limitations</span> <span>28%</span></div>
									<div class="w-full bg-gray-100 h-1 rounded-full"><div class="bg-purple-400 h-1 rounded-full w-[28%]"></div></div>
								</div>
							</div>
						</div>
					</div>
					<h3 class="text-lg font-bold text-gray-900 mb-2">Product managers</h3>
					<p class="text-gray-500 text-sm leading-relaxed">Analyze churn and get product feedback at scale.</p>
				</div>

				<!-- Card 3: User researchers -->
				<div class="group">
					<div class="bg-gray-50 rounded-2xl overflow-hidden mb-6 border border-gray-100 relative h-64">
						<img src="https://images.unsplash.com/photo-1516321318423-f06f85e504b3?auto=format&fit=crop&q=80&w=500" alt="Mobile" class="absolute inset-0 w-full h-full object-cover opacity-80" />
						<div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent flex items-end p-6">
							<div class="bg-white/90 backdrop-blur rounded-lg p-3 text-xs max-w-[80%] shadow-lg">
								<div class="font-medium text-gray-900">"Nice, but I find the onboarding flow a bit non-intuitive."</div>
							</div>
						</div>
						<div class="absolute top-6 left-6 text-white text-xs font-medium drop-shadow-md">What's your first impression of the app?</div>
					</div>
					<h3 class="text-lg font-bold text-gray-900 mb-2">User researchers</h3>
					<p class="text-gray-500 text-sm leading-relaxed">Conduct usability testing, diary studies or ethnographic studies.</p>
				</div>
			</div>
		</div>
	</section>

	<!-- Deep Dive Section -->
	<section class="py-24 bg-white">
		<div class="max-w-[1400px] mx-auto px-6">
			<div class="flex flex-col md:flex-row items-center gap-16">
				<div class="w-full md:w-1/2">
					<h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6 tracking-tight">More than just words</h2>
					<p class="text-lg text-gray-500 leading-relaxed max-w-md">
						Video and audio interviews reveal facial expressions and tone, uncovering deeper user sentiment.
					</p>
				</div>
				<div class="w-full md:w-1/2">
					<div class="rounded-3xl overflow-hidden shadow-2xl">
						<img src="https://images.unsplash.com/photo-1531746020798-e6953c6e8e04?auto=format&fit=crop&q=80&w=1000" alt="Deep Dive" class="w-full h-auto object-cover" />
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Stats Section -->
	<section class="py-24 bg-white border-t border-gray-100">
		<div class="max-w-[1400px] mx-auto px-6">
			<div class="grid grid-cols-1 md:grid-cols-3 gap-12 text-center md:text-left">
				<div>
					<div class="text-6xl md:text-7xl font-bold text-gray-900 mb-4 tracking-tighter">3x</div>
					<p class="text-sm text-gray-500 leading-relaxed max-w-xs mx-auto md:mx-0">Customer responses more than three times longer than average.</p>
				</div>
				<div>
					<div class="text-6xl md:text-7xl font-bold text-gray-900 mb-4 tracking-tighter">&lt;24h</div>
					<p class="text-sm text-gray-500 leading-relaxed max-w-xs mx-auto md:mx-0">Results in hours, not days.</p>
				</div>
				<div>
					<div class="text-6xl md:text-7xl font-bold text-gray-900 mb-4 tracking-tighter">+30M</div>
					<p class="text-sm text-gray-500 leading-relaxed max-w-xs mx-auto md:mx-0">Millions of possible respondents.</p>
				</div>
			</div>
		</div>
	</section>

	<!-- Quote Section (Orange) -->
	<section class="bg-[#F5B745] py-24 relative overflow-hidden">
		<div class="max-w-[1400px] mx-auto px-6 flex flex-col md:flex-row items-center relative z-10">
			<div class="w-full md:w-1/2 pr-0 md:pr-12 mb-12 md:mb-0">
				<blockquote class="text-2xl md:text-3xl font-medium text-white leading-relaxed mb-8">
					“Listen Labs has been a welcomed addition to our team. It compresses hours of work into minutes, reaches a broader audience than our schedule allows and uncovers qual/quant insights in real time.”
				</blockquote>
				<div class="text-white">
					<div class="font-bold text-lg">Lauren Haugh Neville</div>
					<div class="text-white/80 text-sm">Director of Product Insights, Chubbies Shorts</div>
				</div>
			</div>
			<div class="w-full md:w-1/2 flex justify-center md:justify-end">
				<div class="w-64 h-64 md:w-96 md:h-96 rounded-full overflow-hidden border-4 border-white/20 shadow-2xl">
					<img src="https://images.unsplash.com/photo-1580489944761-15a19d654956?auto=format&fit=crop&q=80&w=800" alt="Lauren Haugh Neville" class="w-full h-full object-cover" />
				</div>
			</div>
		</div>
	</section>

	<!-- Security Section -->
	<section class="py-24 bg-white">
		<div class="max-w-[1400px] mx-auto px-6 text-center">
			<h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6 tracking-tight">Your data is safe with us</h2>
			<p class="text-lg text-gray-500 max-w-2xl mx-auto mb-16">
				We don't train on your data. Listen Labs is compliant with SOC 2 Type II, GDPR, ISO 42001, 27001 and 27701.
			</p>
			
			<div class="flex flex-wrap justify-center gap-6 md:gap-12 opacity-80">
				<!-- Badge 1: AICPA SOC -->
				<div class="w-24 h-24 rounded-full border-2 border-gray-200 flex flex-col items-center justify-center p-2 text-center">
					<div class="text-[8px] font-bold text-gray-400 uppercase tracking-widest mb-1">AICPA</div>
					<div class="text-sm font-bold text-gray-800">SOC 2</div>
				</div>
				<!-- Badge 2: GDPR -->
				<div class="w-24 h-24 rounded-full border-2 border-gray-200 flex flex-col items-center justify-center p-2 text-center relative">
					<div class="absolute inset-0 border-2 border-dashed border-gray-100 rounded-full m-1"></div>
					<div class="text-[8px] font-bold text-gray-400 uppercase tracking-widest mb-1">GDPR</div>
					<div class="text-xs font-bold text-gray-800">COMPLIANT</div>
				</div>
				<!-- Badge 3: ISO 42001 -->
				<div class="w-24 h-24 rounded-full border-2 border-gray-200 flex flex-col items-center justify-center p-2 text-center">
					<div class="text-[8px] font-bold text-gray-400 uppercase tracking-widest mb-1">ISO</div>
					<div class="text-sm font-bold text-gray-800">42001</div>
				</div>
				<!-- Badge 4: ISO 27001 -->
				<div class="w-24 h-24 rounded-full border-2 border-gray-200 flex flex-col items-center justify-center p-2 text-center">
					<div class="text-[8px] font-bold text-gray-400 uppercase tracking-widest mb-1">ISO</div>
					<div class="text-sm font-bold text-gray-800">27001</div>
				</div>
				<!-- Badge 5: ISO 27701 -->
				<div class="w-24 h-24 rounded-full border-2 border-gray-200 flex flex-col items-center justify-center p-2 text-center">
					<div class="text-[8px] font-bold text-gray-400 uppercase tracking-widest mb-1">ISO</div>
					<div class="text-sm font-bold text-gray-800">27701</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Footer CTA -->
	<section class="relative h-[500px] flex items-center justify-center overflow-hidden">
		<img src="https://images.unsplash.com/photo-1522202176988-66273c2fd55f?auto=format&fit=crop&q=80&w=2000" alt="Team" class="absolute inset-0 w-full h-full object-cover" />
		<div class="absolute inset-0 bg-black/40"></div>
		<div class="relative z-10 text-center px-6">
			<h2 class="text-4xl md:text-6xl font-bold text-white mb-8 tracking-tight">Listen to your customers</h2>
			<button class="bg-black text-white px-8 py-4 rounded-lg text-lg font-medium hover:bg-gray-900 transition-colors shadow-lg">
				Request Demo
			</button>
		</div>
	</section>

	<!-- Footer -->
	<footer class="bg-white py-20 border-t border-gray-100 text-sm">
		<div class="max-w-[1400px] mx-auto px-6">
			<div class="grid grid-cols-2 md:grid-cols-6 gap-8 mb-16">
				<div class="col-span-2 md:col-span-1">
					<div class="flex items-center gap-2 font-bold text-xl tracking-tight mb-4">
						<svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor" class="text-black">
							<path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-1 14.5v-9l6 4.5-6 4.5z"/>
						</svg>
						Listen
					</div>
					<p class="text-gray-500 text-xs">AI-First Research Platform</p>
				</div>
				
				<div>
					<h4 class="font-bold text-gray-900 mb-4">Use Case</h4>
					<ul class="space-y-3 text-gray-500">
						<li><a href="#" class="hover:text-gray-900">Customer Journey Map</a></li>
						<li><a href="#" class="hover:text-gray-900">Multi-Market Segmentation</a></li>
						<li><a href="#" class="hover:text-gray-900">Brand Perception</a></li>
						<li><a href="#" class="hover:text-gray-900">Concept & Prototype Testing</a></li>
						<li><a href="#" class="hover:text-gray-900">Creative Testing</a></li>
						<li><a href="#" class="hover:text-gray-900">Usability Testing</a></li>
					</ul>
				</div>

				<div>
					<h4 class="font-bold text-gray-900 mb-4">Role</h4>
					<ul class="space-y-3 text-gray-500">
						<li><a href="#" class="hover:text-gray-900">Consumer Insights</a></li>
						<li><a href="#" class="hover:text-gray-900">Brand Marketing</a></li>
						<li><a href="#" class="hover:text-gray-900">Product Managers</a></li>
						<li><a href="#" class="hover:text-gray-900">UX Researchers</a></li>
						<li><a href="#" class="hover:text-gray-900">Agencies</a></li>
						<li><a href="#" class="hover:text-gray-900">Investors</a></li>
					</ul>
				</div>

				<div>
					<h4 class="font-bold text-gray-900 mb-4">Industry</h4>
					<ul class="space-y-3 text-gray-500">
						<li><a href="#" class="hover:text-gray-900">Consumer Packaged Goods</a></li>
						<li><a href="#" class="hover:text-gray-900">Technology</a></li>
						<li><a href="#" class="hover:text-gray-900">E-commerce</a></li>
						<li><a href="#" class="hover:text-gray-900">Healthcare</a></li>
						<li><a href="#" class="hover:text-gray-900">Financial Services</a></li>
						<li><a href="#" class="hover:text-gray-900">Hospitality and Travel</a></li>
					</ul>
				</div>

				<div>
					<h4 class="font-bold text-gray-900 mb-4">Resources</h4>
					<ul class="space-y-3 text-gray-500">
						<li><a href="#" class="hover:text-gray-900">Customers</a></li>
						<li><a href="#" class="hover:text-gray-900">Personality Test</a></li>
						<li><a href="#" class="hover:text-gray-900">Blog</a></li>
						<li><a href="#" class="hover:text-gray-900">Help</a></li>
					</ul>
				</div>

				<div class="space-y-8">
					<div>
						<h4 class="font-bold text-gray-900 mb-4">Company</h4>
						<ul class="space-y-3 text-gray-500">
							<li><a href="#" class="hover:text-gray-900">Careers</a></li>
							<li><a href="#" class="hover:text-gray-900">What's New</a></li>
						</ul>
					</div>
					<div>
						<h4 class="font-bold text-gray-900 mb-4">Legal</h4>
						<ul class="space-y-3 text-gray-500">
							<li><a href="#" class="hover:text-gray-900">Privacy Policy</a></li>
							<li><a href="#" class="hover:text-gray-900">Terms and Conditions</a></li>
							<li><a href="#" class="hover:text-gray-900">Cookie Policy</a></li>
							<li><a href="#" class="hover:text-gray-900">Security</a></li>
						</ul>
					</div>
				</div>
			</div>

			<div class="flex flex-col md:flex-row justify-between items-center pt-8 border-t border-gray-100">
				<div class="text-gray-400 text-xs mb-4 md:mb-0">
					© 2025 Listen Labs. All rights reserved.
				</div>
				<div class="flex items-center gap-6 text-gray-400">
					<a href="#" class="hover:text-gray-900 transition-colors">
						<span class="sr-only">LinkedIn</span>
						<svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24"><path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/></svg>
					</a>
					<a href="#" class="hover:text-gray-900 transition-colors">
						<span class="sr-only">X</span>
						<svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24"><path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817L4.99 21.75H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z"/></svg>
					</a>
					<a href="#" class="hover:text-gray-900 transition-colors">
						<span class="sr-only">YouTube</span>
						<svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24"><path d="M23.498 6.186a3.016 3.016 0 0 0-2.122-2.136C19.505 3.545 12 3.545 12 3.545s-7.505 0-9.377.505A3.017 3.017 0 0 0 .502 6.186C0 8.07 0 12 0 12s0 3.93.502 5.814a3.016 3.016 0 0 0 2.122 2.136c1.871.505 9.376.505 9.376.505s7.505 0 9.377-.505a3.015 3.015 0 0 0 2.122-2.136C24 15.93 24 12 24 12s0-3.93-.502-5.814zM9.545 15.568V8.432L15.818 12l-6.273 3.568z"/></svg>
					</a>
				</div>
			</div>
		</div>
	</footer>

</div>

<style>
	:global(html) {
		scroll-behavior: smooth;
	}
	@keyframes float {
		0%, 100% { transform: translateY(0); }
		50% { transform: translateY(-10px); }
	}
	@keyframes float-slow {
		0%, 100% { transform: translateY(0); }
		50% { transform: translateY(-15px); }
	}
	@keyframes float-delayed {
		0%, 100% { transform: translateY(0); }
		50% { transform: translateY(-8px); }
	}
	.animate-float {
		animation: float 6s ease-in-out infinite;
	}
	.animate-float-slow {
		animation: float-slow 8s ease-in-out infinite;
	}
	.animate-float-delayed {
		animation: float-delayed 7s ease-in-out infinite 1s;
	}
	.font-cursive {
		font-family: 'Brush Script MT', cursive;
	}
</style>


