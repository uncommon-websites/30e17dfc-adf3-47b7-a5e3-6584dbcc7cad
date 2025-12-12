<script lang="ts">
  import Header from "$lib/components/Header.svelte";
  
  // Icons
  const ArrowRight = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"/><path d="m12 5 7 7-7 7"/></svg>`;
  const PlayCircle = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"/><polygon points="10 8 16 12 10 16 10 8"/></svg>`;
  const ChevronLeft = `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m15 18-6-6 6-6"/></svg>`;
  const ChevronRight = `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m9 18 6-6-6-6"/></svg>`;
  const Check = `<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><path d="M20 6 9 17l-5-5"/></svg>`;
  const Plus = `<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"/><path d="M12 5v14"/></svg>`;
  const Instagram = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect width="20" height="20" x="2" y="2" rx="5" ry="5"/><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"/><line x1="17.5" x2="17.51" y1="6.5" y2="6.5"/></svg>`;
  const LinkedIn = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect width="4" height="12" x="2" y="9"/><circle cx="4" cy="4" r="2"/></svg>`;
  const XIcon = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M18 6 6 18"/><path d="m6 6 18 12"/></svg>`;

  // Data
  const heroImages = [
    "/generated/image-a-confident-young-woman-in-her-late-20s--1765574587994-0.webp",
    "/generated/image-two-women-friends-having-coffee-together-1765574591213-1.webp",
    "/generated/image-a-woman-in-her-30s-journaling-at-a-kitch-1765574593716-2.webp",
    "/generated/image-a-diverse-woman-doing-gentle-yoga-or-str-1765574596149-3.webp",
    "/generated/image-a-woman-looking-at-her-phone-with-a-reli-1765574598610-4.webp",
    "/generated/image-a-confident-young-woman-in-her-late-20s--1765574587994-0.webp"
  ];

  const benefitCards = [
    {
      title: "Track with your voice.",
      desc: "Just talk to Vani like a friend. No more tedious forms or endless tapping. Voice-first tracking makes managing PCOS feel natural.",
      image: "/generated/image-a-woman-speaking-into-her-phone-naturall-1765574608591-8.webp"
    },
    {
      title: "AI that understands your patterns.",
      desc: "Vani recognizes connections between your symptoms, habits, and health data that you might miss. Get insights that actually help.",
      image: "/generated/image-close-up-of-hands-holding-a-phone-showin-1765574611037-9.webp"
    },
    {
      title: "Lab results, finally understood.",
      desc: "Upload your lab results and get plain-English explanations. No more googling medical jargon or feeling confused.",
      image: "/generated/image-a-woman-looking-at-medical-lab-results-o-1765574613562-10.webp"
    }
  ];

  const steps = [
    {
      step: 1,
      title: "Download and join the community.",
      desc: "Get early access from the waitlist. Join 2,500+ women already supporting each other through their PCOS journey.",
      image: "plan"
    },
    {
      step: 2,
      title: "Start tracking with your voice.",
      desc: "Just talk to Vani about your symptoms, meals, or how you're feeling. It's like texting a friend who really gets it.",
      image: "schedule"
    },
    {
      step: 3,
      title: "Get personalized insights.",
      desc: "Vani's AI recognizes patterns across your symptoms, nutrition, and habits. See what's really affecting your PCOS.",
      image: "results"
    },
    {
      step: 4,
      title: "Understand your lab results.",
      desc: "Upload lab results and get clear, plain-English explanations. Know exactly what your numbers mean for your PCOS.",
      image: "notes"
    },
    {
      step: 5,
      title: "Take control of your health.",
      desc: "Use your insights to make informed decisions. Track progress over time and see what's working for your body.",
      image: "improve"
    }
  ];

  const faqs = [
    "When will Vani be available?",
    "Is Vani right for me if I'm newly diagnosed?",
    "How does voice tracking work?",
    "Is my health data private and secure?",
    "What makes Vani different from other tracking apps?"
  ];
</script>

<Header />

<main class="w-full overflow-x-hidden">
  <!-- Hero Section -->
  <section class="pt-32 pb-16 md:pt-40 md:pb-24 px-6 text-center max-w-7xl mx-auto">
    <h1 class="text-4xl md:text-6xl lg:text-7xl font-medium tracking-tight text-[#1A1A1A] mb-6 leading-[1.1]">
      PCOS management<br />that finally gets it.
    </h1>
    <p class="text-gray-600 text-lg md:text-xl max-w-3xl mx-auto mb-10 leading-relaxed font-light">
      Track symptoms with your voice, understand patterns with AI, and join a community of women who truly understand your journey.
    </p>
    <button class="bg-[#1A1A1A] text-white px-8 py-3.5 rounded-sm font-medium hover:bg-black transition-colors">
      Join the Waitlist
    </button>
  </section>

  <!-- Hero Images Scroll -->
  <div class="w-full overflow-x-auto pb-12 hide-scrollbar">
    <div class="flex gap-4 px-6 min-w-max">
      {#each heroImages as img, i}
        <div class="relative w-48 h-64 md:w-64 md:h-80 rounded-3xl overflow-hidden flex-shrink-0">
          <img src={img} alt="Women managing PCOS with Vani" class="w-full h-full object-cover" />
        </div>
      {/each}
    </div>
  </div>

  <!-- App Feature Section -->
  <section class="py-20 px-6 max-w-7xl mx-auto">
    <div class="bg-white rounded-[40px] p-8 md:p-16 flex flex-col md:flex-row items-center gap-12 shadow-sm">
      <!-- Phone Mockup -->
      <div class="w-full md:w-1/2 flex justify-center">
        <div class="relative w-[280px] h-[580px] bg-black rounded-[40px] border-[8px] border-black shadow-2xl overflow-hidden">
          <div class="absolute top-0 left-0 right-0 h-6 bg-black z-20 flex justify-center">
            <div class="w-20 h-4 bg-black rounded-b-xl"></div>
          </div>
          <div class="w-full h-full bg-white pt-10 px-4 overflow-hidden flex flex-col">
            <!-- Mock Voice Chat UI -->
            <div class="flex justify-between items-center mb-6">
              <div class="text-lg font-semibold">Vani</div>
              <div class="w-8 h-8 rounded-full bg-gray-100"></div>
            </div>
            <div class="flex-1 space-y-4 overflow-hidden">
              <!-- AI Message -->
              <div class="flex gap-2">
                <div class="w-6 h-6 rounded-full bg-primary-100 flex-shrink-0"></div>
                <div class="bg-gray-50 rounded-2xl rounded-tl-sm p-3 max-w-[80%]">
                  <p class="text-[10px] text-gray-700">How are you feeling today?</p>
                </div>
              </div>
              <!-- User Message -->
              <div class="flex gap-2 justify-end">
                <div class="bg-primary-500 text-white rounded-2xl rounded-tr-sm p-3 max-w-[80%]">
                  <p class="text-[10px]">Having some cramps and feeling tired</p>
                </div>
              </div>
              <!-- AI Response -->
              <div class="flex gap-2">
                <div class="w-6 h-6 rounded-full bg-primary-100 flex-shrink-0"></div>
                <div class="bg-gray-50 rounded-2xl rounded-tl-sm p-3 max-w-[80%]">
                  <p class="text-[10px] text-gray-700">I've noticed this pattern before your cycle. Want to log it?</p>
                </div>
              </div>
            </div>
            <!-- Voice Input -->
            <div class="mt-4 flex items-center gap-2 bg-gray-50 rounded-full px-4 py-2">
              <div class="w-5 h-5 rounded-full bg-primary-500 flex items-center justify-center">
                <div class="w-2 h-2 bg-white rounded-full"></div>
              </div>
              <div class="text-[10px] text-gray-400">Tap to speak...</div>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Content -->
      <div class="w-full md:w-1/2 space-y-8">
        <h2 class="text-3xl md:text-4xl font-medium leading-tight text-[#1A1A1A]">
          Talk to someone who gets it.<br />
          Track symptoms, nutrition, and habits with your voice. Vani's AI recognizes patterns and gives you insights in plain English. Everything you need in one place.
        </h2>
        <div class="flex items-center justify-between pt-4">
          <button class="flex items-center gap-2 text-[#1A1A1A] font-medium hover:opacity-70 transition-opacity">
            {@html PlayCircle}
            See how it works
          </button>
          <div class="flex gap-2">
            <button class="p-2 rounded-full border border-gray-200 hover:bg-gray-50 text-gray-400 hover:text-black transition-colors">
              {@html ChevronLeft}
            </button>
            <button class="p-2 rounded-full border border-gray-200 hover:bg-gray-50 text-gray-400 hover:text-black transition-colors">
              {@html ChevronRight}
            </button>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Value Proposition -->
  <section class="py-16 px-6 max-w-7xl mx-auto">
    <div class="grid md:grid-cols-2 gap-12 items-start">
      <h2 class="text-3xl md:text-5xl font-medium tracking-tight text-[#1A1A1A] leading-tight">
        You deserve to feel understood.
      </h2>
      <p class="text-gray-600 text-lg font-light leading-relaxed">
        PCOS is complex, and you shouldn't have to navigate it alone. Vani combines voice-first tracking, AI pattern recognition, and a supportive community to help you understand your body and take control of your health journey.
      </p>
    </div>
  </section>

  <!-- Benefit Cards -->
  <section class="py-8 px-6 max-w-7xl mx-auto">
    <div class="grid md:grid-cols-3 gap-6">
      {#each benefitCards as card}
        <div class="relative h-[480px] rounded-3xl overflow-hidden group">
          <img src={card.image} alt={card.title} class="absolute inset-0 w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" />
          <div class="absolute inset-0 bg-gradient-to-t from-black/60 via-black/20 to-transparent"></div>
          <div class="absolute bottom-0 left-0 right-0 p-8 text-white">
            <h3 class="text-2xl font-medium mb-3">{card.title}</h3>
            <p class="text-white/80 text-sm leading-relaxed font-light">{card.desc}</p>
          </div>
        </div>
      {/each}
    </div>
  </section>

  <!-- Testimonials -->
  <section class="py-24 px-6 max-w-6xl mx-auto">
    <h2 class="text-3xl md:text-4xl font-medium text-center mb-16">What our community says.</h2>
    <div class="grid md:grid-cols-3 gap-8">
      <!-- Testimonial 1 -->
      <div class="bg-white rounded-3xl p-8 flex flex-col">
        <blockquote class="text-base font-light leading-relaxed text-gray-700 mb-6 flex-1">
          "Finally, something that understands PCOS isn't just about periods. Vani helps me see patterns I never noticed before."
        </blockquote>
        <div class="flex items-center gap-3">
          <img src="/generated/image-a-young-south-asian-woman-with-a-warm-sm-1765574601305-5.webp" alt="Priya K." class="w-12 h-12 rounded-full object-cover" />
          <div>
            <div class="font-medium text-sm">Priya K.</div>
            <div class="text-gray-500 text-xs">Managing PCOS for 3 years</div>
          </div>
        </div>
      </div>

      <!-- Testimonial 2 -->
      <div class="bg-white rounded-3xl p-8 flex flex-col">
        <blockquote class="text-base font-light leading-relaxed text-gray-700 mb-6 flex-1">
          "Being newly diagnosed was overwhelming. Vani makes tracking so easy, and the community support has been incredible."
        </blockquote>
        <div class="flex items-center gap-3">
          <img src="/generated/image-a-black-woman-in-her-late-20s-with-a-gen-1765574603812-6.webp" alt="Michelle T." class="w-12 h-12 rounded-full object-cover" />
          <div>
            <div class="font-medium text-sm">Michelle T.</div>
            <div class="text-gray-500 text-xs">6 months post-diagnosis</div>
          </div>
        </div>
      </div>

      <!-- Testimonial 3 -->
      <div class="bg-white rounded-3xl p-8 flex flex-col">
        <blockquote class="text-base font-light leading-relaxed text-gray-700 mb-6 flex-1">
          "The voice tracking is a game changer. I can log symptoms while I'm feeling them, not hours later when I've forgotten the details."
        </blockquote>
        <div class="flex items-center gap-3">
          <img src="/generated/image-a-middle-eastern-woman-with-a-determined-1765574606232-7.webp" alt="Aisha R." class="w-12 h-12 rounded-full object-cover" />
          <div>
            <div class="font-medium text-sm">Aisha R.</div>
            <div class="text-gray-500 text-xs">PCOS Warrior</div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Stats Grid -->
  <section class="py-12 px-6 max-w-7xl mx-auto border-t border-gray-200">
    <div class="grid md:grid-cols-3 gap-8 text-center md:text-left">
      <div>
        <h3 class="text-xl font-medium mb-2">2,500+ community members.</h3>
        <p class="text-gray-500 text-sm font-light">Join thousands of women supporting each other through their PCOS journey before launch.</p>
      </div>
      <div>
        <h3 class="text-xl font-medium mb-2">Voice-first tracking.</h3>
        <p class="text-gray-500 text-sm font-light">Just talk naturally. No more tedious forms or endless tapping through apps.</p>
      </div>
      <div>
        <h3 class="text-xl font-medium mb-2">AI pattern recognition.</h3>
        <p class="text-gray-500 text-sm font-light">Discover connections between symptoms, nutrition, and habits you might have missed.</p>
      </div>
    </div>
  </section>

  <!-- How it works -->
  <section class="py-20 px-6 max-w-7xl mx-auto" id="features">
    <div class="mb-16 max-w-md">
      <h2 class="text-4xl font-medium mb-6">How it works.</h2>
      <p class="text-gray-600 font-light">Vani combines voice tracking, AI insights, and community support to help you understand your PCOS patterns and take control of your health journey.</p>
    </div>

    <div class="space-y-6">
      {#each steps as step}
        <div class="bg-white rounded-[40px] p-8 md:p-12 flex flex-col items-center text-center max-w-2xl mx-auto shadow-sm">
          <div class="w-full text-left mb-8">
            <span class="inline-block w-8 h-8 rounded-full border border-gray-200 text-center leading-8 text-sm font-medium mb-4">{step.step}</span>
            <h3 class="text-2xl font-medium mb-3">{step.title}</h3>
            <p class="text-gray-500 font-light text-sm max-w-lg">{step.desc}</p>
          </div>
          
          <!-- Phone Mockup for Step -->
          <div class="relative w-[240px] h-[480px] bg-black rounded-[35px] border-[6px] border-black shadow-xl overflow-hidden mt-4">
             <div class="absolute top-0 left-0 right-0 h-5 bg-black z-20 flex justify-center">
                <div class="w-16 h-3 bg-black rounded-b-lg"></div>
             </div>
             <div class="w-full h-full bg-white pt-8 px-3 overflow-hidden">
                <!-- Dynamic Content based on step -->
                {#if step.image === 'plan'}
                  <div class="space-y-3 mt-4">
                    <div class="p-3 border rounded-xl border-black bg-gray-50">
                      <div class="font-bold text-xs mb-1">Optimal ID</div>
                      <div class="h-1 w-full bg-gray-200 rounded"></div>
                    </div>
                    <div class="p-3 border rounded-xl border-gray-200">
                       <div class="font-bold text-xs mb-1 text-gray-400">Essential</div>
                       <div class="h-1 w-full bg-gray-100 rounded"></div>
                    </div>
                  </div>
                {:else if step.image === 'schedule'}
                   <div class="mt-4">
                     <div class="text-center font-bold mb-4">Appointment</div>
                     <div class="bg-gray-100 h-32 rounded-xl mb-3 flex items-center justify-center text-xs text-gray-400">Map View</div>
                     <button class="w-full bg-black text-white text-xs py-2 rounded-lg">Confirm</button>
                   </div>
                {:else if step.image === 'results'}
                   <div class="bg-black h-full -mx-3 -mt-8 pt-10 px-3 text-white">
                      <div class="text-center mb-6">
                        <div class="w-12 h-12 bg-gray-700 rounded-full mx-auto mb-2"></div>
                        <div class="text-sm font-bold">Grace Parker</div>
                      </div>
                      <div class="space-y-2">
                         <div class="bg-gray-800 p-2 rounded-lg h-10"></div>
                         <div class="bg-gray-800 p-2 rounded-lg h-10"></div>
                      </div>
                   </div>
                {:else if step.image === 'notes'}
                   <div class="mt-4 space-y-3">
                      <div class="font-bold text-sm">Health Status</div>
                      <div class="text-[10px] text-gray-500 leading-relaxed">
                        You usually make smart choices for your health through regular exercise...
                      </div>
                      <div class="bg-gray-50 p-2 rounded text-[10px] text-gray-600">
                        Since your diet lacks enough fruits and vegetables...
                      </div>
                   </div>
                {:else}
                   <div class="mt-4 flex flex-col h-full">
                      <div class="flex-1">
                        <div class="bg-gray-100 p-2 rounded-lg rounded-tl-none text-[10px] mb-2 max-w-[80%]">
                          What benefits can I get by bringing ApoB closer to the optimal range?
                        </div>
                        <div class="bg-blue-50 p-2 rounded-lg rounded-tr-none text-[10px] ml-auto max-w-[80%]">
                          By lowering ApoB, you reduce the number of cholesterol-carrying particles...
                        </div>
                      </div>
                      <div class="h-10 border-t mt-2"></div>
                   </div>
                {/if}
             </div>
          </div>
        </div>
      {/each}
    </div>
  </section>

  <!-- Dark Cards Section -->
  <section class="py-8 px-6 max-w-7xl mx-auto">
    <div class="grid md:grid-cols-2 gap-6">
      <!-- Community Card -->
      <div class="bg-[#111] rounded-[40px] p-8 md:p-12 text-white min-h-[500px] flex flex-col relative overflow-hidden">
        <div class="relative z-10">
          <h3 class="text-sm font-medium text-gray-400 mb-2">You're not alone.</h3>
          <h2 class="text-2xl md:text-3xl font-medium max-w-xs">Connect with women who truly understand your journey.</h2>
        </div>
        <!-- Abstract Community Visual -->
        <div class="absolute inset-0 flex items-center justify-center opacity-30 mt-20">
           <svg viewBox="0 0 200 100" class="w-full h-full text-gray-500 fill-current">
              <!-- Simplified dot map representation -->
              {#each Array(100) as _, i}
                <circle cx={Math.random() * 200} cy={Math.random() * 100} r={Math.random() * 1.5} />
              {/each}
           </svg>
        </div>
      </div>

      <!-- Privacy Card -->
      <div class="bg-[#111] rounded-[40px] p-8 md:p-12 text-white min-h-[500px] flex flex-col relative overflow-hidden">
        <div class="relative z-10">
          <h3 class="text-sm font-medium text-gray-400 mb-2">Your data is safe with us.</h3>
          <h2 class="text-2xl md:text-3xl font-medium max-w-xs">Built with privacy at the core. Your health data stays yours.</h2>
        </div>
        <!-- Blurred Text Visual -->
        <div class="absolute inset-0 flex items-center justify-center mt-20 overflow-hidden">
           <div class="text-4xl font-mono text-gray-600 opacity-20 blur-sm select-none break-all p-8">
             Elizab|%b$9yT Willi|I7m/e Magn|&5a! Trigly|?Pm_Lw
           </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Waitlist Section -->
  <section class="py-24 px-6 max-w-7xl mx-auto" id="waitlist">
    <div class="text-center mb-16">
      <h2 class="text-3xl md:text-4xl font-medium mb-4">Join the waitlist.</h2>
      <p class="text-gray-500 font-light max-w-2xl mx-auto">Be among the first to experience PCOS management that finally understands you. Get early access when we launch on the App Store.</p>
    </div>

    <div class="max-w-2xl mx-auto">
      <!-- Waitlist Card -->
      <div class="bg-white rounded-[32px] p-8 md:p-12 flex flex-col">
        <div class="mb-8">
          <h3 class="text-2xl font-medium mb-4">Get early access</h3>
          <p class="text-sm text-gray-500 mb-6">Join thousands of women already on the waitlist. We'll notify you as soon as Vani launches.</p>
        </div>
        
        <ul class="space-y-4 mb-8">
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Priority access to the app when we launch
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Join our community of 2,500+ members before launch
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Voice-first symptom tracking and AI pattern recognition
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Lab result interpretation in plain English
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            PCOS-specific nutrition and habit tracking
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            No spam, just updates on our progress
          </li>
        </ul>

        <div class="space-y-3">
          <input type="email" placeholder="Enter your email" class="w-full px-4 py-3 border border-gray-200 rounded-sm text-sm focus:outline-none focus:border-gray-400 transition-colors" />
          <button class="w-full bg-[#1A1A1A] text-white py-3 rounded-sm font-medium hover:bg-black transition-colors">Join the Waitlist</button>
        </div>
        
        <p class="text-xs text-gray-400 mt-4 text-center">Coming soon to the App Store</p>
      </div>
    </div>
  </section>

  <!-- FAQ -->
  <section class="py-20 px-6 max-w-3xl mx-auto" id="faq">
    <h2 class="text-3xl font-medium text-center mb-12">Frequently asked questions.</h2>
    <div class="space-y-4">
      {#each faqs as question}
        <div class="border-b border-gray-200 py-4 flex justify-between items-center cursor-pointer group hover:bg-gray-50/50 transition-colors px-2">
          <span class="text-sm md:text-base font-medium text-gray-800">{question}</span>
          <span class="text-gray-400 group-hover:text-black transition-colors">{@html Plus}</span>
        </div>
      {/each}
    </div>
    <div class="mt-12 text-center">
      <button class="border border-gray-300 px-6 py-3 rounded-sm text-xs font-medium hover:bg-gray-50 transition-colors">
        View all Frequently Asked Questions
      </button>
    </div>
  </section>

  <!-- Footer -->
  <footer class="py-16 px-6 border-t border-gray-200 bg-[#F9F8F6]">
    <div class="max-w-7xl mx-auto">
      <div class="flex flex-col md:flex-row justify-between items-start md:items-center gap-8 mb-16">
        <div class="flex items-center gap-2">
          <svg width="24" height="24" viewBox="0 0 97 97" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path fill-rule="evenodd" clip-rule="evenodd" d="M96.8438 48.3333C96.8438 75.0271 75.3534 96.6667 48.8438 96.6667C25.3046 96.6667 5.72283 79.605 1.63005 57.0928C1.61771 57.0251 1.60551 56.9572 1.59346 56.8891C1.10084 54.1121 0.84375 51.2529 0.84375 48.3333C0.84375 46.0025 1.00762 43.71 1.32439 41.4671C4.31845 20.2681 20.9721 3.49883 42.0249 0.483986C42.0602 0.478911 42.0954 0.473908 42.131 0.468905C44.3246 0.159814 46.5657 0 48.8438 0C51.8142 0 54.7216 0.271706 57.5428 0.791773C79.8997 4.91296 96.8438 24.6307 96.8438 48.3333ZM84.8438 48.3333C84.8438 68.3537 68.7261 84.5833 48.8438 84.5833C33.861 84.5833 21.0159 75.3669 15.5951 62.257C17.8219 62.6361 20.1099 62.8333 22.4438 62.8333C44.9769 62.8333 63.2438 44.4396 63.2438 21.75C63.2438 19.4 63.0479 17.096 62.6714 14.8538C75.6909 20.3123 84.8438 33.2466 84.8438 48.3333ZM49.6077 12.0913C50.6673 15.1126 51.2438 18.3635 51.2438 21.75C51.2438 37.7662 38.3495 50.75 22.4438 50.75C19.0806 50.75 15.8521 50.1695 12.8517 49.1026C12.8464 48.8469 12.8438 48.5905 12.8438 48.3333C12.8438 28.3129 28.9614 12.0833 48.8438 12.0833C49.0991 12.0833 49.3538 12.086 49.6077 12.0913Z" fill="black"/>
          </svg>
          <span class="font-bold text-lg tracking-wide">Vani</span>
        </div>
        
        <nav class="flex flex-wrap gap-6 md:gap-8 text-xs font-medium text-gray-600">
          <a href="#features" class="hover:text-black">Features</a>
          <a href="#faq" class="hover:text-black">FAQ</a>
          <a href="#" class="hover:text-black">Community</a>
          <a href="#" class="hover:text-black">Terms & Conditions</a>
          <a href="#" class="hover:text-black">Privacy Policy</a>
        </nav>

        <div class="flex gap-4 text-gray-800">
          <a href="#" class="hover:text-black" aria-label="TikTok">{@html XIcon}</a>
          <a href="#" class="hover:text-black" aria-label="Instagram">{@html Instagram}</a>
          <a href="#" class="hover:text-black" aria-label="LinkedIn">{@html LinkedIn}</a>
        </div>
      </div>

      <div class="text-[10px] text-gray-400 leading-relaxed max-w-5xl">
        <p class="mb-2">Vani is a technology company providing symptom tracking and health information tools. Vani does not provide medical advice, diagnosis, or treatment. The information provided by Vani is for informational purposes only and should not replace professional medical advice. Always consult with a qualified healthcare provider regarding any medical conditions or treatment decisions.</p>
        <p class="mb-2">The AI-powered insights and pattern recognition features are designed to help you track and understand your symptoms, but should not be used as a substitute for professional medical care. If you have concerns about your health, please consult with your doctor or healthcare provider.</p>
        <p class="mt-2">By joining our waitlist, you agree to receive updates about Vani. We respect your privacy and will never spam you. You can unsubscribe at any time.</p>
      </div>
    </div>
  </footer>
</main>

<style>
  :global(body) {
    background-color: #F9F8F6;
    font-family: 'Inter', sans-serif;
  }
  
  .hide-scrollbar::-webkit-scrollbar {
    display: none;
  }
  .hide-scrollbar {
    -ms-overflow-style: none;
    scrollbar-width: none;
  }
</style>

