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

<header class="fixed top-0 left-0 right-0 z-50 transition-all duration-300 px-6 py-5 flex items-center justify-between {isScrolled ? 'bg-[#F9F8F6]/90 backdrop-blur-md shadow-sm' : 'bg-transparent'}">
  <div class="flex items-center">
    <!-- Logo -->
    <a href="/" class="flex items-center gap-2 group">
      <svg width="24" height="28" viewBox="0 0 82 97" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M53.7515 96.973C73.0977 96.973 83.4963 73.5156 70.1958 59.7314L69.954 59.4897L40.9346 30.4703L11.9153 59.4897L11.6735 59.7314C-1.8689 73.5156 8.77157 96.973 28.1178 96.973H53.7515Z" fill="#201B21"/>
        <path d="M11.9154 39.6597L15.5428 43.2872L40.9347 17.8952L66.3267 43.2872L69.9541 39.6597C79.1435 30.4703 82.7709 18.6208 81.8036 7.49668C81.32 3.14378 77.6925 0 73.3396 0H8.77168C4.41878 0 0.549534 3.14378 0.307706 7.49668C-0.901432 18.6208 2.48413 30.2285 11.9154 39.6597Z" fill="#201B21"/>
      </svg>
      <span class="font-bold text-xl tracking-wider text-[#1A1A1A]">Aura</span>
    </a>
  </div>

  <div class="flex items-center gap-8">
    <nav class="hidden md:flex items-center gap-8 text-[13px] font-medium text-gray-600">
      <a href="#programs" class="hover:text-black transition-colors">Programs</a>
      <a href="#faq" class="hover:text-black transition-colors">FAQ</a>
    </nav>
    <a href="#join" class="bg-[#1A1A1A] text-white text-[13px] font-medium px-5 py-2.5 rounded-sm hover:bg-black transition-colors">
      Start training
    </a>
  </div>
</header>