```html
<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nexus Infrastructure Group | Building Tomorrow's Foundation</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts: Inter -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <!-- FontAwesome for Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                    },
                    colors: {
                        brand: {
                            50: '#f0f7ff',
                            100: '#e0effe',
                            500: '#0284c7',
                            600: '#0369a1',
                            700: '#075985',
                            900: '#0c4a6e',
                            accent: '#38bdf8',
                        }
                    }
                }
            }
        }
    </script>
    <style>
        /* Custom dynamic background canvas styling */
        #hero-canvas {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            pointer-events: none;
        }
        
        /* Glassmorphism effects */
        .glass-panel {
            background: rgba(15, 23, 42, 0.75);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .glass-nav {
            background: rgba(15, 23, 42, 0.85);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.08);
        }

        /* Pulse glow animation */
        @keyframes pulse-glow {
            0%, 100% { opacity: 0.4; transform: scale(1); }
            50% { opacity: 0.8; transform: scale(1.05); }
        }
        .animate-glow {
            animation: pulse-glow 6s infinite ease-in-out;
        }
    </style>
</head>
<body class="bg-slate-950 text-slate-100 font-sans antialiased selection:bg-brand-500 selection:text-white">

    <!-- Header Navigation -->
    <header class="fixed top-0 left-0 right-0 z-50 glass-nav transition-all duration-300" id="navbar">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-20 flex items-center justify-between">
            <!-- Brand Logo -->
            <a href="#" class="flex items-center gap-3 group">
                <div class="w-10 h-10 rounded-xl bg-gradient-to-tr from-brand-600 to-cyan-400 flex items-center justify-center text-white shadow-lg shadow-brand-500/30 group-hover:scale-105 transition-transform">
                    <i class="fa-solid font-bold fa-cubes text-xl"></i>
                </div>
                <div>
                    <span class="text-xl font-extrabold tracking-tight text-white uppercase">Nexus</span>
                    <span class="text-xs block text-brand-accent tracking-widest font-semibold -mt-1">Infrastructure Group</span>
                </div>
            </a>

            <!-- Desktop Nav Links -->
            <nav class="hidden md:flex items-center gap-8 text-sm font-medium">
                <a href="#about" class="text-slate-300 hover:text-brand-accent transition-colors">About Us</a>
                <a href="#services" class="text-slate-300 hover:text-brand-accent transition-colors">Services</a>
                <a href="#projects" class="text-slate-300 hover:text-brand-accent transition-colors">Projects</a>
                <a href="#stats" class="text-slate-300 hover:text-brand-accent transition-colors">Impact</a>
                <a href="#contact" class="px-5 py-2.5 rounded-full bg-gradient-to-r from-brand-600 to-cyan-500 text-white font-semibold hover:from-brand-500 hover:to-cyan-400 transition-all shadow-md hover:shadow-brand-500/25">
                    Contact Us
                </a>
            </nav>

            <!-- Mobile Menu Button -->
            <button id="mobile-menu-btn" class="md:hidden p-2 rounded-lg text-slate-300 hover:text-white hover:bg-slate-800/60 focus:outline-none">
                <i class="fa-solid fa-bars text-2xl" id="menu-icon"></i>
            </button>
        </div>

        <!-- Mobile Menu Dropdown -->
        <div id="mobile-menu" class="hidden md:hidden glass-panel border-t border-slate-800 px-4 pt-4 pb-6 space-y-3">
            <a href="#about" class="block text-slate-300 hover:text-brand-accent py-2 px-3 rounded-lg hover:bg-slate-800/50">About Us</a>
            <a href="#services" class="block text-slate-300 hover:text-brand-accent py-2 px-3 rounded-lg hover:bg-slate-800/50">Services</a>
            <a href="#projects" class="block text-slate-300 hover:text-brand-accent py-2 px-3 rounded-lg hover:bg-slate-800/50">Projects</a>
            <a href="#stats" class="block text-slate-300 hover:text-brand-accent py-2 px-3 rounded-lg hover:bg-slate-800/50">Impact</a>
            <a href="#contact" class="block text-center mt-2 px-5 py-2.5 rounded-lg bg-brand-600 text-white font-semibold hover:bg-brand-500">Contact Us</a>
        </div>
    </header>

    <!-- Hero Section with Dynamic Animated Loop Background -->
    <section class="relative min-h-screen flex items-center justify-center pt-24 pb-16 overflow-hidden">
        <!-- Canvas particle/grid dynamic video loop background -->
        <canvas id="hero-canvas"></canvas>
        
        <!-- Subtle Glow Overlay -->
        <div class="absolute top-1/4 left-1/2 -translate-x-1/2 w-[600px] h-[600px] bg-brand-500/20 rounded-full blur-[120px] pointer-events-none animate-glow"></div>

        <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
            <!-- Badge -->
            <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full glass-panel border border-cyan-500/30 text-cyan-300 text-xs sm:text-sm font-semibold mb-8 animate-fade-in">
                <span class="flex h-2 w-2 relative">
                  <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-cyan-400 opacity-75"></span>
                  <span class="relative inline-flex rounded-full h-2 w-2 bg-cyan-500"></span>
                </span>
                Next-Generation Critical Infrastructure Solutions
            </div>

            <!-- Main Heading -->
            <h1 class="text-4xl sm:text-6xl md:text-7xl font-extrabold tracking-tight text-white mb-6 leading-tight">
                Architecting the <br class="hidden sm:inline" />
                <span class="bg-clip-text text-transparent bg-gradient-to-r from-brand-accent via-cyan-300 to-sky-500">
                    Connected Tomorrow
                </span>
            </h1>

            <!-- Subtitle -->
            <p class="max-w-3xl mx-auto text-lg sm:text-xl text-slate-300 mb-10 leading-relaxed font-normal">
                Nexus Infrastructure Group delivers resilient energy networks, sustainable smart transport, and digital telecommunications assets powering global growth.
            </p>

            <!-- CTA Buttons -->
            <div class="flex flex-col sm:flex-row items-center justify-center gap-4">
                <a href="#services" class="w-full sm:w-auto px-8 py-4 rounded-xl bg-gradient-to-r from-brand-600 to-cyan-500 text-white font-bold hover:from-brand-500 hover:to-cyan-400 transition-all shadow-lg shadow-brand-600/30 flex items-center justify-center gap-2">
                    <span>Explore Solutions</span>
                    <i class="fa-solid fa-arrow-right text-sm"></i>
                </a>
                <a href="#contact" class="w-full sm:w-auto px-8 py-4 rounded-xl glass-panel text-white font-semibold hover:bg-slate-800/80 hover:border-slate-600 transition-all flex items-center justify-center gap-2">
                    <i class="fa-solid fa-paper-plane text-sm text-brand-accent"></i>
                    <span>Get in Touch</span>
                </a>
            </div>
        </div>

        <!-- Scroll Indicator -->
        <a href="#about" class="absolute bottom-8 left-1/2 -translate-x-1/2 text-slate-400 hover:text-white transition-colors animate-bounce">
            <i class="fa-solid fa-chevron-down text-xl"></i>
        </a>
    </section>

    <!-- Company Overview / About Section -->
    <section id="about" class="py-24 bg-slate-900/60 relative border-t border-slate-800/80">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 lg:gap-16 items-center">
                
                <!-- Left Visual Graphic / Simulated Loop Window -->
                <div class="relative rounded-2xl overflow-hidden glass-panel p-2 border border-slate-700/50 shadow-2xl">
                    <div class="relative h-80 sm:h-96 w-full rounded-xl overflow-hidden bg-slate-950 flex items-center justify-center">
                        <!-- Decorative Abstract Nodes -->
                        <div class="absolute inset-0 bg-gradient-to-tr from-brand-900/40 via-slate-950 to-cyan-900/30"></div>
                        <div class="absolute inset-0 flex items-center justify-center">
                            <div class="w-64 h-64 border border-brand-500/30 rounded-full animate-spin [animation-duration:20s]"></div>
                            <div class="absolute w-48 h-48 border border-cyan-400/20 rounded-full animate-spin [animation-duration:12s] [animation-direction:reverse]"></div>
                        </div>
                        <div class="relative z-10 text-center p-6">
                            <i class="fa-solid fa-network-wired text-5xl text-brand-accent mb-4"></i>
                            <h3 class="text-xl font-bold text-white mb-2">Integrated Global Systems</h3>
                            <p class="text-slate-400 text-sm max-w-xs mx-auto">Connecting energy, civil engineering, and digital framework into unified infrastructure.</p>
                        </div>
                    </div>
                </div>

                <!-- Right Text Content -->
                <div class="space-y-6">
                    <div class="inline-flex items-center gap-2 text-brand-accent text-sm font-bold tracking-wider uppercase">
                        <i class="fa-solid fa-building text-xs"></i> About Nexus Infrastructure
                    </div>
                    <h2 class="text-3xl sm:text-4xl font-extrabold text-white tracking-tight">
                        Pioneering Civil & Digital Transformation
                    </h2>
                    <p class="text-slate-300 leading-relaxed">
                        Nexus Infrastructure Group stands at the forefront of global development. We specialize in engineering, constructing, and maintaining high-performance assets that drive urban sustainability and industrial modernization.
                    </p>
                    <p class="text-slate-400 leading-relaxed">
                        Through dynamic innovation and strict regulatory compliance, we bridge the gap between traditional engineering and tomorrow's smart infrastructure requirements.
                    </p>

                    <!-- Key Pillars List -->
                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 pt-4">
                        <div class="flex items-start gap-3">
                            <div class="w-8 h-8 rounded-lg bg-brand-500/20 text-brand-accent flex items-center justify-center shrink-0 mt-1">
                                <i class="fa-solid fa-shield-halved"></i>
                            </div>
                            <div>
                                <h4 class="text-white font-semibold text-sm">Resilient Quality</h4>
                                <p class="text-slate-400 text-xs mt-1">Built to withstand environmental challenges.</p>
                            </div>
                        </div>
                        <div class="flex items-start gap-3">
                            <div class="w-8 h-8 rounded-lg bg-cyan-500/20 text-cyan-400 flex items-center justify-center shrink-0 mt-1">
                                <i class="fa-solid fa-leaf"></i>
                            </div>
                            <div>
                                <h4 class="text-white font-semibold text-sm">Sustainable Focus</h4>
                                <p class="text-slate-400 text-xs mt-1">Net-zero carbon emission commitment.</p>
                            </div>
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- Services Showcase -->
    <section id="services" class="py-24 relative">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <span class="text-brand-accent text-sm font-bold tracking-wider uppercase">Core Capabilities</span>
                <h2 class="text-3xl sm:text-4xl font-extrabold text-white mt-2">Comprehensive Solutions</h2>
                <p class="text-slate-400 mt-4">Delivering end-to-end infrastructure lifecycle management across multiple vital industries.</p>
            </div>

            <!-- Grid of Cards -->
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                
                <!-- Service 1 -->
                <div class="glass-panel rounded-2xl p-8 hover:border-brand-500/50 transition-all duration-300 hover:-translate-y-1 group">
                    <div class="w-14 h-14 rounded-xl bg-gradient-to-tr from-brand-600 to-cyan-500 flex items-center justify-center text-white text-2xl mb-6 shadow-lg shadow-brand-500/20 group-hover:scale-110 transition-transform">
                        <i class="fa-solid fa-bolt"></i>
                    </div>
                    <h3 class="text-xl font-bold text-white mb-3">Energy & Power Grids</h3>
                    <p class="text-slate-400 text-sm leading-relaxed mb-6">
                        Developing modern power distribution systems, smart grids, and renewable integration for long-term grid sustainability.
                    </p>
                    <a href="#contact" class="inline-flex items-center text-sm font-semibold text-brand-accent hover:text-white transition-colors gap-2">
                        <span>Learn More</span> <i class="fa-solid fa-chevron-right text-xs"></i>
                    </a>
                </div>

                <!-- Service 2 -->
                <div class="glass-panel rounded-2xl p-8 hover:border-brand-500/50 transition-all duration-300 hover:-translate-y-1 group">
                    <div class="w-14 h-14 rounded-xl bg-gradient-to-tr from-cyan-600 to-teal-400 flex items-center justify-center text-white text-2xl mb-6 shadow-lg shadow-cyan-500/20 group-hover:scale-110 transition-transform">
                        <i class="fa-solid fa-tower-cell"></i>
                    </div>
                    <h3 class="text-xl font-bold text-white mb-3">Telecommunications</h3>
                    <p class="text-slate-400 text-sm leading-relaxed mb-6">
                        Deploying fiber-optic backbones, 5G cellular infrastructure, and high-density data network installations worldwide.
                    </p>
                    <a href="#contact" class="inline-flex items-center text-sm font-semibold text-brand-accent hover:text-white transition-colors gap-2">
                        <span>Learn More</span> <i class="fa-solid fa-chevron-right text-xs"></i>
                    </a>
                </div>

                <!-- Service 3 -->
                <div class="glass-panel rounded-2xl p-8 hover:border-brand-500/50 transition-all duration-300 hover:-translate-y-1 group">
                    <div class="w-14 h-14 rounded-xl bg-gradient-to-tr from-sky-600 to-indigo-500 flex items-center justify-center text-white text-2xl mb-6 shadow-lg shadow-sky-500/20 group-hover:scale-110 transition-transform">
                        <i class="fa-solid fa-road"></i>
                    </div>
                    <h3 class="text-xl font-bold text-white mb-3">Smart Transportation</h3>
                    <p class="text-slate-400 text-sm leading-relaxed mb-6">
                        Designing intelligent transit networks, highway monitoring systems, and electrified logistics hubs.
                    </p>
                    <a href="#contact" class="inline-flex items-center text-sm font-semibold text-brand-accent hover:text-white transition-colors gap-2">
                        <span>Learn More</span> <i class="fa-solid fa-chevron-right text-xs"></i>
                    </a>
                </div>

                <!-- Service 4 -->
                <div class="glass-panel rounded-2xl p-8 hover:border-brand-500/50 transition-all duration-300 hover:-translate-y-1 group">
                    <div class="w-14 h-14 rounded-xl bg-gradient-to-tr from-blue-600 to-cyan-400 flex items-center justify-center text-white text-2xl mb-6 shadow-lg shadow-blue-500/20 group-hover:scale-110 transition-transform">
                        <i class="fa-solid fa-droplet"></i>
                    </div>
                    <h3 class="text-xl font-bold text-white mb-3">Water & Utilities</h3>
                    <p class="text-slate-400 text-sm leading-relaxed mb-6">
                        Engineered water management systems, smart metering solutions, and environmental protection networks.
                    </p>
                    <a href="#contact" class="inline-flex items-center text-sm font-semibold text-brand-accent hover:text-white transition-colors gap-2">
                        <span>Learn More</span> <i class="fa-solid fa-chevron-right text-xs"></i>
                    </a>
                </div>

                <!-- Service 5 -->
                <div class="glass-panel rounded-2xl p-8 hover:border-brand-500/50 transition-all duration-300 hover:-translate-y-1 group">
                    <div class="w-14 h-14 rounded-xl bg-gradient-to-tr from-purple-600 to-brand-500 flex items-center justify-center text-white text-2xl mb-6 shadow-lg shadow-purple-500/20 group-hover:scale-110 transition-transform">
                        <i class="fa-solid fa-microchip"></i>
                    </div>
                    <h3 class="text-xl font-bold text-white mb-3">IoT & Asset Monitoring</h3>
                    <p class="text-slate-400 text-sm leading-relaxed mb-6">
                        Real-time telemetry, predictive structural monitoring, and centralized infrastructure asset analytics.
                    </p>
                    <a href="#contact" class="inline-flex items-center text-sm font-semibold text-brand-accent hover:text-white transition-colors gap-2">
                        <span>Learn More</span> <i class="fa-solid fa-chevron-right text-xs"></i>
                    </a>
                </div>

                <!-- Service 6 -->
                <div class="glass-panel rounded-2xl p-8 hover:border-brand-500/50 transition-all duration-300 hover:-translate-y-1 group">
                    <div class="w-14 h-14 rounded-xl bg-gradient-to-tr from-emerald-600 to-teal-400 flex items-center justify-center text-white text-2xl mb-6 shadow-lg shadow-emerald-500/20 group-hover:scale-110 transition-transform">
                        <i class="fa-solid fa-helmet-safety"></i>
                    </div>
                    <h3 class="text-xl font-bold text-white mb-3">EPC Contracting</h3>
                    <p class="text-slate-400 text-sm leading-relaxed mb-6">
                        Turnkey Engineering, Procurement, and Construction management guaranteeing safety, quality, and speed.
                    </p>
                    <a href="#contact" class="inline-flex items-center text-sm font-semibold text-brand-accent hover:text-white transition-colors gap-2">
                        <span>Learn More</span> <i class="fa-solid fa-chevron-right text-xs"></i>
                    </a>
                </div>

            </div>
        </div>
    </section>

    <!-- Stats Counter Section -->
    <section id="stats" class="py-20 bg-slate-900/80 border-y border-slate-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-2 lg:grid-cols-4 gap-8 text-center">
                <div class="p-6">
                    <div class="text-4xl sm:text-5xl font-extrabold text-transparent bg-clip-text bg-gradient-to-r from-brand-accent to-cyan-300">
                        $<span class="counter" data-target="4.2">0</span>B+
                    </div>
                    <p class="text-slate-400 text-sm mt-2 font-medium">Assets Under Management</p>
                </div>
                <div class="p-6">
                    <div class="text-4xl sm:text-5xl font-extrabold text-transparent bg-clip-text bg-gradient-to-r from-brand-accent to-cyan-300">
                        <span class="counter" data-target="1500">0</span>+
                    </div>
                    <p class="text-slate-400 text-sm mt-2 font-medium">Projects Completed</p>
                </div>
                <div class="p-6">
                    <div class="text-4xl sm:text-5xl font-extrabold text-transparent bg-clip-text bg-gradient-to-r from-brand-accent to-cyan-300">
                        <span class="counter" data-target="35">0</span>
                    </div>
                    <p class="text-slate-400 text-sm mt-2 font-medium">Global Markets</p>
                </div>
                <div class="p-6">
                    <div class="text-4xl sm:text-5xl font-extrabold text-transparent bg-clip-text bg-gradient-to-r from-brand-accent to-cyan-300">
                        <span class="counter" data-target="99.9">0</span>%
                    </div>
                    <p class="text-slate-400 text-sm mt-2 font-medium">Operational Reliability</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Form Section -->
    <section id="contact" class="py-24 relative">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-12">
                
                <!-- Contact Info Sidebar -->
                <div class="lg:col-span-5 space-y-8">
                    <div>
                        <span class="text-brand-accent text-sm font-bold tracking-wider uppercase">Get In Touch</span>
                        <h2 class="text-3xl sm:text-4xl font-extrabold text-white mt-2">Connect With Nexus</h2>
                        <p class="text-slate-400 mt-4 leading-relaxed">
                            Have an upcoming project or inquiry? Our engineering and business development team is ready to assist you.
                        </p>
                    </div>

                    <div class="space-y-6">
                        <div class="flex items-start gap-4">
                            <div class="w-12 h-12 rounded-xl bg-slate-800 border border-slate-700 flex items-center justify-center text-brand-accent text-lg shrink-0">
                                <i class="fa-solid fa-location-dot"></i>
                            </div>
                            <div>
                                <h4 class="text-white font-semibold">Corporate Headquarters</h4>
                                <p class="text-slate-400 text-sm mt-1">100 Nexus Tower, Financial District, NY 10005, USA</p>
                            </div>
                        </div>

                        <div class="flex items-start gap-4">
                            <div class="w-12 h-12 rounded-xl bg-slate-800 border border-slate-700 flex items-center justify-center text-brand-accent text-lg shrink-0">
                                <i class="fa-solid fa-envelope"></i>
                            </div>
                            <div>
                                <h4 class="text-white font-semibold">Email Inquiries</h4>
                                <p class="text-slate-400 text-sm mt-1">info@nexusinfrastructure.com</p>
                            </div>
                        </div>

                        <div class="flex items-start gap-4">
                            <div class="w-12 h-12 rounded-xl bg-slate-800 border border-slate-700 flex items-center justify-center text-brand-accent text-lg shrink-0">
                                <i class="fa-solid fa-phone"></i>
                            </div>
                            <div>
                                <h4 class="text-white font-semibold">Telephone</h4>
                                <p class="text-slate-400 text-sm mt-1">+1 (800) 555-NEXUS / +1 (800) 555-6398</p>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Contact Form Card -->
                <div class="lg:col-span-7">
                    <div class="glass-panel rounded-2xl p-8 sm:p-10 relative">
                        
                        <!-- Form Success Message Toast -->
                        <div id="form-success" class="hidden mb-6 p-4 rounded-xl bg-emerald-500/20 border border-emerald-500/50 text-emerald-300 text-sm flex items-center gap-3">
                            <i class="fa-solid fa-circle-check text-xl shrink-0"></i>
                            <div>
                                <p class="font-bold">Message sent successfully!</p>
                                <p class="text-xs text-emerald-400">Thank you for reaching out. A representative will contact you shortly.</p>
                            </div>
                        </div>

                        <form id="contactForm" novalidate class="space-y-6">
                            <div class="grid grid-cols-1 sm:grid-cols-2 gap-6">
                                <!-- First Name -->
                                <div>
                                    <label for="firstName" class="block text-xs font-semibold text-slate-300 uppercase tracking-wider mb-2">First Name *</label>
                                    <input type="text" id="firstName" name="firstName" required
                                        class="w-full px-4 py-3 rounded-xl bg-slate-900/90 border border-slate-700 text-white placeholder-slate-500 focus:outline-none focus:border-brand-accent focus:ring-1 focus:ring-brand-accent transition-all text-sm"
                                        placeholder="John">
                                    <span class="error-msg text-rose-400 text-xs hidden mt-1">Please enter your first name.</span>
                                </div>

                                <!-- Last Name -->
                                <div>
                                    <label for="lastName" class="block text-xs font-semibold text-slate-300 uppercase tracking-wider mb-2">Last Name *</label>
                                    <input type="text" id="lastName" name="lastName" required
                                        class="w-full px-4 py-3 rounded-xl bg-slate-900/90 border border-slate-700 text-white placeholder-slate-500 focus:outline-none focus:border-brand-accent focus:ring-1 focus:ring-brand-accent transition-all text-sm"
                                        placeholder="Doe">
                                    <span class="error-msg text-rose-400 text-xs hidden mt-1">Please enter your last name.</span>
                                </div>
                            </div>

                            <div class="grid grid-cols-1 sm:grid-cols-2 gap-6">
                                <!-- Email -->
                                <div>
                                    <label for="email" class="block text-xs font-semibold text-slate-300 uppercase tracking-wider mb-2">Work Email *</label>
                                    <input type="email" id="email" name="email" required
                                        class="w-full px-4 py-3 rounded-xl bg-slate-900/90 border border-slate-700 text-white placeholder-slate-500 focus:outline-none focus:border-brand-accent focus:ring-1 focus:ring-brand-accent transition-all text-sm"
                                        placeholder="j.doe@company.com">
                                    <span class="error-msg text-rose-400 text-xs hidden mt-1">Please enter a valid email address.</span>
                                </div>

                                <!-- Phone -->
                                <div>
                                    <label for="phone" class="block text-xs font-semibold text-slate-300 uppercase tracking-wider mb-2">Phone Number</label>
                                    <input type="tel" id="phone" name="phone"
                                        class="w-full px-4 py-3 rounded-xl bg-slate-900/90 border border-slate-700 text-white placeholder-slate-500 focus:outline-none focus:border-brand-accent focus:ring-1 focus:ring-brand-accent transition-all text-sm"
                                        placeholder="+1 (555) 000-0000">
                                </div>
                            </div>

                            <!-- Subject / Sector -->
                            <div>
                                <label for="sector" class="block text-xs font-semibold text-slate-300 uppercase tracking-wider mb-2">Sector of Interest *</label>
                                <select id="sector" name="sector" required
                                    class="w-full px-4 py-3 rounded-xl bg-slate-900/90 border border-slate-700 text-white focus:outline-none focus:border-brand-accent focus:ring-1 focus:ring-brand-accent transition-all text-sm">
                                    <option value="">Select an Sector...</option>
                                    <option value="energy">Energy & Power Grids</option>
                                    <option value="telecom">Telecommunications</option>
                                    <option value="transport">Smart Transportation</option>
                                    <option value="water">Water & Utilities</option>
                                    <option value="other">General Inquiry</option>
                                </select>
                                <span class="error-msg text-rose-400 text-xs hidden mt-1">Please select a sector.</span>
                            </div>

                            <!-- Message -->
                            <div>
                                <label for="message" class="block text-xs font-semibold text-slate-300 uppercase tracking-wider mb-2">Message *</label>
                                <textarea id="message" name="message" rows="4" required
                                    class="w-full px-4 py-3 rounded-xl bg-slate-900/90 border border-slate-700 text-white placeholder-slate-500 focus:outline-none focus:border-brand-accent focus:ring-1 focus:ring-brand-accent transition-all text-sm resize-none"
                                    placeholder="Tell us about your project requirements or question..."></textarea>
                                <span class="error-msg text-rose-400 text-xs hidden mt-1">Message must be at least 10 characters.</span>
                            </div>

                            <!-- Submit Button -->
                            <button type="submit" 
                                class="w-full py-4 rounded-xl bg-gradient-to-r from-brand-600 to-cyan-500 text-white font-bold hover:from-brand-500 hover:to-cyan-400 transition-all shadow-lg shadow-brand-500/25 flex items-center justify-center gap-2 text-base">
                                <i class="fa-solid fa-paper-plane text-sm"></i>
                                <span>Submit Inquiry</span>
                            </button>
                        </form>

                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-slate-950 border-t border-slate-800/80 py-12 text-slate-400 text-sm">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col md:flex-row items-center justify-between gap-6">
            <div class="flex items-center gap-3">
                <div class="w-8 h-8 rounded-lg bg-brand-600 flex items-center justify-center text-white font-bold">
                    <i class="fa-solid fa-cubes"></i>
                </div>
                <span class="text-white font-bold">Nexus Infrastructure Group</span>
            </div>
            
            <div class="flex flex-wrap justify-center gap-6 text-xs text-slate-400">
                <a href="#" class="hover:text-white transition-colors">Privacy Policy</a>
                <a href="#" class="hover:text-white transition-colors">Terms of Service</a>
                <a href="#" class="hover:text-white transition-colors">Compliance</a>
                <a href="#" class="hover:text-white transition-colors">Careers</a>
            </div>

            <div class="text-xs text-slate-500">
                &copy; <span id="current-year"></span> Nexus Infrastructure Group. All rights reserved.
            </div>
        </div>
    </footer>

    <!-- Interactive Scripts -->
    <script>
        // Set current year in footer
        document.getElementById('current-year').textContent = new Date().getFullYear();

        // Mobile Menu Toggle
        const mobileMenuBtn = document.getElementById('mobile-menu-btn');
        const mobileMenu = document.getElementById('mobile-menu');
        const menuIcon = document.getElementById('menu-icon');

        mobileMenuBtn.addEventListener('click', () => {
            mobileMenu.classList.toggle('hidden');
            if (mobileMenu.classList.contains('hidden')) {
                menuIcon.classList.remove('fa-xmark');
                menuIcon.classList.add('fa-bars');
            } else {
                menuIcon.classList.remove('fa-bars');
                menuIcon.classList.add('fa-xmark');
            }
        });

        // Dynamic Dynamic Canvas Particles (Simulating infrastructure network data flow)
        const canvas = document.getElementById('hero-canvas');
        const ctx = canvas.getContext('2d');

        let particles = [];
        const particleCount = 45;

        function resizeCanvas() {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        }

        window.addEventListener('resize', resizeCanvas);
        resizeCanvas();

        class Particle {
            constructor() {
                this.reset();
            }

            reset() {
                this.x = Math.random() * canvas.width;
                this.y = Math.random() * canvas.height;
                this.vx = (Math.random() - 0.5) * 0.8;
                this.vy = (Math.random() - 0.5) * 0.8;
                this.radius = Math.random() * 2 + 1;
                this.alpha = Math.random() * 0.5 + 0.2;
            }

            update() {
                this.x += this.vx;
                this.y += this.vy;

                if (this.x < 0 || this.x > canvas.width) this.vx *= -1;
                if (this.y < 0 || this.y > canvas.height) this.vy *= -1;
            }

            draw() {
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.radius, 0, Math.PI * 2);
                ctx.fillStyle = `rgba(56, 189, 248, ${this.alpha})`;
                ctx.fill();
            }
        }

        for (let i = 0; i < particleCount; i++) {
            particles.push(new Particle());
        }

        function drawConnections() {
            for (let i = 0; i < particles.length; i++) {
                for (let j = i + 1; j < particles.length; j++) {
                    const dx = particles[i].x - particles[j].x;
                    const dy = particles[i].y - particles[j].y;
                    const dist = Math.sqrt(dx * dx + dy * dy);

                    if (dist < 150) {
                        ctx.beginPath();
                        ctx.moveTo(particles[i].x, particles[i].y);
                        ctx.lineTo(particles[j].x, particles[j].y);
                        ctx.strokeStyle = `rgba(2, 132, 199, ${0.15 * (1 - dist / 150)})`;
                        ctx.lineWidth = 1;
                        ctx.stroke();
                    }
                }
            }
        }

        function animateLoop() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            particles.forEach(p => {
                p.update();
                p.draw();
            });
            drawConnections();
            requestAnimationFrame(animateLoop);
        }

        window.onload = function() {
            animateLoop();
        };

        // Client-side Contact Form Validation Script
        const contactForm = document.getElementById('contactForm');
        const successMessage = document.getElementById('form-success');

        contactForm.addEventListener('submit', function(e) {
            e.preventDefault();
            let isValid = true;

            // Clear previous errors
            const inputs = contactForm.querySelectorAll('input, select, textarea');
            inputs.forEach(input => {
                const errorSpan = input.parentNode.querySelector('.error-msg');
                if (errorSpan) errorSpan.classList.add('hidden');
                input.classList.remove('border-rose-500');
            });

            // Validate First Name
            const firstName = document.getElementById('firstName');
            if (!firstName.value.trim()) {
                showError(firstName, 'Please enter your first name.');
                isValid = false;
            }

            // Validate Last Name
            const lastName = document.getElementById('lastName');
            if (!lastName.value.trim()) {
                showError(lastName, 'Please enter your last name.');
                isValid = false;
            }

            // Validate Email
            const email = document.getElementById('email');
            const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            if (!email.value.trim() || !emailRegex.test(email.value.trim())) {
                showError(email, 'Please enter a valid email address.');
                isValid = false;
            }

            // Validate Sector
            const sector = document.getElementById('sector');
            if (!sector.value) {
                showError(sector, 'Please select a sector.');
                isValid = false;
            }

            // Validate Message
            const message = document.getElementById('message');
            if (!message.value.trim() || message.value.trim().length < 10) {
                showError(message, 'Message must be at least 10 characters long.');
                isValid = false;
            }

            // Successful Submission Handling
            if (isValid) {
                successMessage.classList.remove('hidden');
                contactForm.reset();
                setTimeout(() => {
                    successMessage.classList.add('hidden');
                }, 6000);
            }
        });

        function showError(element, msg) {
            element.classList.add('border-rose-500');
            const errorSpan = element.parentNode.querySelector('.error-msg');
            if (errorSpan) {
                errorSpan.textContent = msg;
                errorSpan.classList.remove('hidden');
            }
        }
    </script>
</body>
</html>
```