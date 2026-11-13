<!DOCTYPE html>
<html lang="id" class="scroll-smooth">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>KAVÉLIA Fleur — Flowers Speak What Words Cannot</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,500;0,600;0,700;1,400;1,600&family=Great+Vibes&family=Plus+Jakarta+Sans:wght@300;400;500;600;700&display=swap" rel="stylesheet" />

  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            cream: {
              50: '#FDFBF9',
              100: '#FAF4F0',
              200: '#F4E8E2',
              300: '#EAD6CD',
            },
            blush: {
              100: '#F9ECE9',
              200: '#F2D7D2',
              300: '#E8B8B1',
              400: '#DC9A91',
            },
            cocoa: {
              400: '#9F7D74',
              500: '#87635A',
              600: '#6E4F47',
              700: '#5C4039',
              800: '#49312B',
            },
            olive: {
              500: '#6E714A',
              600: '#5B5E3C',
            }
          },
          fontFamily: {
            serif: ['"Cormorant Garamond"', 'Georgia', 'serif'],
            script: ['"Great Vibes"', 'cursive'],
            sans: ['"Plus Jakarta Sans"', 'sans-serif'],
          },
          boxShadow: {
            soft: '0 10px 35px -10px rgba(92, 64, 57, 0.10)',
            card: '0 8px 24px -6px rgba(92, 64, 57, 0.08)',
          }
        }
      }
    };
  </script>

  <style>
    body {
      background-color: #FAF4F0;
      color: #5C4039;
      font-family: 'Plus Jakarta Sans', sans-serif;
      overflow-x: hidden;
    }

    .font-serif-display {
      font-family: 'Cormorant Garamond', Georgia, serif;
    }

    /* Custom Scrollbar */
    ::-webkit-scrollbar {
      width: 8px;
    }
    ::-webkit-scrollbar-track {
      background: #FAF4F0;
    }
    ::-webkit-scrollbar-thumb {
      background: #D8B9B0;
      border-radius: 99px;
    }
    ::-webkit-scrollbar-thumb:hover {
      background: #87635A;
    }

    /* Smooth Page Transition */
    .page-view {
      display: none;
      animation: fadeSlideUp 0.45s cubic-bezier(0.16, 1, 0.3, 1) forwards;
    }
    .page-view.active {
      display: block;
    }

    @keyframes fadeSlideUp {
      from {
        opacity: 0;
        transform: translateY(14px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    /* Arch Image Mask */
    .arch-mask {
      border-radius: 160px 160px 18px 18px;
    }
    .arch-side-mask {
      border-radius: 140px 18px 18px 18px;
    }

    /* Subtle Hero Zoom */
    @keyframes slowZoom {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.04); }
    }
    .hero-zoom {
      animation: slowZoom 18s ease-in-out infinite;
    }

    /* Glassmorphism Nav */
    .nav-scrolled {
      background: rgba(250, 244, 240, 0.92);
      backdrop-filter: blur(12px);
      box-shadow: 0 4px 24px rgba(92, 64, 57, 0.07);
    }
  </style>
</head>
<body class="antialiased selection:bg-blush-200 selection:text-cocoa-800">

  <!-- ==================== SVG SPRITE / BOTANICAL DECORATIONS ==================== -->
  <template id="botanical-corner-svg">
    <svg viewBox="0 0 220 320" fill="none" xmlns="http://www.w3.org/2000/svg" class="w-full h-full opacity-35 pointer-events-none select-none">
      <path d="M12 300C30 230 65 180 120 130C150 102 178 65 190 25" stroke="currentColor" stroke-width="1.2" stroke-linecap="round"/>
      <path d="M90 160C65 140 50 112 58 88C84 95 102 120 90 160Z" stroke="currentColor" stroke-width="1.2"/>
      <path d="M125 125C152 115 178 122 188 144C162 152 138 146 125 125Z" stroke="currentColor" stroke-width="1.2"/>
      <path d="M55 215C28 195 16 165 25 142C52 150 66 178 55 215Z" stroke="currentColor" stroke-width="1.2"/>
      <path d="M148 75C130 58 125 35 138 18C158 28 164 52 148 75Z" stroke="currentColor" stroke-width="1.2"/>
      <circle cx="192" cy="22" r="6" stroke="currentColor" stroke-width="1.2"/>
      <path d="M185 38C198 30 212 35 216 48C202 52 190 48 185 38Z" stroke="currentColor" stroke-width="1.2"/>
    </svg>
  </template>

  <!-- ==================== TOP ANNOUNCEMENT BAR ==================== -->
  <div id="top-bar" class="bg-cocoa-600 text-cream-100 text-xs py-2 px-4 transition-all duration-300">
    <div class="max-w-7xl mx-auto flex flex-wrap items-center justify-between gap-2">
      <div class="hidden md:flex items-center gap-1.5 opacity-85">
        <span>Jakarta Selatan</span>
        <span>•</span>
        <span>Same-Day Delivery</span>
      </div>
      <div class="mx-auto md:mx-0 flex items-center gap-2 font-medium tracking-wide">
        <span>✿ Free Greeting Card for Every Bouquet Order ♡</span>
      </div>
      <div class="hidden sm:flex items-center gap-4">
        <a href="#instagram" onclick="showToast('Membuka Instagram @kaveliafleur')" class="hover:text-blush-200 transition">Follow Our Instagram <span class="underline">@kaveliafleur</span></a>
        <button onclick="document.getElementById('top-bar').style.display='none'" class="opacity-70 hover:opacity-100 text-sm leading-none" aria-label="Tutup pengumuman">&times;</button>
      </div>
    </div>
  </div>

  <!-- ==================== HEADER / NAVBAR ==================== -->
  <header id="main-header" class="sticky top-0 z-40 bg-cream-100/95 border-b border-cream-300/60 transition-all duration-300">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-20 flex items-center justify-between">
      <!-- Brand Logo (Inspired by Uploaded Logo 3 & 4) -->
      <a href="#home" onclick="navigateTo('home'); return false;" class="flex items-center gap-2.5 group">
        <svg class="w-11 h-11 shrink-0 transition-transform duration-300 group-hover:scale-105" viewBox="0 0 120 120" fill="none" xmlns="http://www.w3.org/2000/svg">
          <!-- Serif K Monogram -->
          <path d="M30 22H52L46 28V92L52 98H28L34 92V28L30 22Z" fill="#6E714A"/>
          <path d="M44 68C58 50 75 26 95 26C106 26 112 34 108 44C106 49 102 52 98 52C102 45 101 34 91 34C78 34 62 52 46 72L44 68Z" fill="#6E714A"/>
          <path d="M46 66C66 56 80 68 92 84C98 92 106 94 114 88C105 100 90 102 79 88C68 74 58 68 46 74V66Z" fill="#6E714A"/>
          <!-- Olive Leaf -->
          <path d="M46 76C54 66 67 62 76 66C68 72 56 76 46 76Z" fill="#6E714A"/>
          <!-- Blush Lily Blossom -->
          <path d="M45 64C42 52 32 45 20 48C26 42 35 38 45 45C42 35 46 26 52 22C54 30 58 34 64 38C70 42 66 52 54 56C49 58 47 62 45 64Z" fill="#E8A7A1" stroke="#FAF4F0" stroke-width="1.5"/>
          <path d="M45 62C36 58 28 62 26 72C22 65 21 55 29 50C35 47 41 53 45 62Z" fill="#E8A7A1" stroke="#FAF4F0" stroke-width="1.5"/>
        </svg>
        <div class="leading-none">
          <div class="font-serif-display text-xl sm:text-2xl tracking-[0.14em] text-olive-600 font-semibold">KAVÉLIA</div>
          <div class="flex items-center gap-1.5 -mt-0.5">
            <span class="h-[1px] w-4 bg-blush-400"></span>
            <span class="font-script text-xl text-blush-400 leading-none">Fleur</span>
            <span class="h-[1px] w-4 bg-blush-400"></span>
          </div>
        </div>
      </a>

      <!-- Desktop Navigation -->
      <nav class="hidden lg:flex items-center gap-7 text-[14px] font-medium text-cocoa-600">
        <button onclick="navigateTo('about')" class="nav-link relative py-1 hover:text-cocoa-800 transition" data-nav="about">About Us</button>
        <div class="relative group">
          <button onclick="navigateTo('collection')" class="nav-link flex items-center gap-1 py-1 hover:text-cocoa-800 transition" data-nav="collection">
            Our Collection
            <svg class="w-3.5 h-3.5 transition-transform group-hover:rotate-180" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"/></svg>
          </button>
          <div class="absolute left-0 top-full pt-2 opacity-0 invisible group-hover:opacity-100 group-hover:visible transition-all duration-200 z-50">
            <div class="w-48 bg-cream-50 border border-cream-300 rounded-xl shadow-soft py-2 text-sm">
              <button onclick="navigateToCollection('Semua')" class="w-full text-left px-4 py-2 hover:bg-blush-100 text-cocoa-700">Semua Koleksi</button>
              <button onclick="navigateToCollection('Birthday')" class="w-full text-left px-4 py-2 hover:bg-blush-100 text-cocoa-700">Birthday Bouquet</button>
              <button onclick="navigateToCollection('Wisuda')" class="w-full text-left px-4 py-2 hover:bg-blush-100 text-cocoa-700">Wisuda</button>
              <button onclick="navigateToCollection('Romantic')" class="w-full text-left px-4 py-2 hover:bg-blush-100 text-cocoa-700">Anniversary & Romantic</button>
              <button onclick="navigateToCollection('Custom')" class="w-full text-left px-4 py-2 hover:bg-blush-100 text-cocoa-700">Custom Bouquet</button>
            </div>
          </div>
        </div>
        <button onclick="scrollToHomeSection('services-section')" class="nav-link relative py-1 hover:text-cocoa-800 transition">Services</button>
        <button onclick="navigateTo('gallery')" class="nav-link relative py-1 hover:text-cocoa-800 transition" data-nav="gallery">Gallery</button>
        <button onclick="scrollToHomeSection('testimonials-section')" class="nav-link relative py-1 hover:text-cocoa-800 transition">Testimonials</button>
        <button onclick="navigateTo('contact')" class="nav-link relative py-1 hover:text-cocoa-800 transition" data-nav="contact">Contact</button>
      </nav>

      <!-- Utility Icons -->
      <div class="flex items-center gap-2 sm:gap-3">
        <!-- Search Trigger -->
        <button onclick="toggleSearchModal(true)" class="p-2 rounded-full hover:bg-cream-200 text-cocoa-700 transition" aria-label="Cari buket">
          <svg class="w-5 h-5" fill="none" stroke="currentColor" stroke-width="1.7" viewBox="0 0 24 24"><circle cx="11" cy="11" r="7"/><path stroke-linecap="round" d="M20 20l-3.5-3.5"/></svg>
        </button>

        <!-- Wishlist Trigger -->
        <button onclick="toggleWishlistDrawer(true)" class="relative p-2 rounded-full hover:bg-cream-200 text-cocoa-700 transition" aria-label="Wishlist">
          <svg class="w-5 h-5" fill="none" stroke="currentColor" stroke-width="1.7" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"/></svg>
          <span id="wishlist-badge" class="hidden absolute -top-0.5 -right-0.5 min-w-[18px] h-[18px] px-1 bg-blush-400 text-white text-[10px] font-bold rounded-full flex items-center justify-center">0</span>
        </button>

        <!-- Cart Trigger -->
        <button onclick="toggleCartDrawer(true)" class="relative p-2 rounded-full hover:bg-cream-200 text-cocoa-700 transition" aria-label="Keranjang belanja">
          <svg class="w-5 h-5" fill="none" stroke="currentColor" stroke-width="1.7" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" d="M6 7h12l1 13H5L6 7z"/><path stroke-linecap="round" stroke-linejoin="round" d="M9 7V5a3 3 0 0 1 6 0v2"/></svg>
          <span id="cart-badge" class="hidden absolute -top-0.5 -right-0.5 min-w-[18px] h-[18px] px-1 bg-cocoa-600 text-white text-[10px] font-bold rounded-full flex items-center justify-center">0</span>
        </button>

        <!-- Mobile Menu Button -->
        <button onclick="toggleMobileMenu()" class="lg:hidden p-2 rounded-full hover:bg-cream-200 text-cocoa-700 transition" aria-label="Menu">
          <svg class="w-6 h-6" fill="none" stroke="currentColor" stroke-width="1.8" viewBox="0 0 24 24"><path stroke-linecap="round" d="M4 7h16M4 12h16M4 17h16"/></svg>
        </button>
      </div>
    </div>

    <!-- Mobile Navigation Drawer -->
    <div id="mobile-menu" class="hidden lg:hidden bg-cream-50 border-t border-cream-300 px-6 py-4 space-y-2 text-sm font-medium">
      <button onclick="navigateTo('home'); toggleMobileMenu();" class="block w-full text-left py-2 text-cocoa-700 hover:text-cocoa-900">Home</button>
      <button onclick="navigateTo('about'); toggleMobileMenu();" class="block w-full text-left py-2 text-cocoa-700 hover:text-cocoa-900">About Us</button>
      <button onclick="navigateTo('collection'); toggleMobileMenu();" class="block w-full text-left py-2 text-cocoa-700 hover:text-cocoa-900">Our Collection</button>
      <button onclick="scrollToHomeSection('services-section'); toggleMobileMenu();" class="block w-full text-left py-2 text-cocoa-700 hover:text-cocoa-900">Services</button>
      <button onclick="navigateTo('gallery'); toggleMobileMenu();" class="block w-full text-left py-2 text-cocoa-700 hover:text-cocoa-900">Gallery</button>
      <button onclick="scrollToHomeSection('testimonials-section'); toggleMobileMenu();" class="block w-full text-left py-2 text-cocoa-700 hover:text-cocoa-900">Testimonials</button>
      <button onclick="navigateTo('contact'); toggleMobileMenu();" class="block w-full text-left py-2 text-cocoa-700 hover:text-cocoa-900">Contact</button>
    </div>
  </header>

  <!-- ==================== MAIN CONTENT VIEWS ==================== -->
  <main>

    <!-- ========================================================= -->
    <!-- PAGE 1: HOME VIEW                                         -->
    <!-- ========================================================= -->
    <section id="view-home" class="page-view active">

      <!-- 1. HERO SLIDER SECTION -->
      <div class="relative overflow-hidden bg-gradient-to-br from-[#F7EAE4] via-[#F4DFD8] to-[#EBD0C8] border-b border-cream-300/70">
        <!-- Soft Sunlight Shadow Overlay -->
        <div class="absolute inset-0 pointer-events-none opacity-40" style="background: radial-gradient(circle at 20% 20%, #ffffff 0%, transparent 55%), radial-gradient(circle at 80% 70%, #E8B8B1 0%, transparent 50%);"></div>

        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12 md:py-20 lg:py-24 relative z-10">
          <div class="grid lg:grid-cols-12 gap-10 items-center">
            <!-- Left Text -->
            <div class="lg:col-span-6 space-y-6">
              <div class="flex items-center gap-3">
                <span class="text-xs tracking-[0.22em] uppercase text-cocoa-500 font-semibold">KAVÉLIA FLEUR</span>
                <span class="h-[1px] w-16 bg-cocoa-400/50"></span>
              </div>

              <h1 id="hero-title" class="font-serif-display text-4xl sm:text-5xl lg:text-[64px] leading-[1.06] text-cocoa-700 font-normal">
                Flowers speak<br/>what words cannot.
              </h1>

              <p id="hero-subtitle" class="text-cocoa-600 text-base sm:text-lg max-w-md leading-relaxed">
                Rangkaian bunga elegan untuk setiap momen berharga.
              </p>

              <div class="flex flex-wrap items-center gap-4 pt-2">
                <button onclick="navigateTo('collection')" class="inline-flex items-center gap-3 bg-cocoa-500 hover:bg-cocoa-600 text-cream-50 px-7 py-3.5 rounded-full text-sm font-medium shadow-soft transition-all hover:-translate-y-0.5">
                  <span>Jelajahi Koleksi</span>
                  <span>→</span>
                </button>
                <button onclick="openCustomModal()" class="inline-flex items-center gap-2 border border-cocoa-400/60 hover:bg-cream-50/70 text-cocoa-700 px-6 py-3.5 rounded-full text-sm font-medium transition">
                  <span>Request Custom</span>
                </button>
              </div>

              <!-- Hero Slider Controls -->
              <div class="pt-6 flex items-center gap-4 text-xs text-cocoa-500 font-medium">
                <button onclick="changeHeroSlide(-1)" class="w-7 h-7 rounded-full border border-cocoa-400/40 flex items-center justify-center hover:bg-cream-50 transition" aria-label="Slide sebelumnya">‹</button>
                <div class="flex items-center gap-2.5" id="hero-dots">
                  <button onclick="setHeroSlide(0)" class="hero-dot font-bold text-cocoa-800 scale-110 transition">01</button>
                  <span class="w-6 h-[1px] bg-cocoa-400/40"></span>
                  <button onclick="setHeroSlide(1)" class="hero-dot opacity-55 hover:opacity-100 transition">02</button>
                  <button onclick="setHeroSlide(2)" class="hero-dot opacity-55 hover:opacity-100 transition">03</button>
                </div>
                <button onclick="changeHeroSlide(1)" class="w-7 h-7 rounded-full border border-cocoa-400/40 flex items-center justify-center hover:bg-cream-50 transition" aria-label="Slide berikutnya">›</button>
              </div>
            </div>

            <!-- Right Hero Bouquet Showcase -->
            <div class="lg:col-span-6 relative flex justify-center">
              <div class="relative w-full max-w-lg aspect-[4/3.6] rounded-[36px] overflow-hidden shadow-2xl border-4 border-cream-50/70 bg-blush-100">
                <img id="hero-image"
                     src="https://images.unsplash.com/photo-1561181286-d3fee7d55364?auto=format&fit=crop&w=1000&q=85"
                     alt="Buket Mawar Blush KAVÉLIA Fleur"
                     onerror="handleImgError(this, 'Blush Romance')"
                     class="w-full h-full object-cover hero-zoom transition-opacity duration-500" />
                <!-- Floating Card Tag on Bouquet -->
                <div class="absolute bottom-6 right-6 bg-cream-50/95 backdrop-blur-sm px-5 py-3 rounded-xl shadow-lg border border-blush-200 -rotate-3">
                  <div class="font-serif-display text-sm tracking-[0.16em] text-cocoa-700 font-semibold">KAVÉLIA</div>
                  <div class="font-script text-lg text-blush-400 text-center -mt-1">Fleur</div>
                </div>
              </div>

              <!-- Scroll Indicator -->
              <button onclick="scrollToHomeSection('about-home-section')" class="hidden xl:flex flex-col items-center gap-2 absolute -right-4 bottom-4 text-cocoa-500 hover:text-cocoa-700 transition">
                <span class="text-[10px] tracking-widest uppercase">Scroll</span>
                <span class="w-9 h-9 rounded-full border border-cocoa-400/40 flex items-center justify-center text-sm animate-bounce">↓</span>
              </button>
            </div>
          </div>
        </div>
      </div>

      <!-- 2. ABOUT US (HOME PREVIEW SECTION) -->
      <div id="about-home-section" class="relative py-20 lg:py-24 overflow-hidden">
        <!-- Botanical Side Art -->
        <div class="hidden lg:block absolute left-0 top-10 w-44 h-64 text-cocoa-400 -translate-x-8">
          <div class="botanical-slot w-full h-full"></div>
        </div>
        <div class="hidden lg:block absolute right-0 top-6 w-44 h-64 text-cocoa-400 translate-x-8 scale-x-[-1]">
          <div class="botanical-slot w-full h-full"></div>
        </div>

        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
          <div class="grid lg:grid-cols-12 gap-10 items-center">
            <!-- Boutique Image -->
            <div class="lg:col-span-5">
              <div class="relative overflow-hidden arch-side-mask shadow-soft border-4 border-cream-50 bg-cream-200 aspect-[4/3]">
                <img src="https://images.unsplash.com/photo-1558350315-8aa00e6e4590?auto=format&fit=crop&w=900&q=80"
                     alt="Butik KAVÉLIA Fleur"
                     onerror="handleImgError(this, 'Butik KAVÉLIA')"
                     class="w-full h-full object-cover" />
                <div class="absolute inset-0 bg-gradient-to-t from-cocoa-800/45 via-transparent to-transparent flex items-center justify-center">
                  <div class="text-center text-cream-50 drop-shadow-md">
                    <div class="font-serif-display text-3xl tracking-[0.18em]">KAVÉLIA</div>
                    <div class="font-script text-3xl -mt-1 text-blush-100">Fleur</div>
                  </div>
                </div>
              </div>
            </div>

            <!-- Copywriting -->
            <div class="lg:col-span-4 space-y-4">
              <div class="flex items-center gap-3">
                <span class="text-xs tracking-[0.2em] uppercase text-cocoa-400 font-semibold">ABOUT US</span>
                <span class="h-[1px] w-10 bg-cocoa-400/50"></span>
              </div>
              <h2 class="font-serif-display text-3xl sm:text-4xl text-cocoa-700 leading-tight">
                Merangkai Cerita<br/>Lewat Bunga
              </h2>
              <p class="text-sm sm:text-base text-cocoa-600 leading-relaxed">
                KAVÉLIA Fleur adalah florist yang hadir untuk membawa keindahan bunga dalam setiap momen — dari ucapan sederhana hingga perayaan istimewa yang tak terlupakan.
              </p>
              <div class="pt-2">
                <button onclick="navigateTo('about')" class="inline-flex items-center gap-2.5 border border-cocoa-400/60 hover:bg-cocoa-500 hover:text-cream-50 text-cocoa-700 px-6 py-2.5 rounded-full text-sm font-medium transition">
                  <span>Tentang Kami</span>
                  <span>→</span>
                </button>
              </div>
            </div>

            <!-- 3 Key Values -->
            <div class="lg:col-span-3 space-y-5 lg:border-l border-cream-300 lg:pl-7">
              <div class="flex items-center gap-4">
                <div class="w-11 h-11 rounded-full bg-blush-100 border border-blush-200 flex items-center justify-center text-cocoa-600 shrink-0">
                  <svg class="w-5 h-5" fill="none" stroke="currentColor" stroke-width="1.6" viewBox="0 0 24 24"><path d="M12 2l3 6 6 1-4.5 4 1 6.5L12 16l-5.5 3.5 1-6.5L3 9l6-1 3-6z"/></svg>
                </div>
                <div>
                  <h4 class="text-sm font-semibold text-cocoa-700">Bunga Segar Berkualitas</h4>
                  <p class="text-xs text-cocoa-500">Dipilih langsung setiap pagi</p>
                </div>
              </div>
              <div class="flex items-center gap-4">
                <div class="w-11 h-11 rounded-full bg-blush-100 border border-blush-200 flex items-center justify-center text-cocoa-600 shrink-0">
                  <svg class="w-5 h-5" fill="none" stroke="currentColor" stroke-width="1.6" viewBox="0 0 24 24"><path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78L12 21.23l8.84-8.84a5.5 5.5 0 0 0 0-7.78z"/></svg>
                </div>
                <div>
                  <h4 class="text-sm font-semibold text-cocoa-700">Desain Elegan & Custom</h4>
                  <p class="text-xs text-cocoa-500">Disesuaikan dengan cerita Anda</p>
                </div>
              </div>
              <div class="flex items-center gap-4">
                <div class="w-11 h-11 rounded-full bg-blush-100 border border-blush-200 flex items-center justify-center text-cocoa-600 shrink-0">
                  <svg class="w-5 h-5" fill="none" stroke="currentColor" stroke-width="1.6" viewBox="0 0 24 24"><path d="M1 3h15v13H1zM16 8h4l3 3v5h-7V8z"/><circle cx="5.5" cy="18.5" r="2.5"/><circle cx="18.5" cy="18.5" r="2.5"/></svg>
                </div>
                <div>
                  <h4 class="text-sm font-semibold text-cocoa-700">Pengiriman Aman & Tepat Waktu</h4>
                  <p class="text-xs text-cocoa-500">Kurir khusus bunga terjaga</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- 3. OUR COLLECTION (HOME SECTION) -->
      <div class="py-16 lg:py-20 bg-cream-50/70 border-y border-cream-300/60">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div class="flex flex-col md:flex-row md:items-end justify-between gap-4 mb-8">
            <div class="md:text-center md:mx-auto">
              <div class="flex items-center md:justify-center gap-3 mb-2">
                <span class="h-[1px] w-8 bg-cocoa-400/50"></span>
                <span class="text-xs tracking-[0.2em] uppercase text-cocoa-400 font-semibold">OUR COLLECTION</span>
                <span class="h-[1px] w-8 bg-cocoa-400/50"></span>
              </div>
              <h2 class="font-serif-display text-3xl sm:text-4xl text-cocoa-700">Koleksi Buket Pilihan</h2>
              <p class="text-sm text-cocoa-500 mt-1">Temukan rangkaian bunga terbaik untuk setiap cerita.</p>
            </div>
            <button onclick="navigateTo('collection')" class="self-start md:self-auto inline-flex items-center gap-2 border border-cocoa-400/50 hover:bg-cocoa-500 hover:text-cream-50 text-cocoa-700 px-5 py-2 rounded-full text-xs font-medium transition shrink-0">
              <span>Lihat Semua Koleksi</span>
              <span>→</span>
            </button>
          </div>

          <!-- Filter Pills -->
          <div id="home-filter-pills" class="flex flex-wrap justify-center gap-2.5 mb-10">
            <button onclick="filterHomeProducts('Semua')" class="home-pill active bg-cocoa-500 text-cream-50 px-5 py-2 rounded-full text-xs font-medium transition">Semua</button>
            <button onclick="filterHomeProducts('Birthday')" class="home-pill bg-blush-100 text-cocoa-700 hover:bg-blush-200 px-5 py-2 rounded-full text-xs font-medium transition">Birthday</button>
            <button onclick="filterHomeProducts('Wisuda')" class="home-pill bg-blush-100 text-cocoa-700 hover:bg-blush-200 px-5 py-2 rounded-full text-xs font-medium transition">Wisuda</button>
            <button onclick="filterHomeProducts('Romantic')" class="home-pill bg-blush-100 text-cocoa-700 hover:bg-blush-200 px-5 py-2 rounded-full text-xs font-medium transition">Anniversary</button>
            <button onclick="filterHomeProducts('Custom')" class="home-pill bg-blush-100 text-cocoa-700 hover:bg-blush-200 px-5 py-2 rounded-full text-xs font-medium transition">Custom</button>
          </div>

          <!-- Product Grid -->
          <div id="home-product-grid" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
            <!-- Rendered by JS -->
          </div>
        </div>
      </div>

      <!-- 4. OUR SERVICES SECTION -->
      <div id="services-section" class="relative overflow-hidden bg-gradient-to-r from-blush-100/80 via-[#F5E1DC] to-blush-100/80 border-b border-cream-300/60">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16 lg:py-20">
          <div class="grid lg:grid-cols-12 gap-8 items-center">
            <!-- Left Rose Photo -->
            <div class="lg:col-span-3 hidden lg:block">
              <div class="rounded-3xl overflow-hidden shadow-soft border-4 border-cream-50 aspect-[4/4.5]">
                <img src="https://images.unsplash.com/photo-1518709268805-4e9042af9f23?auto=format&fit=crop&w=700&q=80"
                     alt="Bunga Mawar Segar"
                     onerror="handleImgError(this, 'Fresh Rose')"
                     class="w-full h-full object-cover" />
              </div>
            </div>

            <!-- Copywriting -->
            <div class="lg:col-span-4 space-y-4">
              <div class="flex items-center gap-3">
                <span class="text-xs tracking-[0.2em] uppercase text-cocoa-400 font-semibold">OUR SERVICES</span>
                <span class="h-[1px] w-10 bg-cocoa-400/50"></span>
              </div>
              <h2 class="font-serif-display text-3xl sm:text-4xl text-cocoa-700 leading-tight">
                Layanan Kami<br/>untukmu
              </h2>
              <p class="text-sm text-cocoa-600 leading-relaxed">
                Dari buket hingga pengiriman, kami selalu berusaha memberikan pengalaman terbaik agar setiap pesan tersampaikan sempurna.
              </p>
              <div class="pt-2">
                <button onclick="openCustomModal()" class="inline-flex items-center gap-2 bg-cream-50 hover:bg-cocoa-500 hover:text-cream-50 text-cocoa-700 border border-cocoa-400/40 px-6 py-2.5 rounded-full text-xs font-medium shadow-sm transition">
                  <span>Lihat Detail Layanan</span>
                  <span>→</span>
                </button>
              </div>
            </div>

            <!-- 4 Service Cards -->
            <div class="lg:col-span-5 grid grid-cols-2 gap-4">
              <div onclick="openCustomModal()" class="cursor-pointer bg-cream-50/90 hover:bg-cream-50 p-5 rounded-2xl border border-blush-200/80 shadow-card transition hover:-translate-y-1 text-center space-y-2">
                <div class="w-11 h-11 mx-auto rounded-full bg-blush-100 flex items-center justify-center text-cocoa-600">
                  <svg class="w-5 h-5" fill="none" stroke="currentColor" stroke-width="1.6" viewBox="0 0 24 24"><path d="M12 3c2 2 3 4 3 6a3 3 0 1 1-6 0c0-2 1-4 3-6z"/><path d="M12 12v9M8 17c1.5-1 3-1 4 0M16 15c-1.5-1-3-1-4 0"/></svg>
                </div>
                <h4 class="font-semibold text-sm text-cocoa-700">Buket Custom</h4>
                <p class="text-xs text-cocoa-500 leading-relaxed">Sesuaikan jenis bunga & warna favoritmu.</p>
              </div>

              <div onclick="showToast('Semua pesanan dilengkapi Gift Wrapping Premium!')" class="cursor-pointer bg-cream-50/90 hover:bg-cream-50 p-5 rounded-2xl border border-blush-200/80 shadow-card transition hover:-translate-y-1 text-center space-y-2">
                <div class="w-11 h-11 mx-auto rounded-full bg-blush-100 flex items-center justify-center text-cocoa-600">
                  <svg class="w-5 h-5" fill="none" stroke="currentColor" stroke-width="1.6" viewBox="0 0 24 24"><rect x="3" y="8" width="18" height="4" rx="1"/><path d="M12 8v13M5 12v8a1 1 0 0 0 1 1h12a1 1 0 0 0 1-1v-8M7.5 8a2.5 2.5 0 1 1 0-5C10 3 12 8 12 8s2-5 4.5-5a2.5 2.5 0 1 1 0 5"/></svg>
                </div>
                <h4 class="font-semibold text-sm text-cocoa-700">Gift Wrapping Premium</h4>
                <p class="text-xs text-cocoa-500 leading-relaxed">Kemasan elegan untuk kesan istimewa.</p>
              </div>

              <div onclick="showToast('Tersedia Same-Day & Instant Delivery area Jabodetabek.')" class="cursor-pointer bg-cream-50/90 hover:bg-cream-50 p-5 rounded-2xl border border-blush-200/80 shadow-card transition hover:-translate-y-1 text-center space-y-2">
                <div class="w-11 h-11 mx-auto rounded-full bg-blush-100 flex items-center justify-center text-cocoa-600">
                  <svg class="w-5 h-5" fill="none" stroke="currentColor" stroke-width="1.6" viewBox="0 0 24 24"><path d="M1 3h15v13H1zM16 8h4l3 3v5h-7V8z"/><circle cx="5.5" cy="18.5" r="2.5"/><circle cx="18.5" cy="18.5" r="2.5"/></svg>
                </div>
                <h4 class="font-semibold text-sm text-cocoa-700">Pengiriman Cepat</h4>
                <p class="text-xs text-cocoa-500 leading-relaxed">Aman dan tepat waktu ke tangan penerima.</p>
              </div>

              <div onclick="showToast('Gratis kartu ucapan cetak elegan di setiap order!')" class="cursor-pointer bg-cream-50/90 hover:bg-cream-50 p-5 rounded-2xl border border-blush-200/80 shadow-card transition hover:-translate-y-1 text-center space-y-2">
                <div class="w-11 h-11 mx-auto rounded-full bg-blush-100 flex items-center justify-center text-cocoa-600">
                  <svg class="w-5 h-5" fill="none" stroke="currentColor" stroke-width="1.6" viewBox="0 0 24 24"><rect x="3" y="5" width="18" height="14" rx="2"/><path d="M3 8l9 6 9-6"/></svg>
                </div>
                <h4 class="font-semibold text-sm text-cocoa-700">Kartu Ucapan Gratis</h4>
                <p class="text-xs text-cocoa-500 leading-relaxed">Sampaikan pesanmu dengan lebih bermakna.</p>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- 5. GALLERY & TESTIMONIALS COMBINED SECTION (LIKE MOCKUP 1) -->
      <div id="testimonials-section" class="relative py-20 overflow-hidden">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div class="grid lg:grid-cols-12 gap-12 items-center">
            <!-- Left: Mini Floral Gallery -->
            <div class="lg:col-span-6 space-y-5">
              <div class="flex items-end justify-between">
                <div>
                  <div class="flex items-center gap-3 mb-1">
                    <span class="text-xs tracking-[0.2em] uppercase text-cocoa-400 font-semibold">GALLERY</span>
                    <span class="h-[1px] w-8 bg-cocoa-400/50"></span>
                  </div>
                  <h2 class="font-serif-display text-3xl text-cocoa-700">Our Floral Gallery</h2>
                  <p class="text-xs sm:text-sm text-cocoa-500 mt-1">Koleksi momen indah bersama rangkaian KAVÉLIA Fleur.</p>
                </div>
                <button onclick="navigateTo('gallery')" class="text-xs font-medium text-cocoa-600 border border-cocoa-400/50 px-4 py-2 rounded-full hover:bg-cocoa-500 hover:text-cream-50 transition shrink-0">
                  Lihat Galeri →
                </button>
              </div>

              <div class="grid grid-cols-3 gap-3">
                <div onclick="openLightbox(0)" class="col-span-1 row-span-2 cursor-pointer overflow-hidden rounded-2xl border-2 border-cream-50 shadow-card group">
                  <img src="https://images.unsplash.com/photo-1526047932273-341f2a7631f9?auto=format&fit=crop&w=600&q=80" alt="Gallery 1" onerror="handleImgError(this, 'Floral Art')" class="w-full h-full object-cover group-hover:scale-105 transition duration-500"/>
                </div>
                <div onclick="openLightbox(1)" class="cursor-pointer overflow-hidden rounded-2xl border-2 border-cream-50 shadow-card aspect-square group">
                  <img src="https://images.unsplash.com/photo-1563241527-3004b7be0ffd?auto=format&fit=crop&w=600&q=80" alt="Gallery 2" onerror="handleImgError(this, 'Pink Roses')" class="w-full h-full object-cover group-hover:scale-105 transition duration-500"/>
                </div>
                <div onclick="openLightbox(2)" class="cursor-pointer overflow-hidden rounded-2xl border-2 border-cream-50 shadow-card aspect-square group">
                  <img src="https://images.unsplash.com/photo-1487530811176-3780de880c2d?auto=format&fit=crop&w=600&q=80" alt="Gallery 3" onerror="handleImgError(this, 'Warm Bouquet')" class="w-full h-full object-cover group-hover:scale-105 transition duration-500"/>
                </div>
                <div onclick="openLightbox(3)" class="col-span-2 cursor-pointer overflow-hidden rounded-2xl border-2 border-cream-50 shadow-card h-36 group">
                  <img src="https://images.unsplash.com/photo-1591886960571-74d43a9d4166?auto=format&fit=crop&w=800&q=80" alt="Gallery 4" onerror="handleImgError(this, 'Tulip Joy')" class="w-full h-full object-cover group-hover:scale-105 transition duration-500"/>
                </div>
              </div>
            </div>

            <!-- Right: Testimonials Carousel -->
            <div class="lg:col-span-6 space-y-5">
              <div>
                <div class="flex items-center gap-3 mb-1">
                  <span class="text-xs tracking-[0.2em] uppercase text-cocoa-400 font-semibold">TESTIMONIALS</span>
                  <span class="h-[1px] w-8 bg-cocoa-400/50"></span>
                </div>
                <h2 class="font-serif-display text-3xl text-cocoa-700">Apa Kata Mereka?</h2>
                <p class="text-xs sm:text-sm text-cocoa-500 mt-1">Kepuasan pelanggan adalah prioritas utama kami.</p>
              </div>

              <div class="relative bg-cream-50 border border-cream-300/80 rounded-3xl p-7 shadow-soft">
                <div class="flex items-start gap-5">
                  <img id="testi-avatar" src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?auto=format&fit=crop&w=200&q=80" alt="Pelanggan" class="w-14 h-14 rounded-full object-cover border-2 border-blush-200 shrink-0"/>
                  <div class="space-y-3 flex-1">
                    <p id="testi-quote" class="text-cocoa-700 text-sm sm:text-base italic leading-relaxed">
                      "Buketnya cantik banget! Pengemasannya rapi, bunganya masih sangat segar, dan pengirimannya juga cepat."
                    </p>
                    <div class="flex items-center justify-between pt-2 border-t border-cream-200">
                      <div>
                        <div id="testi-name" class="font-semibold text-sm text-cocoa-700">— Alya F.</div>
                        <div id="testi-tag" class="text-[11px] text-cocoa-400">Pembeli Blush Romance Bouquet</div>
                      </div>
                      <div class="text-amber-400 text-sm tracking-widest">★★★★★</div>
                    </div>
                  </div>
                </div>

                <!-- Controls -->
                <div class="flex items-center justify-end gap-2 mt-5">
                  <button onclick="changeTestimonial(-1)" class="w-8 h-8 rounded-full border border-cream-300 hover:bg-blush-100 flex items-center justify-center text-cocoa-600 transition" aria-label="Testimoni sebelumnya">‹</button>
                  <button onclick="changeTestimonial(1)" class="w-8 h-8 rounded-full border border-cream-300 hover:bg-blush-100 flex items-center justify-center text-cocoa-600 transition" aria-label="Testimoni berikutnya">›</button>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- 6. NEWSLETTER BANNER -->
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 pb-20">
        <div class="relative overflow-hidden rounded-3xl bg-gradient-to-r from-[#B89288] via-[#B48C82] to-[#C8A49B] text-cream-50 p-8 md:p-12 shadow-soft">
          <div class="grid lg:grid-cols-12 gap-6 items-center relative z-10">
            <div class="lg:col-span-5 space-y-2">
              <h3 class="font-serif-display text-3xl">Berlangganan Newsletter</h3>
              <p class="text-xs sm:text-sm text-cream-100/90 leading-relaxed">
                Dapatkan informasi koleksi terbaru, promo spesial, dan inspirasi buket langsung di email kamu.
              </p>
            </div>
            <form onsubmit="handleNewsletter(event, 'main-newsletter-email')" class="lg:col-span-5 flex flex-col sm:flex-row gap-3">
              <input id="main-newsletter-email" type="email" required placeholder="Masukkan email kamu" class="flex-1 px-5 py-3 rounded-full bg-cream-50 text-cocoa-800 placeholder:text-cocoa-400 text-sm focus:outline-none focus:ring-2 focus:ring-blush-200"/>
              <button type="submit" class="bg-cocoa-700 hover:bg-cocoa-800 text-cream-50 px-6 py-3 rounded-full text-sm font-medium transition shrink-0">
                Berlangganan →
              </button>
            </form>
            <div class="hidden lg:block lg:col-span-2">
              <img src="https://images.unsplash.com/photo-1561181286-d3fee7d55364?auto=format&fit=crop&w=400&q=80" alt="Newsletter Bouquet" class="w-28 h-24 object-cover rounded-2xl ml-auto border-2 border-cream-50/50 rotate-3 shadow-lg"/>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- ========================================================= -->
    <!-- PAGE 2: ABOUT US VIEW (Matching Mockup 2 Top-Right)       -->
    <!-- ========================================================= -->
    <section id="view-about" class="page-view">
      <!-- Page Banner -->
      <div class="relative bg-gradient-to-r from-[#F3E2DC] via-[#EAD2CA] to-[#F3E2DC] border-b border-cream-300 overflow-hidden">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-14 flex items-center justify-between">
          <div class="space-y-2 relative z-10">
            <span class="text-xs uppercase tracking-[0.2em] text-cocoa-500">KAVÉLIA FLEUR</span>
            <h1 class="font-serif-display text-4xl sm:text-5xl text-cocoa-700">About Us</h1>
            <p class="text-sm sm:text-base text-cocoa-600">Lebih dari sekadar bunga, kami merangkai emosi.</p>
          </div>
          <img src="https://images.unsplash.com/photo-1561181286-d3fee7d55364?auto=format&fit=crop&w=600&q=80" alt="About Banner" class="hidden sm:block w-64 h-36 object-cover rounded-3xl border-2 border-cream-50 shadow-soft"/>
        </div>
      </div>

      <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 py-16 lg:py-20">
        <div class="grid md:grid-cols-12 gap-12 items-center">
          <div class="md:col-span-5 flex justify-center">
            <div class="w-72 h-72 sm:w-80 sm:h-80 rounded-full overflow-hidden border-8 border-cream-50 shadow-soft">
              <img src="https://images.unsplash.com/photo-1526047932273-341f2a7631f9?auto=format&fit=crop&w=800&q=80" alt="Tentang KAVÉLIA Fleur" class="w-full h-full object-cover"/>
            </div>
          </div>

          <div class="md:col-span-7 space-y-6">
            <h2 class="font-serif-display text-3xl sm:text-4xl text-cocoa-700">Tentang KAVÉLIA Fleur</h2>
            <p class="text-cocoa-600 leading-relaxed">
              KAVÉLIA Fleur adalah florist butik yang berdiri untuk membawa keindahan bunga segar dalam setiap momen spesialmu. Kami percaya bahwa setiap kelopak dan tangkai memiliki bahasa emosinya sendiri — mulai dari ungkapan syukur, cinta, perayaan kelulusan, hingga penghiburan yang hangat.
            </p>
            <p class="text-cocoa-600 leading-relaxed">
              Setiap rangkaian kami dirangkai secara <em>handcrafted</em> oleh florist berpengalaman dengan pemilihan kertas pembungkus premium dan pita satin berkarakter lembut.
            </p>

            <!-- Visi, Misi, Nilai -->
            <div class="grid sm:grid-cols-3 gap-4 pt-4">
              <div class="bg-cream-50 p-5 rounded-2xl border border-cream-300 text-center space-y-2 shadow-card">
                <div class="w-10 h-10 mx-auto rounded-full bg-blush-100 flex items-center justify-center text-cocoa-600">✧</div>
                <h4 class="font-serif-display text-xl text-cocoa-700 font-semibold">Visi</h4>
                <p class="text-xs text-cocoa-500 leading-relaxed">Menjadi florist terpercaya dan inspiratif di setiap perayaan hidup.</p>
              </div>
              <div class="bg-cream-50 p-5 rounded-2xl border border-cream-300 text-center space-y-2 shadow-card">
                <div class="w-10 h-10 mx-auto rounded-full bg-blush-100 flex items-center justify-center text-cocoa-600">♡</div>
                <h4 class="font-serif-display text-xl text-cocoa-700 font-semibold">Misi</h4>
                <p class="text-xs text-cocoa-500 leading-relaxed">Menyebarkan kebahagiaan melalui rangkaian bunga penuh makna.</p>
              </div>
              <div class="bg-cream-50 p-5 rounded-2xl border border-cream-300 text-center space-y-2 shadow-card">
                <div class="w-10 h-10 mx-auto rounded-full bg-blush-100 flex items-center justify-center text-cocoa-600">✿</div>
                <h4 class="font-serif-display text-xl text-cocoa-700 font-semibold">Nilai</h4>
                <p class="text-xs text-cocoa-500 leading-relaxed">Kualitas segar, kreativitas desain, dan ketulusan pelayanan.</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- ========================================================= -->
    <!-- PAGE 3: OUR COLLECTION VIEW (Matching Mockup 2 Mid-Right) -->
    <!-- ========================================================= -->
    <section id="view-collection" class="page-view">
      <!-- Page Banner -->
      <div class="relative bg-gradient-to-r from-[#F3E2DC] via-[#EAD2CA] to-[#F3E2DC] border-b border-cream-300">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-14 flex items-center justify-between">
          <div class="space-y-2">
            <span class="text-xs uppercase tracking-[0.2em] text-cocoa-500">KATALOG LENGKAP</span>
            <h1 class="font-serif-display text-4xl sm:text-5xl text-cocoa-700">Our Collection</h1>
            <p class="text-sm sm:text-base text-cocoa-600">Temukan rangkaian bunga terbaik untuk setiap cerita.</p>
          </div>
          <img src="https://images.unsplash.com/photo-1563241527-3004b7be0ffd?auto=format&fit=crop&w=600&q=80" alt="Collection Banner" class="hidden sm:block w-64 h-36 object-cover rounded-3xl border-2 border-cream-50 shadow-soft"/>
        </div>
      </div>

      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
        <div class="flex flex-col md:flex-row justify-between items-start md:items-center gap-4 mb-8 pb-4 border-b border-cream-300">
          <div id="collection-count" class="text-sm text-cocoa-600">Menampilkan semua rangkaian bunga</div>
          <div class="flex items-center gap-3">
            <label for="sort-select" class="text-xs text-cocoa-500">Urutkan:</label>
            <select id="sort-select" onchange="renderCollectionPage()" class="bg-cream-50 border border-cream-300 rounded-full px-4 py-2 text-xs text-cocoa-700 focus:outline-none">
              <option value="featured">Terbaru & Populer</option>
              <option value="price-asc">Harga Terendah</option>
              <option value="price-desc">Harga Tertinggi</option>
            </select>
          </div>
        </div>

        <div class="grid lg:grid-cols-12 gap-8">
          <!-- Sidebar Filter -->
          <aside class="lg:col-span-3 space-y-6">
            <div class="bg-cream-50 p-6 rounded-2xl border border-cream-300 space-y-4">
              <h3 class="font-serif-display text-xl text-cocoa-700 font-semibold">Kategori</h3>
              <div id="sidebar-categories" class="space-y-2.5 text-sm">
                <!-- Rendered by JS -->
              </div>
            </div>

            <div class="bg-blush-100/70 p-6 rounded-2xl border border-blush-200 space-y-3">
              <h4 class="font-serif-display text-xl text-cocoa-700">Butuh Buket Custom?</h4>
              <p class="text-xs text-cocoa-600 leading-relaxed">Konsultasikan kombinasi bunga dan budget sesuai keinginan Anda bersama florist kami.</p>
              <button onclick="openCustomModal()" class="w-full bg-cocoa-500 hover:bg-cocoa-600 text-cream-50 py-2.5 rounded-full text-xs font-medium transition">Buat Buket Custom</button>
            </div>
          </aside>

          <!-- Products Grid -->
          <div class="lg:col-span-9">
            <div id="collection-product-grid" class="grid grid-cols-1 sm:grid-cols-2 xl:grid-cols-3 gap-6">
              <!-- Rendered by JS -->
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- ========================================================= -->
    <!-- PAGE 4: GALLERY VIEW (Matching Mockup 2 Lower-Right)      -->
    <!-- ========================================================= -->
    <section id="view-gallery" class="page-view">
      <div class="relative bg-gradient-to-r from-[#F3E2DC] via-[#EAD2CA] to-[#F3E2DC] border-b border-cream-300">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-14 flex items-center justify-between">
          <div class="space-y-2">
            <span class="text-xs uppercase tracking-[0.2em] text-cocoa-500">PORTFOLIO BUNGA</span>
            <h1 class="font-serif-display text-4xl sm:text-5xl text-cocoa-700">Gallery</h1>
            <p class="text-sm sm:text-base text-cocoa-600">Potret keindahan dalam setiap rangkaian KAVÉLIA Fleur.</p>
          </div>
          <img src="https://images.unsplash.com/photo-1487530811176-3780de880c2d?auto=format&fit=crop&w=600&q=80" alt="Gallery Banner" class="hidden sm:block w-64 h-36 object-cover rounded-3xl border-2 border-cream-50 shadow-soft"/>
        </div>
      </div>

      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-14">
        <div id="full-gallery-grid" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-5">
          <!-- Rendered by JS -->
        </div>
      </div>
    </section>

    <!-- ========================================================= -->
    <!-- PAGE 5: CONTACT US VIEW (Matching Mockup 2 Bottom-Right)  -->
    <!-- ========================================================= -->
    <section id="view-contact" class="page-view">
      <div class="relative bg-gradient-to-r from-[#F3E2DC] via-[#EAD2CA] to-[#F3E2DC] border-b border-cream-300">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-14 flex items-center justify-between">
          <div class="space-y-2">
            <span class="text-xs uppercase tracking-[0.2em] text-cocoa-500">HUBUNGI KAMI</span>
            <h1 class="font-serif-display text-4xl sm:text-5xl text-cocoa-700">Contact Us</h1>
            <p class="text-sm sm:text-base text-cocoa-600">Kami selalu siap membantu merangkai momen spesialmu.</p>
          </div>
          <img src="https://images.unsplash.com/photo-1558350315-8aa00e6e4590?auto=format&fit=crop&w=600&q=80" alt="Contact Banner" class="hidden sm:block w-64 h-36 object-cover rounded-3xl border-2 border-cream-50 shadow-soft"/>
        </div>
      </div>

      <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
        <div class="grid md:grid-cols-12 gap-10 items-start">
          <!-- Contact Details -->
          <div class="md:col-span-5 space-y-6">
            <div class="bg-cream-50 p-7 rounded-3xl border border-cream-300 space-y-6 shadow-card">
              <div class="flex items-start gap-4">
                <div class="w-10 h-10 rounded-full bg-blush-100 flex items-center justify-center text-cocoa-600 shrink-0">📍</div>
                <div>
                  <h4 class="font-semibold text-sm text-cocoa-700">Alamat Butik</h4>
                  <p class="text-xs sm:text-sm text-cocoa-500 mt-0.5 leading-relaxed">Jl. Melati No. 12, Jakarta Selatan<br/>DKI Jakarta 12545</p>
                </div>
              </div>

              <div class="flex items-start gap-4">
                <div class="w-10 h-10 rounded-full bg-blush-100 flex items-center justify-center text-cocoa-600 shrink-0">📞</div>
                <div>
                  <h4 class="font-semibold text-sm text-cocoa-700">WhatsApp</h4>
                  <p class="text-xs sm:text-sm text-cocoa-500 mt-0.5">+62 812 3456 7890</p>
                </div>
              </div>

              <div class="flex items-start gap-4">
                <div class="w-10 h-10 rounded-full bg-blush-100 flex items-center justify-center text-cocoa-600 shrink-0">✉</div>
                <div>
                  <h4 class="font-semibold text-sm text-cocoa-700">Email</h4>
                  <p class="text-xs sm:text-sm text-cocoa-500 mt-0.5">hello@kaveliafleur.id</p>
                </div>
              </div>

              <div class="pt-3 border-t border-cream-200">
                <h4 class="font-semibold text-xs uppercase tracking-wider text-cocoa-400 mb-3">Jam Operasional</h4>
                <p class="text-xs text-cocoa-600">Senin – Minggu: 08.00 – 20.00 WIB</p>
              </div>
            </div>
          </div>

          <!-- Contact Form -->
          <div class="md:col-span-7">
            <form onsubmit="handleContactSubmit(event)" class="bg-cream-50 p-8 rounded-3xl border border-cream-300 shadow-soft space-y-5">
              <h3 class="font-serif-display text-2xl sm:text-3xl text-cocoa-700">Kirim Pesan</h3>
              <div>
                <label class="block text-xs font-medium text-cocoa-600 mb-1.5">Nama Lengkap</label>
                <input type="text" required placeholder="Contoh: Alya Putri" class="w-full px-4 py-3 rounded-xl bg-cream-100/70 border border-cream-300 text-sm focus:outline-none focus:ring-2 focus:ring-blush-300"/>
              </div>
              <div>
                <label class="block text-xs font-medium text-cocoa-600 mb-1.5">Email / Nomor WhatsApp</label>
                <input type="text" required placeholder="email@contoh.com atau 0812..." class="w-full px-4 py-3 rounded-xl bg-cream-100/70 border border-cream-300 text-sm focus:outline-none focus:ring-2 focus:ring-blush-300"/>
              </div>
              <div>
                <label class="block text-xs font-medium text-cocoa-600 mb-1.5">Pesan Kamu</label>
                <textarea rows="4" required placeholder="Ceritakan kebutuhan buket atau acara spesialmu..." class="w-full px-4 py-3 rounded-xl bg-cream-100/70 border border-cream-300 text-sm focus:outline-none focus:ring-2 focus:ring-blush-300"></textarea>
              </div>
              <div class="flex justify-end">
                <button type="submit" class="bg-cocoa-500 hover:bg-cocoa-600 text-cream-50 px-8 py-3 rounded-full text-sm font-medium transition shadow-sm">
                  Kirim Pesan →
                </button>
              </div>
            </form>
          </div>
        </div>
      </div>
    </section>

  </main>

  <!-- ==================== FOOTER ==================== -->
  <footer class="relative overflow-hidden bg-cocoa-700 text-cream-100 pt-16 pb-8">
    <!-- Botanical Footer Corner Art -->
    <div class="hidden md:block absolute left-0 bottom-0 w-44 h-64 text-blush-200/30">
      <div class="botanical-slot w-full h-full"></div>
    </div>
    <div class="hidden md:block absolute right-0 bottom-0 w-44 h-64 text-blush-200/30 scale-x-[-1]">
      <div class="botanical-slot w-full h-full"></div>
    </div>

    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-12 gap-10 pb-12 border-b border-cream-100/15">
        <!-- Brand Info -->
        <div class="lg:col-span-4 space-y-4">
          <div class="flex items-center gap-3">
            <svg class="w-10 h-10 shrink-0" viewBox="0 0 120 120" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M30 22H52L46 28V92L52 98H28L34 92V28L30 22Z" fill="#FAF4F0"/>
              <path d="M44 68C58 50 75 26 95 26C106 26 112 34 108 44C106 49 102 52 98 52C102 45 101 34 91 34C78 34 62 52 46 72L44 68Z" fill="#FAF4F0"/>
              <path d="M46 66C66 56 80 68 92 84C98 92 106 94 114 88C105 100 90 102 79 88C68 74 58 68 46 74V66Z" fill="#FAF4F0"/>
              <path d="M45 64C42 52 32 45 20 48C26 42 35 38 45 45C42 35 46 26 52 22C54 30 58 34 64 38C70 42 66 52 54 56C49 58 47 62 45 64Z" fill="#E8B8B1"/>
            </svg>
            <div>
              <div class="font-serif-display text-2xl tracking-[0.15em]">KAVÉLIA</div>
              <div class="font-script text-xl text-blush-200 -mt-1">Fleur</div>
            </div>
          </div>
          <p class="text-sm text-cream-200/80 italic font-serif-display text-lg">Flowers for every story.</p>
          <p class="text-xs text-cream-200/70 max-w-xs leading-relaxed">
            Florist butik di Jakarta Selatan yang merangkai bunga segar pilihan dengan estetika elegan dan penuh kehangatan.
          </p>
        </div>

        <!-- Navigasi -->
        <div class="lg:col-span-2 space-y-3 text-sm">
          <h4 class="font-semibold text-cream-50">Navigasi</h4>
          <ul class="space-y-2 text-xs text-cream-200/80">
            <li><button onclick="navigateTo('home')" class="hover:text-blush-200 transition">Home</button></li>
            <li><button onclick="navigateTo('about')" class="hover:text-blush-200 transition">About Us</button></li>
            <li><button onclick="navigateTo('collection')" class="hover:text-blush-200 transition">Our Collection</button></li>
            <li><button onclick="scrollToHomeSection('services-section')" class="hover:text-blush-200 transition">Services</button></li>
            <li><button onclick="navigateTo('gallery')" class="hover:text-blush-200 transition">Gallery</button></li>
            <li><button onclick="navigateTo('contact')" class="hover:text-blush-200 transition">Contact</button></li>
          </ul>
        </div>

        <!-- Hubungi Kami -->
        <div class="lg:col-span-3 space-y-3 text-sm">
          <h4 class="font-semibold text-cream-50">Hubungi Kami</h4>
          <ul class="space-y-2.5 text-xs text-cream-200/80">
            <li class="flex items-center gap-2"><span>📞</span><span>+62 812 3456 7890</span></li>
            <li class="flex items-center gap-2"><span>✉</span><span>hello@kaveliafleur.id</span></li>
            <li class="flex items-center gap-2"><span>📍</span><span>Jl. Melati No. 12, Jakarta Selatan</span></li>
          </ul>
          <div class="flex items-center gap-3 pt-2">
            <button onclick="showToast('@kaveliafleur di Instagram')" class="w-8 h-8 rounded-full border border-cream-100/25 hover:bg-cream-100/15 flex items-center justify-center text-xs transition">IG</button>
            <button onclick="showToast('@kaveliafleur di TikTok')" class="w-8 h-8 rounded-full border border-cream-100/25 hover:bg-cream-100/15 flex items-center justify-center text-xs transition">TT</button>
            <button onclick="showToast('KAVÉLIA Fleur di Pinterest')" class="w-8 h-8 rounded-full border border-cream-100/25 hover:bg-cream-100/15 flex items-center justify-center text-xs transition">PI</button>
          </div>
        </div>

        <!-- Ikuti Kami -->
        <div class="lg:col-span-3 space-y-3 text-sm">
          <h4 class="font-semibold text-cream-50">Ikuti Kami</h4>
          <p class="text-xs text-cream-200/80">Dapatkan update koleksi & promo terbaru!</p>
          <form onsubmit="handleNewsletter(event, 'footer-newsletter-email')" class="flex">
            <input id="footer-newsletter-email" type="email" required placeholder="Masukkan email kamu" class="w-full px-4 py-2.5 rounded-l-full bg-cream-50 text-cocoa-800 text-xs focus:outline-none"/>
            <button type="submit" class="bg-cocoa-500 hover:bg-cocoa-400 px-4 py-2.5 rounded-r-full text-xs font-medium transition">→</button>
          </form>
        </div>
      </div>

      <div class="pt-6 flex flex-col sm:flex-row items-center justify-between gap-3 text-xs text-cream-200/70">
        <div>© 2025 KAVÉLIA Fleur. All rights reserved.</div>
        <div class="flex items-center gap-4">
          <span>Made with ♡ for flower lovers.</span>
          <button onclick="window.scrollTo({top:0, behavior:'smooth'})" class="w-8 h-8 rounded-full bg-cream-50 text-cocoa-700 hover:bg-blush-200 flex items-center justify-center font-bold transition" aria-label="Kembali ke atas">↑</button>
        </div>
      </div>
    </div>
  </footer>

  <!-- ==================== MODALS & DRAWERS ==================== -->

  <!-- 1. Product Quick View Modal -->
  <div id="product-modal" class="hidden fixed inset-0 z-50 bg-cocoa-800/50 backdrop-blur-sm flex items-center justify-center p-4">
    <div class="bg-cream-50 rounded-3xl max-w-2xl w-full overflow-hidden shadow-2xl border border-cream-300 grid sm:grid-cols-2 relative animate-[fadeSlideUp_0.3s_ease]">
      <button onclick="closeProductModal()" class="absolute top-4 right-4 z-10 w-8 h-8 rounded-full bg-cream-50/90 text-cocoa-700 hover:bg-blush-100 flex items-center justify-center font-bold shadow">&times;</button>
      <div class="bg-blush-100 aspect-square sm:aspect-auto">
        <img id="modal-img" src="" alt="" class="w-full h-full object-cover"/>
      </div>
      <div class="p-6 sm:p-7 flex flex-col justify-between space-y-4">
        <div class="space-y-3">
          <span id="modal-cat" class="inline-block text-[11px] uppercase tracking-widest bg-blush-100 text-cocoa-600 px-3 py-1 rounded-full font-medium"></span>
          <h3 id="modal-title" class="font-serif-display text-2xl sm:text-3xl text-cocoa-700"></h3>
          <div id="modal-price" class="text-lg font-semibold text-cocoa-600"></div>
          <p id="modal-desc" class="text-xs text-cocoa-500 leading-relaxed"></p>

          <div class="pt-2 space-y-2">
            <label class="block text-xs font-medium text-cocoa-700">Pilih Warna Wrapping:</label>
            <div class="flex gap-2" id="wrap-options">
              <button type="button" onclick="selectWrap(this, 'Blush Pink')" class="wrap-btn px-3 py-1.5 rounded-full text-xs border border-cocoa-500 bg-cocoa-500 text-cream-50">Blush Pink</button>
              <button type="button" onclick="selectWrap(this, 'Warm Cream')" class="wrap-btn px-3 py-1.5 rounded-full text-xs border border-cream-300 bg-cream-100 text-cocoa-700">Warm Cream</button>
              <button type="button" onclick="selectWrap(this, 'Sage Olive')" class="wrap-btn px-3 py-1.5 rounded-full text-xs border border-cream-300 bg-cream-100 text-cocoa-700">Sage Olive</button>
            </div>
          </div>

          <div class="space-y-1.5">
            <label class="block text-xs font-medium text-cocoa-700">Kartu Ucapan Gratis:</label>
            <input id="modal-card-note" type="text" placeholder="Tulis pesan singkat untuk penerima..." class="w-full px-3.5 py-2 rounded-xl bg-cream-100 border border-cream-300 text-xs focus:outline-none focus:ring-1 focus:ring-cocoa-400"/>
          </div>
        </div>

        <button id="modal-add-btn" class="w-full bg-cocoa-500 hover:bg-cocoa-600 text-cream-50 py-3 rounded-full text-sm font-medium transition shadow-soft">
          Tambah ke Keranjang
        </button>
      </div>
    </div>
  </div>

  <!-- 2. Custom Bouquet & Service Detail Modal -->
  <div id="custom-modal" class="hidden fixed inset-0 z-50 bg-cocoa-800/50 backdrop-blur-sm flex items-center justify-center p-4">
    <div class="bg-cream-50 rounded-3xl max-w-lg w-full p-7 shadow-2xl border border-cream-300 relative space-y-5">
      <button onclick="document.getElementById('custom-modal').classList.add('hidden')" class="absolute top-5 right-5 w-8 h-8 rounded-full bg-cream-200 text-cocoa-700 flex items-center justify-center font-bold">&times;</button>
      <div>
        <span class="text-xs uppercase tracking-widest text-cocoa-400">LAYANAN EKSKLUSIF</span>
        <h3 class="font-serif-display text-3xl text-cocoa-700 mt-1">Request Buket Custom</h3>
        <p class="text-xs text-cocoa-500 mt-1">Rancang buket impianmu sesuai nuansa acara dan preferensi bunga.</p>
      </div>
      <form onsubmit="handleCustomSubmit(event)" class="space-y-4">
        <div>
          <label class="block text-xs font-medium text-cocoa-600 mb-1">Pilihan Bunga Utama</label>
          <select id="custom-flower" class="w-full px-4 py-2.5 rounded-xl bg-cream-100 border border-cream-300 text-sm text-cocoa-700">
            <option>Mawar Pink & Baby's Breath</option>
            <option>Tulip Pastel Import</option>
            <option>Bunga Matahari & Chamomile</option>
            <option>Mix Seasonal Flowers (Romantic)</option>
          </select>
        </div>
        <div class="grid grid-cols-2 gap-3">
          <div>
            <label class="block text-xs font-medium text-cocoa-600 mb-1">Estimasi Budget</label>
            <select id="custom-budget" class="w-full px-4 py-2.5 rounded-xl bg-cream-100 border border-cream-300 text-sm text-cocoa-700">
              <option>Rp 200.000 – Rp 350.000</option>
              <option>Rp 350.000 – Rp 600.000</option>
              <option>Diatas Rp 600.000 (Luxury)</option>
            </select>
          </div>
          <div>
            <label class="block text-xs font-medium text-cocoa-600 mb-1">Tanggal Kirim</label>
            <input type="date" required class="w-full px-3 py-2.5 rounded-xl bg-cream-100 border border-cream-300 text-sm text-cocoa-700"/>
          </div>
        </div>
        <div>
          <label class="block text-xs font-medium text-cocoa-600 mb-1">Catatan Nuansa / Kartu Ucapan</label>
          <textarea rows="3" required placeholder="Misal: Nuansa soft pink & cream untuk acara wisuda..." class="w-full px-4 py-2.5 rounded-xl bg-cream-100 border border-cream-300 text-sm"></textarea>
        </div>
        <button type="submit" class="w-full bg-cocoa-500 hover:bg-cocoa-600 text-cream-50 py-3 rounded-full text-sm font-medium transition">
          Kirim Permintaan Custom →
        </button>
      </form>
    </div>
  </div>

  <!-- 3. Search Modal -->
  <div id="search-modal" class="hidden fixed inset-0 z-50 bg-cocoa-800/45 backdrop-blur-sm flex items-start justify-center pt-24 p-4">
    <div class="bg-cream-50 rounded-3xl max-w-xl w-full p-6 shadow-2xl border border-cream-300 space-y-4">
      <div class="flex items-center gap-3 border-b border-cream-300 pb-3">
        <svg class="w-5 h-5 text-cocoa-400" fill="none" stroke="currentColor" stroke-width="1.8" viewBox="0 0 24 24"><circle cx="11" cy="11" r="7"/><path stroke-linecap="round" d="M20 20l-3.5-3.5"/></svg>
        <input id="search-input" oninput="handleSearch(this.value)" type="text" placeholder="Cari buket mawar, tulip, wisuda, birthday..." class="w-full bg-transparent text-sm text-cocoa-800 focus:outline-none"/>
        <button onclick="toggleSearchModal(false)" class="text-cocoa-500 hover:text-cocoa-800 text-xl leading-none">&times;</button>
      </div>
      <div id="search-results" class="max-h-72 overflow-y-auto divide-y divide-cream-200">
        <!-- Rendered by JS -->
      </div>
    </div>
  </div>

  <!-- 4. Cart Drawer -->
  <div id="cart-drawer" class="hidden fixed inset-0 z-50 bg-cocoa-800/45 backdrop-blur-sm flex justify-end">
    <div class="bg-cream-50 w-full max-w-md h-full flex flex-col justify-between shadow-2xl border-l border-cream-300">
      <div class="p-6 border-b border-cream-300 flex items-center justify-between">
        <div>
          <h3 class="font-serif-display text-2xl text-cocoa-700">Keranjang Belanja</h3>
          <p class="text-xs text-cocoa-400">Gratis kartu ucapan di setiap buket</p>
        </div>
        <button onclick="toggleCartDrawer(false)" class="w-8 h-8 rounded-full bg-cream-200 text-cocoa-700 flex items-center justify-center font-bold">&times;</button>
      </div>

      <div id="cart-items" class="flex-1 overflow-y-auto p-6 space-y-4">
        <!-- Rendered by JS -->
      </div>

      <div class="p-6 border-t border-cream-300 bg-cream-100/70 space-y-4">
        <div class="flex items-center justify-between text-sm font-semibold text-cocoa-700">
          <span>Subtotal</span>
          <span id="cart-subtotal">Rp 0</span>
        </div>
        <button onclick="checkoutWhatsApp()" class="w-full bg-cocoa-500 hover:bg-cocoa-600 text-cream-50 py-3.5 rounded-full text-sm font-medium transition shadow-soft">
          Pesan Sekarang via WhatsApp →
        </button>
      </div>
    </div>
  </div>

  <!-- 5. Wishlist Drawer -->
  <div id="wishlist-drawer" class="hidden fixed inset-0 z-50 bg-cocoa-800/45 backdrop-blur-sm flex justify-end">
    <div class="bg-cream-50 w-full max-w-md h-full flex flex-col justify-between shadow-2xl border-l border-cream-300">
      <div class="p-6 border-b border-cream-300 flex items-center justify-between">
        <div>
          <h3 class="font-serif-display text-2xl text-cocoa-700">Favorit Saya</h3>
          <p class="text-xs text-cocoa-400">Simpan rangkaian bunga pilihanmu</p>
        </div>
        <button onclick="toggleWishlistDrawer(false)" class="w-8 h-8 rounded-full bg-cream-200 text-cocoa-700 flex items-center justify-center font-bold">&times;</button>
      </div>
      <div id="wishlist-items" class="flex-1 overflow-y-auto p-6 space-y-4"></div>
    </div>
  </div>

  <!-- 6. Lightbox Modal -->
  <div id="lightbox-modal" class="hidden fixed inset-0 z-50 bg-cocoa-800/80 backdrop-blur-sm flex items-center justify-center p-4">
    <button onclick="closeLightbox()" class="absolute top-6 right-6 w-10 h-10 rounded-full bg-cream-50 text-cocoa-700 font-bold text-xl flex items-center justify-center">&times;</button>
    <button onclick="stepLightbox(-1)" class="absolute left-4 sm:left-8 w-10 h-10 rounded-full bg-cream-50/80 text-cocoa-800 font-bold text-xl flex items-center justify-center">‹</button>
    <div class="max-w-3xl w-full text-center space-y-3">
      <img id="lightbox-img" src="" alt="Gallery Preview" class="max-h-[78vh] mx-auto rounded-2xl border-4 border-cream-50 shadow-2xl object-contain"/>
      <p id="lightbox-caption" class="text-cream-100 text-sm font-serif-display tracking-wide"></p>
    </div>
    <button onclick="stepLightbox(1)" class="absolute right-4 sm:right-8 w-10 h-10 rounded-full bg-cream-50/80 text-cocoa-800 font-bold text-xl flex items-center justify-center">›</button>
  </div>

  <!-- 7. Toast Notification -->
  <div id="toast" class="fixed bottom-6 left-1/2 -translate-x-1/2 z-[60] bg-cocoa-800 text-cream-50 px-6 py-3 rounded-full text-xs sm:text-sm font-medium shadow-xl opacity-0 pointer-events-none transition-all duration-300"></div>

  <!-- ==================== JAVASCRIPT ==================== -->
  <script>
    // -------- 1. DATA --------
    const products = [
      {
        id: 1,
        name: "Blush Romance Bouquet",
        category: "Romantic",
        tag: "Buket Mawar",
        price: 225000,
        image: "https://images.unsplash.com/photo-1561181286-d3fee7d55364?auto=format&fit=crop&w=700&q=80",
        desc: "Kombinasi mawar blush segar dengan baby's breath lembut dalam balutan wrapping sutra bernuansa pastel."
      },
      {
        id: 2,
        name: "Sunlit Bouquet",
        category: "Wisuda",
        tag: "Buket Sunflower",
        price: 185000,
        image: "https://images.unsplash.com/photo-1597848212624-a19eb35e2651?auto=format&fit=crop&w=700&q=80",
        desc: "Bunga matahari cerah yang melambangkan semangat dan kebahagiaan, sempurna untuk hadiah wisuda atau ulang tahun."
      },
      {
        id: 3,
        name: "Sweet Tulip",
        category: "Birthday",
        tag: "Buket Tulip",
        price: 240000,
        image: "https://images.unsplash.com/photo-1520763185298-1b434c919102?auto=format&fit=crop&w=700&q=80",
        desc: "Rangkaian bunga tulip pink import yang minimalis, manis, dan berkelas untuk ungkapan kasih sayang."
      },
      {
        id: 4,
        name: "Everlasting Love",
        category: "Romantic",
        tag: "Buket Mix Flower",
        price: 210000,
        image: "https://images.unsplash.com/photo-1487530811176-3780de880c2d?auto=format&fit=crop&w=700&q=80",
        desc: "Perpaduan harmonis mawar peach, carnation, dan dedaunan eucalyptus harum yang menenangkan."
      },
      {
        id: 5,
        name: "Dreamy Pink",
        category: "Birthday",
        tag: "Buket Mawar",
        price: 230000,
        image: "https://images.unsplash.com/photo-1563241527-3004b7be0ffd?auto=format&fit=crop&w=700&q=80",
        desc: "Rangkaian bunga penuh nuansa dreamy pink dengan pita satin elegan untuk merayakan hari lahir orang tersayang."
      },
      {
        id: 6,
        name: "Elegant White",
        category: "Custom",
        tag: "Buket Putih",
        price: 220000,
        image: "https://images.unsplash.com/photo-1526047932273-341f2a7631f9?auto=format&fit=crop&w=700&q=80",
        desc: "Kesucian bunga putih pilihan dengan aksen krem hangat, cocok untuk acara formal, tunangan, maupun ucapan tulus."
      }
    ];

    const heroSlides = [
      {
        title: "Flowers speak<br/>what words cannot.",
        subtitle: "Rangkaian bunga elegan untuk setiap momen berharga.",
        image: "https://images.unsplash.com/photo-1561181286-d3fee7d55364?auto=format&fit=crop&w=1000&q=85"
      },
      {
        title: "Elegance crafted<br/>in every petal.",
        subtitle: "Bunga segar pilihan yang dirangkai penuh ketulusan setiap hari.",
        image: "https://images.unsplash.com/photo-1526047932273-341f2a7631f9?auto=format&fit=crop&w=1000&q=85"
      },
      {
        title: "Celebrate love<br/>with timeless blooms.",
        subtitle: "Sampaikan rasa terima kasih, cinta, dan doa lewat buket istimewa.",
        image: "https://images.unsplash.com/photo-1487530811176-3780de880c2d?auto=format&fit=crop&w=1000&q=85"
      }
    ];

    const galleryPhotos = [
      { src: "https://images.unsplash.com/photo-1526047932273-341f2a7631f9?auto=format&fit=crop&w=900&q=80", caption: "Blush Peony & Rose Arrangement — KAVÉLIA Fleur" },
      { src: "https://images.unsplash.com/photo-1563241527-3004b7be0ffd?auto=format&fit=crop&w=900&q=80", caption: "Soft Pink Garden Roses Edition" },
      { src: "https://images.unsplash.com/photo-1487530811176-3780de880c2d?auto=format&fit=crop&w=900&q=80", caption: "Warm Peach & Eucalyptus Hand Bouquet" },
      { src: "https://images.unsplash.com/photo-1591886960571-74d43a9d4166?auto=format&fit=crop&w=900&q=80", caption: "Pastel Tulip Morning Harvest" },
      { src: "https://images.unsplash.com/photo-1558350315-8aa00e6e4590?auto=format&fit=crop&w=900&q=80", caption: "Sudut Butik KAVÉLIA Fleur Jakarta" },
      { src: "https://images.unsplash.com/photo-1597848212624-a19eb35e2651?auto=format&fit=crop&w=900&q=80", caption: "Sunlit Graduation Bouquet" }
    ];

    const testimonials = [
      {
        quote: '"Buketnya cantik banget! Pengemasannya rapi, bunganya masih sangat segar, dan pengirimannya juga cepat."',
        name: "— Alya F.",
        tag: "Pembeli Blush Romance Bouquet",
        avatar: "https://images.unsplash.com/photo-1534528741775-53994a69daeb?auto=format&fit=crop&w=200&q=80"
      },
      {
        quote: '"Pelayanan sangat baik dan ramah. Hasil rangkaiannya bahkan lebih cantik daripada ekspektasi saya!"',
        name: "— Dinda R.",
        tag: "Pembeli Sweet Tulip",
        avatar: "https://images.unsplash.com/photo-1544005313-94ddf0286df2?auto=format&fit=crop&w=200&q=80"
      },
      {
        quote: '"KAVÉLIA Fleur selalu jadi pilihan utama untuk setiap momen spesial keluarga kami. Kartu ucapannya juga estetik."',
        name: "— Sarah A.",
        tag: "Pelanggan Setia Jakarta Selatan",
        avatar: "https://images.unsplash.com/photo-1517841905240-472988babdf9?auto=format&fit=crop&w=200&q=80"
      }
    ];

    // -------- 2. STATE --------
    let currentHeroIdx = 0;
    let currentTestiIdx = 0;
    let currentLightboxIdx = 0;
    let homeFilter = "Semua";
    let collectionCategory = "Semua";
    let selectedWrap = "Blush Pink";
    let wishlist = [];
    let cart = [];

    // -------- 3. HELPERS --------
    function formatRp(num) {
      return "Rp " + num.toLocaleString("id-ID");
    }

    function handleImgError(img, label) {
      const svg = encodeURIComponent(`
        <svg xmlns="http://www.w3.org/2000/svg" width="600" height="600" viewBox="0 0 600 600">
          <rect width="600" height="600" fill="#F2D7D2"/>
          <circle cx="300" cy="270" r="95" fill="#E8B8B1" opacity="0.5"/>
          <text x="50%" y="52%" text-anchor="middle" font-family="Georgia, serif" font-size="26" fill="#5C4039">${label}</text>
          <text x="50%" y="59%" text-anchor="middle" font-family="sans-serif" font-size="14" fill="#87635A">KAVÉLIA Fleur</text>
        </svg>
      `);
      img.src = `data:image/svg+xml;charset=UTF-8,${svg}`;
    }

    let toastTimer;
    function showToast(msg) {
      const toast = document.getElementById("toast");
      toast.textContent = msg;
      toast.classList.remove("opacity-0", "translate-y-3");
      toast.classList.add("opacity-100", "translate-y-0");
      clearTimeout(toastTimer);
      toastTimer = setTimeout(() => {
        toast.classList.remove("opacity-100", "translate-y-0");
        toast.classList.add("opacity-0", "translate-y-3");
      }, 2800);
    }

    // -------- 4. NAVIGATION (SPA VIEWS) --------
    function navigateTo(viewName) {
      document.querySelectorAll(".page-view").forEach(el => el.classList.remove("active"));
      const target = document.getElementById(`view-${viewName}`);
      if (target) target.classList.add("active");

      document.querySelectorAll(".nav-link").forEach(btn => {
        btn.classList.remove("text-cocoa-800", "font-semibold", "underline", "underline-offset-8");
        if (btn.dataset.nav === viewName) {
          btn.classList.add("text-cocoa-800", "font-semibold", "underline", "underline-offset-8");
        }
      });

      if (viewName === "collection") renderCollectionPage();
      if (viewName === "gallery") renderFullGallery();
      window.scrollTo({ top: 0, behavior: "smooth" });
    }

    function navigateToCollection(cat) {
      collectionCategory = cat;
      navigateTo("collection");
    }

    function scrollToHomeSection(id) {
      navigateTo("home");
      setTimeout(() => {
        const el = document.getElementById(id);
        if (el) el.scrollIntoView({ behavior: "smooth", block: "start" });
      }, 80);
    }

    function toggleMobileMenu() {
      document.getElementById("mobile-menu").classList.toggle("hidden");
    }

    // -------- 5. HERO SLIDER --------
    function setHeroSlide(idx) {
      currentHeroIdx = idx;
      const slide = heroSlides[idx];
      const img = document.getElementById("hero-image");
      img.style.opacity = "0";
      setTimeout(() => {
        document.getElementById("hero-title").innerHTML = slide.title;
        document.getElementById("hero-subtitle").textContent = slide.subtitle;
        img.src = slide.image;
        img.style.opacity = "1";
      }, 220);

      document.querySelectorAll(".hero-dot").forEach((dot, i) => {
        if (i === idx) {
          dot.classList.add("font-bold", "text-cocoa-800", "scale-110");
          dot.classList.remove("opacity-55");
        } else {
          dot.classList.remove("font-bold", "text-cocoa-800", "scale-110");
          dot.classList.add("opacity-55");
        }
      });
    }

    function changeHeroSlide(dir) {
      const next = (currentHeroIdx + dir + heroSlides.length) % heroSlides.length;
      setHeroSlide(next);
    }

    setInterval(() => changeHeroSlide(1), 6500);

    // -------- 6. PRODUCT RENDERING --------
    function createProductCard(product, showPrice = true) {
      const isWishlisted = wishlist.includes(product.id);
      return `
        <div class="group bg-cream-50 rounded-2xl border border-cream-300/80 overflow-hidden shadow-card hover:shadow-soft transition-all duration-300 hover:-translate-y-1 flex flex-col">
          <div class="relative aspect-[4/4.2] overflow-hidden bg-blush-100 cursor-pointer" onclick="openProductModal(${product.id})">
            <img src="${product.image}" alt="${product.name}" onerror="handleImgError(this, '${product.name}')" class="w-full h-full object-cover group-hover:scale-105 transition duration-500"/>
            <button onclick="event.stopPropagation(); toggleWishlist(${product.id})" class="absolute top-3 right-3 w-8 h-8 rounded-full bg-cream-50/90 hover:bg-cream-50 flex items-center justify-center shadow-sm transition ${isWishlisted ? 'text-blush-400' : 'text-cocoa-500'}" aria-label="Simpan ke favorit">
              ${isWishlisted ? '♥' : '♡'}
            </button>
            <div class="absolute bottom-3 left-3 bg-cream-50/90 backdrop-blur-sm px-3 py-1 rounded-full text-[10px] font-medium text-cocoa-600">
              ${product.tag}
            </div>
          </div>
          <div class="p-4 flex-1 flex flex-col justify-between space-y-3">
            <div class="cursor-pointer" onclick="openProductModal(${product.id})">
              <h3 class="font-serif-display text-lg text-cocoa-700 font-semibold leading-snug group-hover:text-cocoa-500 transition">${product.name}</h3>
              ${showPrice ? `<div class="text-sm font-semibold text-cocoa-500 mt-1">${formatRp(product.price)}</div>` : ''}
            </div>
            <div class="flex items-center gap-2 pt-1">
              <button onclick="quickAddToCart(${product.id})" class="flex-1 bg-blush-100 hover:bg-cocoa-500 hover:text-cream-50 text-cocoa-700 py-2 rounded-full text-xs font-medium transition">
                + Keranjang
              </button>
              <button onclick="openProductModal(${product.id})" class="px-3 py-2 rounded-full border border-cream-300 hover:bg-cream-200 text-xs text-cocoa-600 transition" title="Detail">
                Detail
              </button>
            </div>
          </div>
        </div>
      `;
    }

    function filterHomeProducts(cat) {
      homeFilter = cat;
      document.querySelectorAll(".home-pill").forEach(pill => {
        if (pill.textContent.trim() === cat || (cat === "Romantic" && pill.textContent.trim() === "Anniversary")) {
          pill.className = "home-pill active bg-cocoa-500 text-cream-50 px-5 py-2 rounded-full text-xs font-medium transition";
        } else {
          pill.className = "home-pill bg-blush-100 text-cocoa-700 hover:bg-blush-200 px-5 py-2 rounded-full text-xs font-medium transition";
        }
      });
      renderHomeProducts();
    }

    function renderHomeProducts() {
      const container = document.getElementById("home-product-grid");
      const filtered = homeFilter === "Semua"
        ? products.slice(0, 4)
        : products.filter(p => p.category === homeFilter);
      const list = filtered.length ? filtered.slice(0, 4) : products.slice(0, 4);
      container.innerHTML = list.map(p => createProductCard(p, true)).join("");
    }

    function renderCollectionPage() {
      const categories = ["Semua", "Birthday", "Wisuda", "Romantic", "Custom"];
      document.getElementById("sidebar-categories").innerHTML = categories.map(cat => `
        <label class="flex items-center gap-2.5 cursor-pointer text-cocoa-600 hover:text-cocoa-800">
          <input type="radio" name="cat-filter" value="${cat}" ${collectionCategory === cat ? "checked" : ""} onchange="collectionCategory='${cat}'; renderCollectionPage();" class="accent-cocoa-600"/>
          <span>${cat === "Romantic" ? "Romantic & Anniversary" : cat}</span>
        </label>
      `).join("");

      let list = collectionCategory === "Semua"
        ? [...products]
        : products.filter(p => p.category === collectionCategory);

      const sortVal = document.getElementById("sort-select")?.value || "featured";
      if (sortVal === "price-asc") list.sort((a, b) => a.price - b.price);
      if (sortVal === "price-desc") list.sort((a, b) => b.price - a.price);

      document.getElementById("collection-count").textContent = `Menampilkan ${list.length} rangkaian bunga (${collectionCategory})`;
      document.getElementById("collection-product-grid").innerHTML = list.map(p => createProductCard(p, true)).join("");
    }

    // -------- 7. PRODUCT QUICK VIEW MODAL --------
    function openProductModal(id) {
      const p = products.find(item => item.id === id);
      if (!p) return;
      document.getElementById("modal-img").src = p.image;
      document.getElementById("modal-cat").textContent = p.category + " • " + p.tag;
      document.getElementById("modal-title").textContent = p.name;
      document.getElementById("modal-price").textContent = formatRp(p.price);
      document.getElementById("modal-desc").textContent = p.desc;
      document.getElementById("modal-card-note").value = "";

      document.getElementById("modal-add-btn").onclick = () => {
        const note = document.getElementById("modal-card-note").value.trim();
        addToCart(p, selectedWrap, note);
        closeProductModal();
        toggleCartDrawer(true);
      };

      document.getElementById("product-modal").classList.remove("hidden");
    }

    function closeProductModal() {
      document.getElementById("product-modal").classList.add("hidden");
    }

    function selectWrap(btn, name) {
      selectedWrap = name;
      document.querySelectorAll(".wrap-btn").forEach(b => {
        b.className = "wrap-btn px-3 py-1.5 rounded-full text-xs border border-cream-300 bg-cream-100 text-cocoa-700";
      });
      btn.className = "wrap-btn px-3 py-1.5 rounded-full text-xs border border-cocoa-500 bg-cocoa-500 text-cream-50";
    }

    // -------- 8. CART & WISHLIST --------
    function quickAddToCart(id) {
      const p = products.find(item => item.id === id);
      if (p) addToCart(p, "Blush Pink", "");
    }

    function addToCart(product, wrap, note) {
      const existing = cart.find(c => c.id === product.id && c.wrap === wrap && c.note === note);
      if (existing) {
        existing.qty += 1;
      } else {
        cart.push({ ...product, wrap, note, qty: 1 });
      }
      updateCartUI();
      showToast(`${product.name} ditambahkan ke keranjang ♡`);
    }

    function updateCartQty(idx, delta) {
      cart[idx].qty += delta;
      if (cart[idx].qty <= 0) cart.splice(idx, 1);
      updateCartUI();
    }

    function updateCartUI() {
      const totalItems = cart.reduce((sum, item) => sum + item.qty, 0);
      const badge = document.getElementById("cart-badge");
      badge.textContent = totalItems;
      badge.classList.toggle("hidden", totalItems === 0);

      const container = document.getElementById("cart-items");
      if (!cart.length) {
        container.innerHTML = `<div class="text-center py-16 text-cocoa-400 text-sm space-y-2"><div class="text-3xl">✿</div><p>Keranjangmu masih kosong.</p></div>`;
        document.getElementById("cart-subtotal").textContent = "Rp 0";
        return;
      }

      let subtotal = 0;
      container.innerHTML = cart.map((item, idx) => {
        subtotal += item.price * item.qty;
        return `
          <div class="flex gap-3.5 bg-cream-100/70 p-3 rounded-2xl border border-cream-300">
            <img src="${item.image}" alt="${item.name}" class="w-16 h-16 rounded-xl object-cover shrink-0"/>
            <div class="flex-1 min-w-0">
              <h4 class="font-semibold text-sm text-cocoa-700 truncate">${item.name}</h4>
              <p class="text-[11px] text-cocoa-400">Wrap: ${item.wrap}</p>
              ${item.note ? `<p class="text-[11px] text-cocoa-500 italic truncate">"${item.note}"</p>` : ""}
              <div class="flex items-center justify-between mt-2">
                <span class="text-xs font-semibold text-cocoa-600">${formatRp(item.price * item.qty)}</span>
                <div class="flex items-center gap-2 bg-cream-50 border border-cream-300 rounded-full px-2 py-0.5 text-xs">
                  <button onclick="updateCartQty(${idx}, -1)" class="px-1 font-bold">-</button>
                  <span>${item.qty}</span>
                  <button onclick="updateCartQty(${idx}, 1)" class="px-1 font-bold">+</button>
                </div>
              </div>
            </div>
          </div>
        `;
      }).join("");

      document.getElementById("cart-subtotal").textContent = formatRp(subtotal);
    }

    function toggleCartDrawer(open) {
      document.getElementById("cart-drawer").classList.toggle("hidden", !open);
      updateCartUI();
    }

    function checkoutWhatsApp() {
      if (!cart.length) return showToast("Pilih buket terlebih dahulu.");
      const summary = cart.map(c => `- ${c.name} (${c.qty}x, Wrap: ${c.wrap}${c.note ? ', Kartu: "' + c.note + '"' : ''})`).join("%0A");
      const total = document.getElementById("cart-subtotal").textContent;
      const url = `https://wa.me/6281234567890?text=Halo%20KAVÉLIA%20Fleur,%20saya%20ingin%20memesan:%0A${summary}%0A%0ATotal:%20${total}`;
      window.open(url, "_blank");
    }

    function toggleWishlist(id) {
      const idx = wishlist.indexOf(id);
      if (idx > -1) {
        wishlist.splice(idx, 1);
        showToast("Dihapus dari favorit");
      } else {
        wishlist.push(id);
        showToast("Disimpan ke favorit ♥");
      }
      updateWishlistUI();
      renderHomeProducts();
      if (document.getElementById("view-collection").classList.contains("active")) renderCollectionPage();
    }

    function updateWishlistUI() {
      const badge = document.getElementById("wishlist-badge");
      badge.textContent = wishlist.length;
      badge.classList.toggle("hidden", wishlist.length === 0);

      const container = document.getElementById("wishlist-items");
      if (!wishlist.length) {
        container.innerHTML = `<div class="text-center py-16 text-cocoa-400 text-sm">Belum ada rangkaian bunga favorit.</div>`;
        return;
      }

      container.innerHTML = wishlist.map(id => {
        const p = products.find(item => item.id === id);
        return `
          <div class="flex items-center gap-3 bg-cream-100/70 p-3 rounded-2xl border border-cream-300">
            <img src="${p.image}" class="w-16 h-16 rounded-xl object-cover"/>
            <div class="flex-1">
              <h4 class="font-semibold text-sm text-cocoa-700">${p.name}</h4>
              <p class="text-xs text-cocoa-500">${formatRp(p.price)}</p>
            </div>
            <button onclick="quickAddToCart(${p.id})" class="bg-cocoa-500 text-cream-50 px-3 py-1.5 rounded-full text-xs">+ Keranjang</button>
          </div>
        `;
      }).join("");
    }

    function toggleWishlistDrawer(open) {
      document.getElementById("wishlist-drawer").classList.toggle("hidden", !open);
      updateWishlistUI();
    }

    // -------- 9. TESTIMONIALS, GALLERY & SEARCH --------
    function changeTestimonial(dir) {
      currentTestiIdx = (currentTestiIdx + dir + testimonials.length) % testimonials.length;
      const t = testimonials[currentTestiIdx];
      document.getElementById("testi-quote").textContent = t.quote;
      document.getElementById("testi-name").textContent = t.name;
      document.getElementById("testi-tag").textContent = t.tag;
      document.getElementById("testi-avatar").src = t.avatar;
    }

    function renderFullGallery() {
      document.getElementById("full-gallery-grid").innerHTML = galleryPhotos.map((item, idx) => `
        <div onclick="openLightbox(${idx})" class="cursor-pointer group relative overflow-hidden rounded-3xl border-4 border-cream-50 shadow-card aspect-[4/3.4]">
          <img src="${item.src}" alt="${item.caption}" onerror="handleImgError(this, 'KAVÉLIA Gallery')" class="w-full h-full object-cover group-hover:scale-105 transition duration-500"/>
          <div class="absolute inset-0 bg-gradient-to-t from-cocoa-800/70 via-transparent to-transparent opacity-0 group-hover:opacity-100 transition flex items-end p-5">
            <span class="text-cream-50 text-sm font-serif-display tracking-wide">${item.caption}</span>
          </div>
        </div>
      `).join("");
    }

    function openLightbox(idx) {
      currentLightboxIdx = idx;
      document.getElementById("lightbox-img").src = galleryPhotos[idx].src;
      document.getElementById("lightbox-caption").textContent = galleryPhotos[idx].caption;
      document.getElementById("lightbox-modal").classList.remove("hidden");
    }

    function closeLightbox() {
      document.getElementById("lightbox-modal").classList.add("hidden");
    }

    function stepLightbox(dir) {
      currentLightboxIdx = (currentLightboxIdx + dir + galleryPhotos.length) % galleryPhotos.length;
      openLightbox(currentLightboxIdx);
    }

    function toggleSearchModal(open) {
      const modal = document.getElementById("search-modal");
      modal.classList.toggle("hidden", !open);
      if (open) {
        document.getElementById("search-input").value = "";
        handleSearch("");
        setTimeout(() => document.getElementById("search-input").focus(), 100);
      }
    }

    function handleSearch(query) {
      const q = query.toLowerCase().trim();
      const matched = products.filter(p =>
        p.name.toLowerCase().includes(q) ||
        p.category.toLowerCase().includes(q) ||
        p.tag.toLowerCase().includes(q)
      );
      document.getElementById("search-results").innerHTML = matched.length
        ? matched.map(p => `
            <div onclick="toggleSearchModal(false); openProductModal(${p.id});" class="py-3 flex items-center gap-3 cursor-pointer hover:bg-cream-100 px-2 rounded-xl transition">
              <img src="${p.image}" class="w-12 h-12 rounded-xl object-cover"/>
              <div class="flex-1">
                <div class="text-sm font-semibold text-cocoa-700">${p.name}</div>
                <div class="text-xs text-cocoa-400">${p.tag} • ${formatRp(p.price)}</div>
              </div>
              <span class="text-xs text-cocoa-500">Lihat →</span>
            </div>
          `).join("")
        : `<div class="py-6 text-center text-xs text-cocoa-400">Tidak ditemukan buket dengan kata kunci tersebut.</div>`;
    }

    // -------- 10. FORMS & MODALS --------
    function openCustomModal() {
      document.getElementById("custom-modal").classList.remove("hidden");
    }

    function handleCustomSubmit(e) {
      e.preventDefault();
      document.getElementById("custom-modal").classList.add("hidden");
      showToast("Permintaan Buket Custom terkirim! Florist kami akan menghubungi Anda.");
      e.target.reset();
    }

    function handleNewsletter(e, inputId) {
      e.preventDefault();
      document.getElementById(inputId).value = "";
      showToast("Terima kasih! Anda berhasil berlangganan newsletter KAVÉLIA Fleur ♡");
    }

    function handleContactSubmit(e) {
      e.preventDefault();
      e.target.reset();
      showToast("Pesan Anda telah terkirim! Tim kami akan segera membalas.");
    }

    // -------- 11. INIT --------
    document.addEventListener("DOMContentLoaded", () => {
      // Inject Botanical Line Art
      const tpl = document.getElementById("botanical-corner-svg").innerHTML;
      document.querySelectorAll(".botanical-slot").forEach(slot => slot.innerHTML = tpl);

      renderHomeProducts();
      updateCartUI();
      updateWishlistUI();

      // Sticky Header Effect
      window.addEventListener("scroll", () => {
        const header = document.getElementById("main-header");
        header.classList.toggle("nav-scrolled", window.scrollY > 30);
      });
    });
  </script>
</body>
</html>
```

e-over Drawer)** — Tambah/kurangi jumlah item, simpan ke favorit, hitung subtotal otomatis dalam Rupiah, hingga tombol langsung **Pesan via WhatsApp**.
7. **Request Buket Custom & Galeri Lightbox** — Formulir permintaan buket kustom serta pratinjau foto galeri layar penuh (*lightbox*).
