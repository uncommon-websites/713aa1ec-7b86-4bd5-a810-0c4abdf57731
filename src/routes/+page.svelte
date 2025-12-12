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
    "/generated/image-woman-doing-strength-training-with-dumbb-1765517418962-0.webp",
    "/generated/image-athletic-woman-performing-barbell-squats-1765517423144-1.webp",
    "/generated/image-confident-woman-resting-between-sets-in--1765517425626-2.webp",
    "/generated/image-woman-doing-cable-exercises-for-upper-bo-1765517427902-3.webp",
    "/generated/image-athletic-woman-stretching-and-warming-up-1765517430177-4.webp",
    "/generated/image-woman-checking-fitness-progress-on-phone-1765517432433-5.webp"
  ];

  const benefitCards = [
    {
      title: "Personalized for your body.",
      desc: "Aura adapts to your unique physiology, goals, and progress with programming designed specifically for women by elite bodybuilding experts.",
      image: "/generated/image-woman-reviewing-personalized-workout-pla-1765517434730-6.webp"
    },
    {
      title: "Track every transformation.",
      desc: "Monitor your strength gains, body composition changes, and workout performance with precision tracking built for serious results.",
      image: "/generated/image-athletic-woman-tracking-workout-progress-1765517437041-7.webp"
    },
    {
      title: "Expert guidance, daily.",
      desc: "Train with confidence knowing every workout is backed by proven Olympia-level methodology adapted for your fitness journey.",
      image: "/generated/image-confident-woman-preparing-for-workout-wi-1765517439336-8.webp"
    }
  ];

  const steps = [
    {
      step: 1,
      title: "Choose your transformation goal.",
      desc: "Select from strength building, body recomposition, or competition prep. Each program is designed with Olympia-proven methodology adapted for your level.",
      image: "plan"
    },
    {
      step: 2,
      title: "Complete your fitness profile.",
      desc: "Answer questions about your training history, current fitness level, and body composition goals so we can personalize your program.",
      image: "schedule"
    },
    {
      step: 3,
      title: "Get your personalized program.",
      desc: "Receive your custom training plan instantly, with progressive overload built in and exercises demonstrated by elite coaches.",
      image: "results"
    },
    {
      step: 4,
      title: "Track your workouts daily.",
      desc: "Log sets, reps, and weights with our intuitive interface. Watch your strength numbers climb and body transform week by week.",
      image: "notes"
    },
    {
      step: 5,
      title: "Evolve with adaptive programming.",
      desc: "Your program adjusts based on your progress, ensuring you're always challenged at the right intensity for continuous gains.",
      image: "improve"
    }
  ];

  const faqs = [
    "What does an Aura membership include?",
    "Is Aura right for my fitness level?",
    "How is Aura different from other fitness apps?",
    "Do I need gym equipment to use Aura?",
    "What makes Aura's programming unique for women?"
  ];
</script>

<Header />

<main class="w-full overflow-x-hidden">
  <!-- Hero Section -->
  <section class="pt-32 pb-16 md:pt-40 md:pb-24 px-6 text-center max-w-7xl mx-auto">
    <h1 class="text-4xl md:text-6xl lg:text-7xl font-medium tracking-tight text-[#1A1A1A] mb-6 leading-[1.1]">
      Elite strength training<br />designed for women.
    </h1>
    <p class="text-gray-600 text-lg md:text-xl max-w-3xl mx-auto mb-10 leading-relaxed font-light">
      Transform your body with personalized programs from a 2x Miss Olympia champion. Expert guidance, proven methodology, beautiful design.
    </p>
    <button class="bg-[#1A1A1A] text-white px-8 py-3.5 rounded-sm font-medium hover:bg-black transition-colors">
      Start your transformation
    </button>
  </section>

  <!-- Hero Images Scroll -->
  <div class="w-full overflow-x-auto pb-12 hide-scrollbar">
    <div class="flex gap-4 px-6 min-w-max">
      {#each heroImages as img, i}
        <div class="relative w-48 h-64 md:w-64 md:h-80 rounded-3xl overflow-hidden flex-shrink-0">
          <img src={img} alt="Women strength training" class="w-full h-full object-cover" />
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
            <!-- Mock UI -->
            <div class="flex justify-between items-center mb-6">
              <div class="w-8 h-8 rounded-full bg-gray-200"></div>
              <div class="w-8 h-8 rounded-full bg-gray-100"></div>
            </div>
            <div class="mb-6">
              <div class="text-xs text-gray-500 mb-1">Today's Workout</div>
              <div class="text-2xl font-bold">Upper Body</div>
            </div>
            <div class="space-y-3">
              <div class="h-20 bg-gray-50 rounded-xl w-full border border-gray-100 p-3">
                <div class="w-1/2 h-2 bg-gray-200 rounded mb-2"></div>
                <div class="w-full h-1 bg-primary-400 rounded"></div>
              </div>
              <div class="h-20 bg-gray-50 rounded-xl w-full border border-gray-100 p-3">
                <div class="w-1/2 h-2 bg-gray-200 rounded mb-2"></div>
                <div class="w-full h-1 bg-primary-300 rounded"></div>
              </div>
              <div class="h-20 bg-gray-50 rounded-xl w-full border border-gray-100 p-3">
                <div class="w-1/2 h-2 bg-gray-200 rounded mb-2"></div>
                <div class="w-full h-1 bg-primary-200 rounded"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Content -->
      <div class="w-full md:w-1/2 space-y-8">
        <h2 class="text-3xl md:text-4xl font-medium leading-tight text-[#1A1A1A]">
          Your training at a glance.<br />
          Track every workout, monitor your progressive overload, and watch your strength numbers climb. Access your personalized program with exercise demos and form cues from elite coaches.
        </h2>
        <div class="flex items-center justify-between pt-4">
          <button class="flex items-center gap-2 text-[#1A1A1A] font-medium hover:opacity-70 transition-opacity">
            {@html PlayCircle}
            Watch demo
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
        You deserve strength that transforms everything.
      </h2>
      <p class="text-gray-600 text-lg font-light leading-relaxed">
        Your transformation is more than aesthetics—it's confidence, power, and becoming the strongest version of yourself. With elite-level expertise adapted for your body, we help you build real strength that changes how you move through the world.
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

  <!-- Testimonial -->
  <section class="py-24 px-6 max-w-4xl mx-auto text-center">
    <blockquote class="text-2xl md:text-3xl font-medium leading-relaxed text-[#1A1A1A] mb-8">
      "Most fitness apps weren't built for women's bodies or goals. Aura changes that. Every program is rooted in competitive bodybuilding science but designed to be approachable, beautiful, and effective for any woman ready to transform."
    </blockquote>
    <div class="flex flex-col items-center gap-3">
      <img src="/generated/image-professional-female-bodybuilder-and-fitn-1765517441626-9.webp" alt="Founder" class="w-12 h-12 rounded-full object-cover" />
      <div class="text-center">
        <div class="font-medium text-sm">Aura Founder</div>
        <div class="text-gray-500 text-xs">2x Miss Olympia Champion</div>
      </div>
    </div>
  </section>

  <!-- Stats Grid -->
  <section class="py-12 px-6 max-w-7xl mx-auto border-t border-gray-200">
    <div class="grid md:grid-cols-3 gap-8 text-center md:text-left">
      <div>
        <h3 class="text-xl font-medium mb-2">Instant program access.</h3>
        <p class="text-gray-500 text-sm font-light">Complete your profile and receive your personalized training plan immediately. Start your first workout today.</p>
      </div>
      <div>
        <h3 class="text-xl font-medium mb-2">Progressive overload built in.</h3>
        <p class="text-gray-500 text-sm font-light">Your program automatically adjusts intensity based on your performance, ensuring continuous strength gains.</p>
      </div>
      <div>
        <h3 class="text-xl font-medium mb-2">Olympia-proven methodology.</h3>
        <p class="text-gray-500 text-sm font-light">Train with techniques refined at the highest level of competition, adapted specifically for women's physiology.</p>
      </div>
    </div>
  </section>

  <!-- How it works -->
  <section class="py-20 px-6 max-w-7xl mx-auto">
    <div class="mb-16 max-w-md">
      <h2 class="text-4xl font-medium mb-6">How it works.</h2>
      <p class="text-gray-600 font-light">From your first workout to your strongest self, Aura guides you through every rep. Personalized programming, expert coaching, and progress tracking combine to create transformations that last.</p>
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
                      <div class="font-bold text-xs mb-1">Strength Builder</div>
                      <div class="h-1 w-full bg-gray-200 rounded"></div>
                    </div>
                    <div class="p-3 border rounded-xl border-gray-200">
                       <div class="font-bold text-xs mb-1 text-gray-400">Body Recomp</div>
                       <div class="h-1 w-full bg-gray-100 rounded"></div>
                    </div>
                  </div>
                {:else if step.image === 'schedule'}
                   <div class="mt-4">
                     <div class="text-center font-bold mb-4">Fitness Profile</div>
                     <div class="bg-gray-100 h-32 rounded-xl mb-3 flex items-center justify-center text-xs text-gray-400">Profile Questions</div>
                     <button class="w-full bg-black text-white text-xs py-2 rounded-lg">Continue</button>
                   </div>
                {:else if step.image === 'results'}
                   <div class="bg-black h-full -mx-3 -mt-8 pt-10 px-3 text-white">
                      <div class="text-center mb-6">
                        <div class="w-12 h-12 bg-gray-700 rounded-full mx-auto mb-2"></div>
                        <div class="text-sm font-bold">Your Program</div>
                      </div>
                      <div class="space-y-2">
                         <div class="bg-gray-800 p-2 rounded-lg h-10"></div>
                         <div class="bg-gray-800 p-2 rounded-lg h-10"></div>
                      </div>
                   </div>
                {:else if step.image === 'notes'}
                   <div class="mt-4 space-y-3">
                      <div class="font-bold text-sm">Today's Workout</div>
                      <div class="text-[10px] text-gray-500 leading-relaxed">
                        3 sets × 8-10 reps
                      </div>
                      <div class="bg-gray-50 p-2 rounded text-[10px] text-gray-600">
                        Barbell Bench: 65 lbs → 70 lbs
                      </div>
                   </div>
                {:else}
                   <div class="mt-4 flex flex-col h-full">
                      <div class="flex-1">
                        <div class="bg-gray-100 p-2 rounded-lg rounded-tl-none text-[10px] mb-2 max-w-[80%]">
                          How do I know when to increase weight??
                        </div>
                        <div class="bg-blue-50 p-2 rounded-lg rounded-tr-none text-[10px] ml-auto max-w-[80%]">
                          When you can complete all sets with good form, increase by 5-10%
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
          <h3 class="text-sm font-medium text-gray-400 mb-2">Built by women, for women.</h3>
          <h2 class="text-2xl md:text-3xl font-medium max-w-xs">Join a community that understands your journey.</h2>
        </div>
        <!-- Abstract Visual -->
        <div class="absolute inset-0 flex items-center justify-center opacity-30 mt-20">
           <svg viewBox="0 0 200 100" class="w-full h-full text-gray-500 fill-current">
              <!-- Simplified dot representation -->
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
          <h2 class="text-2xl md:text-3xl font-medium max-w-xs">We're built to protect your privacy by default.</h2>
        </div>
        <!-- Blurred Text Visual -->
        <div class="absolute inset-0 flex items-center justify-center mt-20 overflow-hidden">
           <div class="text-4xl font-mono text-gray-600 opacity-20 blur-sm select-none break-all p-8">
             Workout|%d$9aT Progr|I7e/s Stren|&5g! Transf|?Pm_Lw
           </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Pricing Section -->
  <section class="py-24 px-6 max-w-7xl mx-auto" id="join">
    <div class="text-center mb-16">
      <h2 class="text-3xl md:text-4xl font-medium mb-4">Elite training for every woman.</h2>
      <p class="text-gray-500 font-light max-w-2xl mx-auto">Olympia-level expertise, personalized programming, and expert guidance—made accessible. Because investing in your strength is investing in yourself.</p>
    </div>

    <div class="grid md:grid-cols-2 gap-6 max-w-4xl mx-auto">
      <!-- Foundation Plan -->
      <div class="bg-white rounded-[32px] p-8 flex flex-col">
        <div class="w-12 h-12 bg-primary-100 rounded-full mb-6"></div>
        <h3 class="text-2xl font-medium mb-1">Foundation</h3>
        <p class="text-sm text-gray-500 mb-6">Begin your transformation journey.</p>
        <div class="mb-8">
          <span class="text-2xl font-medium">$29</span>
          <span class="text-gray-400 text-sm">/mo</span>
          <div class="text-[10px] text-primary-600 mt-1 font-medium">7-day free trial included</div>
        </div>
        <ul class="space-y-4 mb-8 flex-1">
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Personalized strength training programs adapted to your level.
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Progressive overload tracking and workout logging.
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Exercise library with form demonstrations and coaching cues.
          </li>
        </ul>
        <button class="w-full bg-[#1A1A1A] text-white py-3 rounded-sm font-medium hover:bg-black transition-colors">Start free trial</button>
      </div>

      <!-- Elite Plan -->
      <div class="bg-white rounded-[32px] p-8 flex flex-col relative overflow-hidden">
        <div class="absolute top-0 right-0 bg-primary-100 px-4 py-1 rounded-bl-xl text-xs font-medium text-primary-800">Most Popular</div>
        <div class="w-12 h-12 bg-primary-200 rounded-full mb-6"></div>
        <h3 class="text-2xl font-medium mb-1">Elite</h3>
        <p class="text-sm text-gray-500 mb-6">The complete transformation system.</p>
        <div class="mb-8">
          <span class="text-2xl font-medium">$49</span>
          <span class="text-gray-400 text-sm">/mo</span>
          <div class="text-[10px] text-primary-600 mt-1 font-medium">7-day free trial included</div>
        </div>
        <ul class="space-y-4 mb-8 flex-1">
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Everything in Foundation plus advanced programming options.
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Nutrition guidance and macro tracking integrated with training.
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Direct access to coaching team for form checks and program adjustments.
          </li>
        </ul>
        <button class="w-full bg-[#1A1A1A] text-white py-3 rounded-sm font-medium hover:bg-black transition-colors">Start free trial</button>
      </div>
    </div>
  </section>

  <!-- FAQ -->
  <section class="py-20 px-6 max-w-3xl mx-auto" id="faq">
    <h2 class="text-3xl font-medium text-center mb-12">Your questions answered.</h2>
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
        View all FAQs
      </button>
    </div>
  </section>

  <!-- Footer -->
  <footer class="py-16 px-6 border-t border-gray-200 bg-[#F9F8F6]">
    <div class="max-w-7xl mx-auto">
      <div class="flex flex-col md:flex-row justify-between items-start md:items-center gap-8 mb-16">
        <div class="flex items-center gap-2">
           <svg width="20" height="24" viewBox="0 0 82 97" fill="none" xmlns="http://www.w3.org/2000/svg">
             <path d="M53.7515 96.973C73.0977 96.973 83.4963 73.5156 70.1958 59.7314L69.954 59.4897L40.9346 30.4703L11.9153 59.4897L11.6735 59.7314C-1.8689 73.5156 8.77157 96.973 28.1178 96.973H53.7515Z" fill="#201B21"/>
             <path d="M11.9154 39.6597L15.5428 43.2872L40.9347 17.8952L66.3267 43.2872L69.9541 39.6597C79.1435 30.4703 82.7709 18.6208 81.8036 7.49668C81.32 3.14378 77.6925 0 73.3396 0H8.77168C4.41878 0 0.549534 3.14378 0.307706 7.49668C-0.901432 18.6208 2.48413 30.2285 11.9154 39.6597Z" fill="#201B21"/>
           </svg>
           <span class="font-bold text-lg tracking-wider">Aura</span>
        </div>
        
        <nav class="flex flex-wrap gap-6 md:gap-8 text-xs font-medium text-gray-600">
          <a href="#programs" class="hover:text-black">Programs</a>
          <a href="#faq" class="hover:text-black">FAQ</a>
          <a href="#" class="hover:text-black">Blog</a>
          <a href="#" class="hover:text-black">Terms & Conditions</a>
          <a href="#" class="hover:text-black">Privacy Policy</a>
        </nav>

        <div class="flex gap-4 text-gray-800">
          <a href="#" class="hover:text-black">{@html XIcon}</a>
          <a href="#" class="hover:text-black">{@html Instagram}</a>
          <a href="#" class="hover:text-black">{@html LinkedIn}</a>
        </div>
      </div>

      <div class="text-[10px] text-gray-400 leading-relaxed max-w-5xl">
        <p class="mb-2">Aura is a fitness technology platform providing personalized training programs. All fitness programs are designed for general wellness purposes and should not replace professional medical advice. Consult with a healthcare provider before beginning any new exercise program, especially if you have pre-existing health conditions. Results may vary based on individual effort, consistency, and adherence to the program. All information provided by Aura is for educational and informational purposes only.</p>
        <p>Aura's membership includes access to personalized training programs, exercise libraries, and progress tracking tools. Additional features and services may be available at different membership tiers. For complete details, see our Terms & Conditions.</p>
        <p class="mt-2">By providing your contact information, you agree to receive communications from Aura. Message and data rates may apply. Message frequency varies.</p>
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

