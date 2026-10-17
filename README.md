html
<!DOCTYPE html>
<html lang="en" class="h-full bg-slate-950 text-slate-100">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nexus Infrastructure Group LLC — Portal</title>
    
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        obsidian: '#0b0f19',
                        navydark: '#111827',
                        cyanglow: '#0ea5e9',
                        emeraldglow: '#10b981',
                        amberglow: '#f59e0b',
                        roseglow: '#ef4444'
                    },
                    fontFamily: {
                        sans: ['Inter', 'system-ui', 'sans-serif'],
                        mono: ['JetBrains Mono', 'Fira Code', 'monospace']
                    }
                }
            }
        }
    </script>
    <style>
        /* Custom Glowing Visual Effects */
        .glow-box-cyan {
            box-shadow: 0 0 15px rgba(14, 165, 233, 0.2);
        }
        .glow-box-emerald {
            box-shadow: 0 0 15px rgba(16, 185, 129, 0.25);
        }
        .scanline {
            background: linear-gradient(to bottom, rgba(255,255,255,0), rgba(255,255,255,0.03) 50%, rgba(0,0,0,0.3) 51%, rgba(0,0,0,0));
            background-size: 100% 4px;
        }
        /* Custom Lock Dial Animation */
        @keyframes pulseGlow {
            0%, 100% { opacity: 0.6; transform: scale(1); }
            50% { opacity: 1; transform: scale(1.03); }
        }
        .pulse-active {
            animation: pulseGlow 2s infinite ease-in-out;
        }
    </style>
</head>
<body class="min-h-screen font-sans bg-slate-950 text-slate-100 flex flex-col justify-between scanline selection:bg-cyanglow/30 selection:text-cyan-200">

    <!-- HEADER / TOP BRAND BANNER -->
    <header class="bg-slate-900/90 border-b border-slate-800 backdrop-blur sticky top-0 z-50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-3 flex flex-col md:flex-row items-center justify-between gap-4">
            
            <!-- Company Logo & Name -->
            <div class="flex items-center space-x-3">
                <div class="w-10 h-10 rounded-lg bg-gradient-to-tr from-cyan-600 to-blue-500 flex items-center justify-center font-bold text-slate-950 text-xl shadow-lg shadow-cyan-500/20">
                    <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 11H5m14 0a2 2 0 012 2v6a2 2 0 01-2 2H5a2 2 0 01-2-2v-6a2 2 0 012-2m14 0V9a2 2 0 00-2-2M5 11V9a2 2 0 012-2m0 0V5a2 2 0 012-2h6a2 2 0 012 2v2M7 7h10"></path>
                    </svg>
                </div>
                <div>
                    <h1 class="text-lg font-bold tracking-tight text-slate-100">Nexus Infrastructure Group LLC</h1>
                    <p class="text-xs text-slate-400">Enterprise Systems & Secure Operations</p>
                </div>
            </div>

            <!-- Generic Contact Info Banner -->
            <div class="flex flex-wrap items-center justify-center gap-4 text-xs text-slate-300">
                <a href="mailto:support@nexusinfra.com" class="flex items-center space-x-1.5 hover:text-cyan-400 transition-colors bg-slate-800/60 px-3 py-1.5 rounded-md border border-slate-700/50">
                    <svg class="w-4 h-4 text-cyan-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"></path>
                    </svg>
                    <span>support@nexusinfra.com</span>
                </a>
                <a href="tel:+18005550199" class="flex items-center space-x-1.5 hover:text-cyan-400 transition-colors bg-slate-800/60 px-3 py-1.5 rounded-md border border-slate-700/50">
                    <svg class="w-4 h-4 text-cyan-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"></path>
                    </svg>
                    <span>+1 (800) 555-0199</span>
                </a>
                <div class="hidden lg:flex items-center space-x-1.5 bg-slate-800/60 px-3 py-1.5 rounded-md border border-slate-700/50 text-slate-400">
                    <svg class="w-4 h-4 text-cyan-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"></path>
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"></path>
                    </svg>
                    <span>Corporate HQ • Suite 400, Chicago IL</span>
                </div>
            </div>

        </div>
    </header>

    <!-- MAIN BODY WRAPPER -->
    <main class="flex-grow max-w-5xl w-full mx-auto px-4 py-8 flex flex-col gap-8">

        <!-- SPLASH / HERO INTRO SECTION -->
        <section class="bg-slate-900/50 rounded-2xl p-6 md:p-10 border border-slate-800 shadow-xl relative overflow-hidden">
            <div class="absolute -right-16 -bottom-16 w-64 h-64 bg-cyan-500/10 rounded-full blur-3xl pointer-events-none"></div>
            
            <div class="max-w-3xl space-y-4">
                <span class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full text-xs font-semibold bg-cyan-950 text-cyan-400 border border-cyan-800/50">
                    <span class="w-2 h-2 rounded-full bg-cyan-400 animate-ping"></span>
                    Portal Entrance Active
                </span>
                <h2 class="text-3xl md:text-4xl font-extrabold tracking-tight text-white">
                    Nexus Infrastructure Operations Hub
                </h2>
                <p class="text-slate-300 text-base leading-relaxed">
                    Welcome to the central gateway for Nexus Infrastructure Group LLC. This landing page provides client directory access, system status metrics, and internal operational resource control.
                </p>
            </div>
        </section>

        <!-- VISUAL ACCESS CONTROL GATE / LOCK MECHANISM -->
        <section id="lockSection" class="bg-slate-900/90 rounded-2xl border border-slate-800 p-6 md:p-8 shadow-2xl relative transition-all duration-500">
            
            <div class="text-center max-w-xl mx-auto space-y-3">
                <!-- Visual Status Icon -->
                <div id="lockIconContainer" class="w-16 h-16 mx-auto rounded-full bg-cyan-950/80 border border-cyan-500/30 flex items-center justify-center glow-box-cyan transition-all duration-300">
                    <svg id="lockIcon" class="w-8 h-8 text-cyan-400 transition-all duration-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 15v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v6a2 2 0 002 2zm10-10V7a4 4 0 00-8 0v4h8z"></path>
                    </svg>
                </div>
                
                <h3 id="lockTitle" class="text-xl font-bold text-white">Security Gateway Verification</h3>
                <p id="lockSubtitle" class="text-sm text-slate-400">
                    Perform visual verification below by selecting the required security pattern sequence to unseal the protected infrastructure assets.
                </p>
            </div>

            <!-- Visual Key Lock Panel -->
            <div id="lockMechanism" class="mt-8 bg-slate-950/80 p-6 rounded-xl border border-slate-800 max-w-md mx-auto space-y-6">
                
                <!-- Target Visual Pattern Prompt -->
                <div class="text-center space-y-2">
                    <span class="text-xs uppercase tracking-wider font-mono text-slate-400">Verification Pattern Code:</span>
                    <div id="codeDisplay" class="flex justify-center items-center gap-3 font-mono text-xl font-bold">
                        <span class="px-3 py-1 rounded bg-slate-900 border border-cyan-500/30 text-cyan-400 shadow-inner">3</span>
                        <span class="px-3 py-1 rounded bg-slate-900 border border-cyan-500/30 text-cyan-400 shadow-inner">8</span>
                        <span class="px-3 py-1 rounded bg-slate-900 border border-cyan-500/30 text-cyan-400 shadow-inner">1</span>
                    </div>
                </div>

                <!-- Interactive Keypad -->
                <div class="grid grid-cols-3 gap-3">
                    <button onclick="pressKey('1')" class="py-3 rounded-lg bg-slate-900 border border-slate-800 text-slate-200 hover:border-cyan-500/50 hover:bg-slate-800 active:scale-95 transition text-lg font-mono font-semibold">1</button>
                    <button onclick="pressKey('2')" class="py-3 rounded-lg bg-slate-900 border border-slate-800 text-slate-200 hover:border-cyan-500/50 hover:bg-slate-800 active:scale-95 transition text-lg font-mono font-semibold">2</button>
                    <button onclick="pressKey('3')" class="py-3 rounded-lg bg-slate-900 border border-slate-800 text-slate-200 hover:border-cyan-500/50 hover:bg-slate-800 active:scale-95 transition text-lg font-mono font-semibold">3</button>
                    <button onclick="pressKey('4')" class="py-3 rounded-lg bg-slate-900 border border-slate-800 text-slate-200 hover:border-cyan-500/50 hover:bg-slate-800 active:scale-95 transition text-lg font-mono font-semibold">4</button>
                    <button onclick="pressKey('5')" class="py-3 rounded-lg bg-slate-900 border border-slate-800 text-slate-200 hover:border-cyan-500/50 hover:bg-slate-800 active:scale-95 transition text-lg font-mono font-semibold">5</button>
                    <button onclick="pressKey('6')" class="py-3 rounded-lg bg-slate-900 border border-slate-800 text-slate-200 hover:border-cyan-500/50 hover:bg-slate-800 active:scale-95 transition text-lg font-mono font-semibold">6</button>
                    <button onclick="pressKey('7')" class="py-3 rounded-lg bg-slate-900 border border-slate-800 text-slate-200 hover:border-cyan-500/50 hover:bg-slate-800 active:scale-95 transition text-lg font-mono font-semibold">7</button>
                    <button onclick="pressKey('8')" class="py-3 rounded-lg bg-slate-900 border border-slate-800 text-slate-200 hover:border-cyan-500/50 hover:bg-slate-800 active:scale-95 transition text-lg font-mono font-semibold">8</button>
                    <button onclick="pressKey('9')" class="py-3 rounded-lg bg-slate-900 border border-slate-800 text-slate-200 hover:border-cyan-500/50 hover:bg-slate-800 active:scale-95 transition text-lg font-mono font-semibold">9</button>
                </div>

                <!-- Input Feedback Line -->
                <div class="flex items-center justify-between border-t border-slate-800 pt-4">
                    <div class="flex items-center gap-2">
                        <span class="text-xs text-slate-400 font-mono">Entered:</span>
                        <span id="inputDisplay" class="font-mono text-cyan-400 tracking-widest font-bold min-h-[24px]">___</span>
                    </div>
                    <button onclick="resetKeypad()" class="text-xs text-slate-400 hover:text-slate-200 underline transition">Reset</button>
                </div>

                <!-- Status Message Output -->
                <div id="statusMessage" class="hidden text-center text-xs font-mono py-2 rounded-md"></div>
            </div>

            <!-- Unlock Confirmation Action Button -->
            <div class="mt-6 text-center">
                <button id="verifyBtn" onclick="verifyLock()" class="px-8 py-3 rounded-xl bg-cyan-600 hover:bg-cyan-500 text-slate-950 font-bold tracking-wide transition shadow-lg shadow-cyan-600/30 active:scale-95">
                    Verify & Unlock Content
                </button>
            </div>
        </section>

        <!-- PROTECTED INTERNAL CONTENT SECTION (Initially Hidden) -->
        <section id="protectedContent" class="hidden space-y-6 transition-all duration-700 opacity-0 transform translate-y-4">
            
            <div class="flex items-center justify-between bg-emerald-950/40 border border-emerald-500/30 p-4 rounded-xl text-emerald-400 text-sm font-mono glow-box-emerald">
                <div class="flex items-center gap-2">
                    <svg class="w-5 h-5 text-emerald-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 11V7a4 4 0 118 0m-4 8v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v6a2 2 0 002 2z"></path>
                    </svg>
                    <span>Status: Gateway Unlocked. Full Content Unlocked.</span>
                </div>
                <button onclick="lockPortal()" class="text-xs underline hover:text-emerald-300">Lock Gateway</button>
            </div>

            <!-- Internal Resource Cards Grid -->
            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                
                <!-- Internal Module 1 -->
                <div class="bg-slate-900 border border-slate-800 p-6 rounded-2xl hover:border-slate-700 transition space-y-3">
                    <div class="w-10 h-10 rounded-lg bg-blue-900/50 border border-blue-500/30 flex items-center justify-center text-blue-400">
                        <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 12h14M12 5l7 7-7 7"></path>
                        </svg>
                    </div>
                    <h4 class="text-lg font-bold text-white">Infrastructure Directory</h4>
                    <p class="text-sm text-slate-400">Access internal server logs, configuration repositories, and deployment pipelines.</p>
                </div>

                <!-- Internal Module 2 -->
                <div class="bg-slate-900 border border-slate-800 p-6 rounded-2xl hover:border-slate-700 transition space-y-3">
                    <div class="w-10 h-10 rounded-lg bg-emerald-900/50 border border-emerald-500/30 flex items-center justify-center text-emerald-400">
                        <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 002 2h2a2 2 0 002-2z"></path>
                        </svg>
                    </div>
                    <h4 class="text-lg font-bold text-white">System Metrics & Telemetry</h4>
                    <p class="text-sm text-slate-400">Monitor active network nodes, operational throughput, and real-time status.</p>
                </div>

            </div>
        </section>

    </main>

    <!-- FOOTER -->
    <footer class="bg-slate-900/60 border-t border-slate-800 mt-12 py-6 text-center text-xs text-slate-500">
        <div class="max-w-7xl mx-auto px-4 space-y-1">
            <p>© 2026 Nexus Infrastructure Group LLC. All rights reserved.</p>
            <p class="font-mono text-slate-600">Secure Access Gateway • System Version 2.4.0</p>
        </div>
    </footer>

    <!-- INTERACTIVE VERIFICATION SCRIPT -->
    <script>
        const targetCode = "381";
        let currentInput = "";

        function pressKey(num) {
            if (currentInput.length < 3) {
                currentInput += num;
                updateDisplay();
            }
        }

        function resetKeypad() {
            currentInput = "";
            updateDisplay();
            hideStatus();
        }

        function updateDisplay() {
            const display = document.getElementById('inputDisplay');
            display.textContent = currentInput.padEnd(3, '_');
        }

        function hideStatus() {
            const status = document.getElementById('statusMessage');
            status.classList.add('hidden');
        }

        function verifyLock() {
            const status = document.getElementById('statusMessage');
            status.classList.remove('hidden');

            if (currentInput === targetCode) {
                // Success Handling
                status.className = "text-center text-xs font-mono py-2 rounded-md bg-emerald-950 text-emerald-400 border border-emerald-800";
                status.textContent = "VERIFICATION SUCCESSFUL — UNLOCKING...";

                setTimeout(() => {
                    // Update Lock Icon Visuals
                    const lockContainer = document.getElementById('lockIconContainer');
                    const lockIcon = document.getElementById('lockIcon');
                    
                    lockContainer.className = "w-16 h-16 mx-auto rounded-full bg-emerald-950/80 border border-emerald-500/50 flex items-center justify-center glow-box-emerald";
                    lockIcon.className = "w-8 h-8 text-emerald-400";
                    lockIcon.innerHTML = `<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 11V7a4 4 0 118 0m-4 8v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v6a2 2 0 002 2z"></path>`;

                    document.getElementById('lockTitle').textContent = "Gateway Unlocked";
                    document.getElementById('lockSubtitle').textContent = "Visual verification complete. Operational assets revealed below.";

                    // Hide Mechanism & Show Protected Section
                    document.getElementById('lockMechanism').classList.add('hidden');
                    document.getElementById('verifyBtn').classList.add('hidden');

                    const protectedSection = document.getElementById('protectedContent');
                    protectedSection.classList.remove('hidden');
                    setTimeout(() => {
                        protectedSection.classList.remove('opacity-0', 'translate-y-4');
                    }, 50);

                }, 600);

            } else {
                // Failure Handling
                status.className = "text-center text-xs font-mono py-2 rounded-md bg-rose-950 text-rose-400 border border-rose-800";
                status.textContent = "INVALID CODE. PLEASE CHECK THE DISPLAYED PATTERN.";
                currentInput = "";
                updateDisplay();
            }
        }

        function lockPortal() {
            // Relock reset mechanism
            const protectedSection = document.getElementById('protectedContent');
            protectedSection.classList.add('opacity-0', 'translate-y-4');
            
            setTimeout(() => {
                protectedSection.classList.add('hidden');
                
                const lockContainer = document.getElementById('lockIconContainer');
                const lockIcon = document.getElementById('lockIcon');
                
                lockContainer.className = "w-16 h-16 mx-auto rounded-full bg-cyan-950/80 border border-cyan-500/30 flex items-center justify-center glow-box-cyan";
                lockIcon.className = "w-8 h-8 text-cyan-400";
                lockIcon.innerHTML = `<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 15v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v6a2 2 0 002 2zm10-10V7a4 4 0 00-8 0v4h8z"></path>`;

                document.getElementById('lockTitle').textContent = "Security Gateway Verification";
                document.getElementById('lockSubtitle').textContent = "Perform visual verification below by selecting the required security pattern sequence to unseal the protected infrastructure assets.";

                document.getElementById('lockMechanism').classList.remove('hidden');
                document.getElementById('verifyBtn').classList.remove('hidden');
                
                resetKeypad();
            }, 300);
        }
    </script>
</body>
</html>
<!DOCTYPE html>
<html lang="en" class="h-full bg-slate-950 text-slate-100">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nexus Infrastructure Group LLC — Secure Portal Gateway</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        obsidian: '#0B0F19',
                        navyDark: '#111827',
                        cyanGlow: '#0EA5E9',
                        emeraldGlow: '#10B981',
                        amberGlow: '#F59E0B',
                        roseGlow: '#EF4444'
                    },
                    fontFamily: {
                        sans: ['Inter', 'system-ui', 'sans-serif'],
                        mono: ['JetBrains Mono', 'Fira Code', 'monospace']
                    }
                }
            }
        }
    </script>
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>
    <style>
        /* Custom scrollbars for dark terminal look */
        ::-webkit-scrollbar {
            width: 6px;
            height: 6px;
        }
        ::-webkit-scrollbar-track {
            background: #0B0F19;
        }
        ::-webkit-scrollbar-thumb {
            background: #1E293B;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #0EA5E9;
        }
        /* Custom glow effects */
        .cyan-glow {
            box-shadow: 0 0 15px -3px rgba(14, 165, 233, 0.3);
        }
        .emerald-glow {
            box-shadow: 0 0 15px -3px rgba(16, 185, 129, 0.3);
        }
        .scanline {
            background: linear-gradient(
                to bottom,
                rgba(255,255,255,0),
                rgba(255,255,255,0) 50%,
                rgba(0, 0, 0, 0.3) 50%,
                rgba(0, 0, 0, 0.3)
            );
            background-size: 100% 4px;
        }
    </style>
</head>
<body class="h-full flex flex-col font-sans bg-obsidian text-slate-200 antialiased selection:bg-cyan-500 selection:text-slate-950 overflow-x-hidden">

    <!-- Top Security Banner -->
    <header class="bg-slate-900/90 border-b border-slate-800 px-4 py-2 text-xs flex flex-wrap justify-between items-center gap-2 backdrop-blur-md sticky top-0 z-50">
        <div class="flex items-center gap-3">
            <div class="flex items-center gap-2">
                <span class="relative flex h-2 w-2">
                    <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-emerald-400 opacity-75"></span>
                    <span class="relative inline-flex rounded-full h-2 w-2 bg-emerald-500"></span>
                </span>
                <span class="font-mono text-slate-400 uppercase tracking-widest font-semibold">TLS 1.3 Active</span>
            </div>
            <span class="text-slate-700">|</span>
            <span class="font-mono text-emerald-400 flex items-center gap-1">
                <i data-lucide="shield-check" class="w-3.5 h-3.5"></i> PKI ENCRYPTED NODE
            </span>
            <span class="text-slate-700 hidden sm:inline">|</span>
            <span class="text-slate-400 font-mono hidden sm:inline">GATEWAY ID: <span class="text-slate-200">NIG-US-EAST-09</span></span>
        </div>
        <div class="flex items-center gap-4 font-mono text-slate-400">
            <div class="flex items-center gap-1.5 bg-slate-950/60 px-2.5 py-1 rounded border border-slate-800">
                <i data-lucide="clock" class="w-3.5 h-3.5 text-cyan-400"></i>
                <span id="liveClock" class="text-slate-200 font-bold">2026-10-16 13:54:02 EST</span>
            </div>
        </div>
    </header>

    <!-- Main Header & Portal Navigation Swapper -->
    <section class="bg-gradient-to-r from-slate-900 via-slate-900/95 to-slate-900 border-b border-slate-800 px-4 sm:px-8 py-5">
        <div class="max-w-7xl mx-auto flex flex-col md:flex-row md:items-center justify-between gap-4">
            <div class="flex items-center gap-4">
                <div class="p-3 bg-cyan-500/10 border border-cyan-500/30 rounded-xl text-cyan-400">
                    <i data-lucide="cpu" class="w-8 h-8"></i>
                </div>
                <div>
                    <div class="flex items-center gap-2">
                        <h1 class="text-xl sm:text-2xl font-bold tracking-tight text-white">NEXUS INFRASTRUCTURE GROUP</h1>
                        <span class="px-2 py-0.5 text-[10px] font-mono uppercase tracking-wider bg-slate-800 text-cyan-400 border border-slate-700 rounded-full">LLC Enterprise</span>
                    </div>
                    <p class="text-xs sm:text-sm text-slate-400">Multi-Agent Control & Communication Portal Gateway</p>
                </div>
            </div>

            <!-- Main Tab Switcher -->
            <div class="flex bg-slate-950 p-1 rounded-xl border border-slate-800 self-start md:self-auto">
                <button id="tab-maci" onclick="switchPortal('maci')" class="flex items-center gap-2 px-5 py-2.5 rounded-lg text-sm font-medium transition-all duration-200 bg-cyan-500 text-slate-950 shadow-md font-mono">
                    <i data-lucide="terminal" class="w-4 h-4"></i>
                    <span>MACI GATEWAY</span>
                </button>
                <button id="tab-mailroom" onclick="switchPortal('mailroom')" class="flex items-center gap-2 px-5 py-2.5 rounded-lg text-sm font-medium transition-all duration-200 text-slate-400 hover:text-white font-mono">
                    <i data-lucide="mail" class="w-4 h-4"></i>
                    <span>N.I.G. MAILROOM</span>
                    <span id="unreadBadge" class="ml-1 px-1.5 py-0.5 text-[10px] bg-cyan-500/20 text-cyan-400 border border-cyan-500/30 rounded-full">3</span>
                </button>
            </div>
        </div>
    </section>

    <!-- Notification / Toast Container -->
    <div id="toastContainer" class="fixed bottom-5 right-5 z-50 flex flex-col gap-2 max-w-sm"></div>

    <!-- MAIN PORTAL CONTAINER -->
    <main class="flex-1 max-w-7xl w-full mx-auto p-4 sm:p-6 lg:p-8 space-y-6">

        <!-- ==================================================================== -->
        <!-- PORTAL 1: MACI SECURE GATEWAY -->
        <!-- ==================================================================== -->
        <div id="portal-maci" class="space-y-6">
            
            <!-- Auth Token Bar / Quick Status -->
            <div class="grid grid-cols-1 md:grid-cols-4 gap-4">
                <div class="bg-slate-900 border border-slate-800 rounded-xl p-4 flex items-center justify-between">
                    <div>
                        <div class="text-xs text-slate-400 font-mono">ACTIVE TOKEN</div>
                        <div class="text-sm font-mono font-bold text-emerald-400 flex items-center gap-1.5 mt-0.5">
                            <i data-lucide="key" class="w-3.5 h-3.5"></i> MACI-8849-AUTH-OK
                        </div>
                    </div>
                    <span class="px-2 py-1 text-[10px] font-mono bg-emerald-500/10 text-emerald-400 border border-emerald-500/20 rounded">VALID</span>
                </div>

                <div class="bg-slate-900 border border-slate-800 rounded-xl p-4 flex items-center justify-between">
                    <div>
                        <div class="text-xs text-slate-400 font-mono">ACTIVE AGENTS</div>
                        <div class="text-lg font-mono font-bold text-cyan-400 mt-0.5">14 / 16 THREADS</div>
                    </div>
                    <i data-lucide="bot" class="w-6 h-6 text-cyan-500/50"></i>
                </div>

                <div class="bg-slate-900 border border-slate-800 rounded-xl p-4 flex items-center justify-between">
                    <div>
                        <div class="text-xs text-slate-400 font-mono">NETWORK LATENCY</div>
                        <div class="text-lg font-mono font-bold text-slate-100 mt-0.5" id="latencyVal">12 ms</div>
                    </div>
                    <i data-lucide="activity" class="w-6 h-6 text-emerald-500/50"></i>
                </div>

                <div class="bg-slate-900 border border-slate-800 rounded-xl p-4 flex items-center justify-between">
                    <div>
                        <div class="text-xs text-slate-400 font-mono">NODE LOAD</div>
                        <div class="text-lg font-mono font-bold text-amber-400 mt-0.5" id="cpuVal">24.8%</div>
                    </div>
                    <i data-lucide="bar-chart-3" class="w-6 h-6 text-amber-500/50"></i>
                </div>
            </div>

            <!-- Central Split Layout: Interactive Console & Agent Matrix -->
            <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
                
                <!-- Interactive MACI Command Console (2 Cols) -->
                <div class="lg:col-span-2 bg-slate-900 border border-slate-800 rounded-xl overflow-hidden flex flex-col h-[520px] shadow-2xl relative">
                    <!-- Console Header -->
                    <div class="bg-slate-950 px-4 py-3 border-b border-slate-800 flex items-center justify-between">
                        <div class="flex items-center gap-2">
                            <div class="flex gap-1.5">
                                <span class="w-3 h-3 rounded-full bg-rose-500/80 inline-block"></span>
                                <span class="w-3 h-3 rounded-full bg-amber-500/80 inline-block"></span>
                                <span class="w-3 h-3 rounded-full bg-emerald-500/80 inline-block"></span>
                            </div>
                            <span class="text-xs font-mono text-slate-400 ml-2">maci-terminal-v4.2@nexusinfrastructuregroup.com</span>
                        </div>
                        <div class="flex items-center gap-2">
                            <button onclick="clearConsole()" class="text-slate-500 hover:text-slate-300 text-xs font-mono px-2 py-1 rounded bg-slate-900 border border-slate-800 hover:border-slate-700 transition">
                                Clear
                            </button>
                            <span class="px-2 py-0.5 text-[10px] font-mono bg-cyan-500/10 text-cyan-400 border border-cyan-500/20 rounded">
                                INTERACTIVE
                            </span>
                        </div>
                    </div>

                    <!-- Terminal Output Window -->
                    <div id="terminalOutput" class="flex-1 p-4 font-mono text-xs leading-relaxed overflow-y-auto space-y-2 scanline bg-slate-950/80">
                        <div class="text-slate-500">[SYSTEM INIT] Establishing TLS 1.3 socket to nexusinfrastructuregroup.com...</div>
                        <div class="text-emerald-400">[SUCCESS] MACI Core System Connected. Token Session active: [0x88F9A].</div>
                        <div class="text-cyan-400">[MACI PROTOCOL] Type '<span class="text-white font-bold">help</span>' or '<span class="text-white font-bold">agent --list</span>' for system commands.</div>
                        <div class="text-slate-400">----------------------------------------------------------------------</div>
                    </div>

                    <!-- Command Line Input -->
                    <form id="consoleForm" onsubmit="handleConsoleSubmit(event)" class="bg-slate-950 p-3 border-t border-slate-800 flex items-center gap-2">
                        <span class="text-cyan-400 font-mono text-xs font-bold pl-2">maci&gt;</span>
                        <input type="text" id="consoleInput" autocomplete="off" placeholder="Type a command (e.g. status, ping, agent --list, mailroom, connect)..." class="flex-1 bg-transparent border-none text-xs font-mono text-slate-100 focus:outline-none placeholder-slate-600">
                        <button type="submit" class="px-3 py-1.5 bg-cyan-600 hover:bg-cyan-500 text-slate-950 rounded font-mono text-xs font-bold transition">
                            EXEC
                        </button>
                    </form>
                </div>

                <!-- Agent Status Matrix (1 Col) -->
                <div class="bg-slate-900 border border-slate-800 rounded-xl p-5 flex flex-col justify-between space-y-4">
                    <div>
                        <div class="flex items-center justify-between mb-4">
                            <h2 class="text-sm font-bold font-mono text-slate-200 flex items-center gap-2">
                                <i data-lucide="network" class="w-4 h-4 text-cyan-400"></i>
                                AGENT MATRIX
                            </h2>
                            <span class="text-[10px] font-mono text-slate-400">AUTO-SYNC ON</span>
                        </div>

                        <!-- Agent Items -->
                        <div class="space-y-3 font-mono text-xs">
                            <div class="p-3 bg-slate-950 border border-slate-800/80 rounded-lg flex items-center justify-between">
                                <div class="flex items-center gap-2.5">
                                    <div class="w-2 h-2 rounded-full bg-emerald-400 animate-pulse"></div>
                                    <div>
                                        <div class="text-slate-200 font-bold">NODE-ALPHA-ROUTER</div>
                                        <div class="text-[10px] text-slate-500">Routing & Traffic Shaping</div>
                                    </div>
                                </div>
                                <span class="text-emerald-400 text-[10px]">99.98%</span>
                            </div>

                            <div class="p-3 bg-slate-950 border border-slate-800/80 rounded-lg flex items-center justify-between">
                                <div class="flex items-center gap-2.5">
                                    <div class="w-2 h-2 rounded-full bg-emerald-400"></div>
                                    <div>
                                        <div class="text-slate-200 font-bold">MACI-DISPATCH-AGENT</div>
                                        <div class="text-[10px] text-slate-500">Autonomous Task Queue</div>
                                    </div>
                                </div>
                                <span class="text-emerald-400 text-[10px]">ACTIVE</span>
                            </div>

                            <div class="p-3 bg-slate-950 border border-slate-800/80 rounded-lg flex items-center justify-between">
                                <div class="flex items-center gap-2.5">
                                    <div class="w-2 h-2 rounded-full bg-amber-400"></div>
                                    <div>
                                        <div class="text-slate-200 font-bold">MAILROOM-RELAY-1</div>
                                        <div class="text-[10px] text-slate-500">SMTP / Cryptographic Buffer</div>
                                    </div>
                                </div>
                                <span class="text-amber-400 text-[10px]">SYNCING</span>
                            </div>

                            <div class="p-3 bg-slate-950 border border-slate-800/80 rounded-lg flex items-center justify-between">
                                <div class="flex items-center gap-2.5">
                                    <div class="w-2 h-2 rounded-full bg-cyan-400"></div>
                                    <div>
                                        <div class="text-slate-200 font-bold">SECURITY-SENTINEL</div>
                                        <div class="text-[10px] text-slate-500">PKI Threat Detection</div>
                                    </div>
                                </div>
                                <span class="text-cyan-400 text-[10px]">MONITOR</span>
                            </div>
                        </div>
                    </div>

                    <div class="pt-2 border-t border-slate-800">
                        <button onclick="switchPortal('mailroom')" class="w-full py-2 px-3 bg-slate-800 hover:bg-slate-700 text-cyan-400 font-mono text-xs rounded-lg transition flex items-center justify-center gap-2">
                            <i data-lucide="arrow-right" class="w-3.5 h-3.5"></i> Jump to N.I.G. Mailroom Terminal
                        </button>
                    </div>
                </div>

            </div>
        </div>

        <!-- ==================================================================== -->
        <!-- PORTAL 2: N.I.G. MAILROOM TERMINAL -->
        <!-- ==================================================================== -->
        <div id="portal-mailroom" class="space-y-6 hidden">
            
            <!-- Top Controls & Search Bar -->
            <div class="flex flex-col sm:flex-row items-center justify-between gap-4 bg-slate-900 p-4 border border-slate-800 rounded-xl">
                <div class="flex items-center gap-3 w-full sm:w-auto">
                    <div class="p-2 bg-emerald-500/10 border border-emerald-500/30 rounded-lg text-emerald-400">
                        <i data-lucide="mail-check" class="w-5 h-5"></i>
                    </div>
                    <div>
                        <h2 class="text-base font-bold text-slate-100">N.I.G. SECURE MAILROOM TERMINAL</h2>
                        <p class="text-xs text-slate-400">Encrypted Infrastructure Dispatches & Corporate Inbox</p>
                    </div>
                </div>

                <!-- Inbox Filters -->
                <div class="flex items-center gap-2 w-full sm:w-auto justify-end">
                    <button onclick="filterMail('ALL')" class="mail-filter-btn px-3 py-1.5 text-xs font-mono rounded-lg bg-cyan-500 text-slate-950 font-bold" data-filter="ALL">ALL</button>
                    <button onclick="filterMail('SECURED')" class="mail-filter-btn px-3 py-1.5 text-xs font-mono rounded-lg bg-slate-800 text-slate-300 hover:bg-slate-700" data-filter="SECURED">SECURED</button>
                    <button onclick="filterMail('PENDING')" class="mail-filter-btn px-3 py-1.5 text-xs font-mono rounded-lg bg-slate-800 text-slate-300 hover:bg-slate-700" data-filter="PENDING">PENDING</button>
                </div>
            </div>

            <!-- Mailroom Grid: Inbox (Left) & Composer / Viewer (Right) -->
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-6">
                
                <!-- Inbox Telemetry Stream (5 Cols) -->
                <div class="lg:col-span-5 bg-slate-900 border border-slate-800 rounded-xl p-4 flex flex-col h-[580px]">
                    <div class="flex items-center justify-between pb-3 border-b border-slate-800">
                        <span class="text-xs font-mono text-slate-400 uppercase font-bold flex items-center gap-2">
                            <i data-lucide="inbox" class="w-4 h-4 text-cyan-400"></i> Dispatch Stream
                        </span>
                        <span class="text-[10px] font-mono text-emerald-400">ENCRYPTION: AES-GCM-256</span>
                    </div>

                    <div id="mailListContainer" class="flex-1 overflow-y-auto mt-3 space-y-2 pr-1">
                        <!-- Dynamic mail items populated by JS -->
                    </div>
                </div>

                <!-- Secure Dispatch Composer & Reader (7 Cols) -->
                <div class="lg:col-span-7 bg-slate-900 border border-slate-800 rounded-xl p-5 flex flex-col justify-between h-[580px]">
                    
                    <div class="space-y-4">
                        <div class="flex items-center justify-between pb-3 border-b border-slate-800">
                            <h3 class="text-sm font-bold font-mono text-slate-100 flex items-center gap-2">
                                <i data-lucide="send" class="w-4 h-4 text-cyan-400"></i>
                                COMPOSE ENCRYPTED DISPATCH
                            </h3>
                            <span class="px-2 py-0.5 text-[10px] font-mono bg-cyan-500/10 text-cyan-400 border border-cyan-500/30 rounded">
                                DIGITAL SIGNATURE REQUIRED
                            </span>
                        </div>

                        <form id="mailForm" onsubmit="dispatchMail(event)" class="space-y-3">
                            <div class="grid grid-cols-1 sm:grid-cols-2 gap-3">
                                <div>
                                    <label class="block text-[11px] font-mono text-slate-400 mb-1">RECIPIENT CHANNEL</label>
                                    <select id="mailRecipient" class="w-full bg-slate-950 border border-slate-800 rounded-lg p-2.5 text-xs text-slate-200 font-mono focus:border-cyan-500 focus:outline-none">
                                        <option value="maci-admin@nexusinfrastructuregroup.com">maci-admin@nexusinfrastructuregroup.com</option>
                                        <option value="security@nexusinfrastructuregroup.com">security@nexusinfrastructuregroup.com</option>
                                        <option value="operations@nexusinfrastructuregroup.com">operations@nexusinfrastructuregroup.com</option>
                                        <option value="mailroom-dispatch@nexusinfrastructuregroup.com">mailroom-dispatch@nexusinfrastructuregroup.com</option>
                                    </select>
                                </div>
                                <div>
                                    <label class="block text-[11px] font-mono text-slate-400 mb-1">PRIORITY LEVEL</label>
                                    <select id="mailPriority" class="w-full bg-slate-950 border border-slate-800 rounded-lg p-2.5 text-xs text-slate-200 font-mono focus:border-cyan-500 focus:outline-none">
                                        <option value="HIGH">HIGH (IMMEDIATE PKI DISPATCH)</option>
                                        <option value="STANDARD" selected>STANDARD</option>
                                        <option value="LOW">LOW LOG TRANSMISSION</option>
                                    </select>
                                </div>
                            </div>

                            <div>
                                <label class="block text-[11px] font-mono text-slate-400 mb-1">SUBJECT / REFERENCE</label>
                                <input type="text" id="mailSubject" required placeholder="e.g. Node-09 Maintenance Audit Payload" class="w-full bg-slate-950 border border-slate-800 rounded-lg p-2.5 text-xs text-slate-200 font-mono focus:border-cyan-500 focus:outline-none">
                            </div>

                            <div>
                                <label class="block text-[11px] font-mono text-slate-400 mb-1">PAYLOAD CONTENT (ENCRYPTED ON DISPATCH)</label>
                                <textarea id="mailBody" rows="4" required placeholder="Enter message payload data or system instruction..." class="w-full bg-slate-950 border border-slate-800 rounded-lg p-2.5 text-xs text-slate-200 font-mono focus:border-cyan-500 focus:outline-none"></textarea>
                            </div>

                            <!-- Drag and drop zone -->
                            <div>
                                <label class="block text-[11px] font-mono text-slate-400 mb-1">ATTACHMENT TRANSMISSION DROPZONE</label>
                                <div id="dropZone" onclick="triggerFileSelect()" class="border-2 border-dashed border-slate-800 hover:border-cyan-500/50 bg-slate-950/50 rounded-lg p-4 text-center cursor-pointer transition">
                                    <i data-lucide="upload-cloud" class="w-6 h-6 text-slate-500 mx-auto mb-1"></i>
                                    <p class="text-xs text-slate-400 font-mono" id="dropZoneText">Click or Drag & Drop secure files here to attach</p>
                                    <input type="file" id="fileInput" class="hidden" onchange="handleFileSelect(event)">
                                </div>
                            </div>

                            <button type="submit" class="w-full py-3 bg-gradient-to-r from-cyan-600 to-cyan-500 hover:from-cyan-500 hover:to-cyan-400 text-slate-950 font-mono font-bold text-xs rounded-lg transition flex items-center justify-center gap-2 shadow-lg">
                                <i data-lucide="lock" class="w-4 h-4"></i> DISPATCH ENCRYPTED PAYLOAD
                            </button>
                        </form>
                    </div>

                </div>

            </div>
        </div>

    </main>

    <!-- Footer -->
    <footer class="bg-slate-950 border-t border-slate-800 py-4 px-6 text-center text-xs font-mono text-slate-500 mt-auto">
        <div class="max-w-7xl mx-auto flex flex-col sm:flex-row items-center justify-between gap-2">
            <div>
                © 2026 NEXUS INFRASTRUCTURE GROUP LLC. ALL RIGHTS RESERVED.
            </div>
            <div class="flex items-center gap-4 text-slate-400">
                <span>SYSTEM VERSION: v8.4.1</span>
                <span>•</span>
                <a href="https://nexusinfrastructuregroup.com" target="_blank" class="hover:text-cyan-400 transition">OFFICIAL PORTAL DOMAIN</a>
            </div>
        </div>
    </footer>

    <!-- Interactive JavaScript state handling -->
    <script>
        // Lucide icons initialization
        lucide.createIcons();

        // System Data State
        let mails = [
            {
                id: 'MSG-8849',
                from: 'security-sentinel@nexusinfrastructuregroup.com',
                subject: 'PKI Certificate Key Rotation Completed',
                date: '2026-10-16 12:40 EST',
                status: 'SECURED',
                body: 'All active MACI interface nodes have updated their cryptographic handshakes. Node-09 verified.'
            },
            {
                id: 'MSG-8842',
                from: 'maci-dispatch@nexusinfrastructuregroup.com',
                subject: 'Autonomous Traffic Router - High Load Alert',
                date: '2026-10-16 11:15 EST',
                status: 'SECURED',
                body: 'Gateway capacity hit 78% during scheduled cluster syncing. Load balancing auto-adjusted.'
            },
            {
                id: 'MSG-8835',
                from: 'mailroom-admin@nexusinfrastructuregroup.com',
                subject: 'Pending Clearance for Protocol Upgrade',
                date: '2026-10-16 09:30 EST',
                status: 'PENDING',
                body: 'Scheduled dispatch for version 8.5.0 requires secondary key confirmation.'
            }
        ];

        let currentFilter = 'ALL';

        // Clock Functionality
        function updateClock() {
            const now = new Date();
            const year = now.getFullYear();
            const month = String(now.getMonth() + 1).padStart(2, '0');
            const day = String(now.getDate()).padStart(2, '0');
            const hours = String(now.getHours()).padStart(2, '0');
            const minutes = String(now.getMinutes()).padStart(2, '0');
            const seconds = String(now.getSeconds()).padStart(2, '0');
            
            document.getElementById('liveClock').textContent = `${year}-${month}-${day} ${hours}:${minutes}:${seconds} EST`;
        }
        setInterval(updateClock, 1000);
        updateClock();

        // Dynamic System Metrics Simulation
        setInterval(() => {
            const latency = Math.floor(Math.random() * 8) + 10;
            const cpu = (Math.random() * 5 + 22).toFixed(1);
            document.getElementById('latencyVal').textContent = `${latency} ms`;
            document.getElementById('cpuVal').textContent = `${cpu}%`;
        }, 3000);

        // Tab Swapper
        function switchPortal(portal) {
            const maciTab = document.getElementById('tab-maci');
            const mailroomTab = document.getElementById('tab-mailroom');
            const maciView = document.getElementById('portal-maci');
            const mailroomView = document.getElementById('portal-mailroom');

            if (portal === 'maci') {
                maciView.classList.remove('hidden');
                mailroomView.classList.add('hidden');

                maciTab.className = "flex items-center gap-2 px-5 py-2.5 rounded-lg text-sm font-medium transition-all duration-200 bg-cyan-500 text-slate-950 shadow-md font-mono";
                mailroomTab.className = "flex items-center gap-2 px-5 py-2.5 rounded-lg text-sm font-medium transition-all duration-200 text-slate-400 hover:text-white font-mono";
            } else {
                maciView.classList.add('hidden');
                mailroomView.classList.remove('hidden');

                mailroomTab.className = "flex items-center gap-2 px-5 py-2.5 rounded-lg text-sm font-medium transition-all duration-200 bg-cyan-500 text-slate-950 shadow-md font-mono";
                maciTab.className = "flex items-center gap-2 px-5 py-2.5 rounded-lg text-sm font-medium transition-all duration-200 text-slate-400 hover:text-white font-mono";
            }
        }

        // Terminal Console Logic
        function printToConsole(text, type = 'default') {
            const output = document.getElementById('terminalOutput');
            const line = document.createElement('div');

            if (type === 'cmd') {
                line.className = 'text-cyan-400 font-bold';
                line.textContent = `maci> ${text}`;
            } else if (type === 'success') {
                line.className = 'text-emerald-400';
                line.textContent = text;
            } else if (type === 'warn') {
                line.className = 'text-amber-400';
                line.textContent = text;
            } else if (type === 'error') {
                line.className = 'text-rose-400';
                line.textContent = text;
            } else {
                line.className = 'text-slate-300';
                line.textContent = text;
            }

            output.appendChild(line);
            output.scrollTop = output.scrollHeight;
        }

        function clearConsole() {
            document.getElementById('terminalOutput').innerHTML = '';
            printToConsole('[CONSOLE CLEARED]', 'warn');
        }

        function handleConsoleSubmit(e) {
            e.preventDefault();
            const input = document.getElementById('consoleInput');
            const rawCmd = input.value.trim();
            if (!rawCmd) return;

            printToConsole(rawCmd, 'cmd');
            input.value = '';

            const cmd = rawCmd.toLowerCase();

            setTimeout(() => {
                if (cmd === 'help') {
                    printToConsole('Available Commands:', 'warn');
                    printToConsole('  status        - Show MACI network status & node health');
                    printToConsole('  ping          - Test link to nexusinfrastructuregroup.com');
                    printToConsole('  agent --list  - Display active autonomous agent matrix');
                    printToConsole('  mailroom      - Switch context to N.I.G. Mailroom Terminal');
                    printToConsole('  connect       - Force PKI handshake re-validation');
                    printToConsole('  clear         - Clear terminal window');
                } else if (cmd === 'status') {
                    printToConsole('[STATUS REPORT] All nodes operational. TLS 1.3 Cipher Suite: TLS_AES_256_GCM_SHA384.', 'success');
                    printToConsole('Active Connections: 14 Threads. Gateway Latency: 12ms.');
                } else if (cmd === 'ping') {
                    printToConsole('PING nexusinfrastructuregroup.com (104.21.48.12): 56 data bytes');
                    printToConsole('64 bytes from 104.21.48.12: icmp_seq=1 ttl=58 time=11.4 ms', 'success');
                    printToConsole('64 bytes from 104.21.48.12: icmp_seq=2 ttl=58 time=12.1 ms', 'success');
                } else if (cmd === 'agent --list') {
                    printToConsole('NODE-ALPHA-ROUTER  [RUNNING]  Port 443  Priority: 10', 'success');
                    printToConsole('MACI-DISPATCH-AGENT[RUNNING]  Port 8080 Priority: 08', 'success');
                    printToConsole('SECURITY-SENTINEL  [MONITOR]  Port 9090 Priority: 01', 'success');
                } else if (cmd === 'mailroom') {
                    printToConsole('Switching interface to N.I.G. Mailroom Terminal...', 'warn');
                    switchPortal('mailroom');
                } else if (cmd === 'connect') {
                    printToConsole('[PKI HANDSHAKE] Re-authenticating cryptographic session with Nexus Core...', 'warn');
                    setTimeout(() => {
                        printToConsole('[PKI HANDSHAKE SUCCESS] Session Token Renewed.', 'success');
                    }, 600);
                } else if (cmd === 'clear') {
                    clearConsole();
                } else {
                    printToConsole(`Command not recognized: '${rawCmd}'. Type 'help' for options.`, 'error');
                }
            }, 150);
        }

        // Render Mail List
        function renderMailList() {
            const container = document.getElementById('mailListContainer');
            container.innerHTML = '';

            const filteredMails = mails.filter(m => currentFilter === 'ALL' || m.status === currentFilter);

            if (filteredMails.length === 0) {
                container.innerHTML = `<div class="p-4 text-center text-xs font-mono text-slate-500">No dispatches found for current filter.</div>`;
                return;
            }

            filteredMails.forEach(mail => {
                const card = document.createElement('div');
                card.className = "p-3 bg-slate-950 border border-slate-800 hover:border-slate-700 rounded-lg cursor-pointer transition space-y-1.5";
                
                const statusColor = mail.status === 'SECURED' 
                    ? 'bg-emerald-500/10 text-emerald-400 border-emerald-500/30' 
                    : 'bg-amber-500/10 text-amber-400 border-amber-500/30';

                card.innerHTML = `
                    <div class="flex items-center justify-between">
                        <span class="text-[10px] font-mono font-bold text-slate-400">${mail.id}</span>
                        <span class="px-2 py-0.5 text-[9px] font-mono border rounded ${statusColor}">${mail.status}</span>
                    </div>
                    <div class="text-xs font-bold text-slate-200 truncate">${mail.subject}</div>
                    <div class="text-[11px] font-mono text-slate-400 truncate">${mail.from}</div>
                    <div class="text-[10px] font-mono text-slate-500 text-right">${mail.date}</div>
                `;

                card.onclick = () => {
                    showToast(`Loaded Dispatch ${mail.id}`, 'info');
                    document.getElementById('mailSubject').value = `RE: ${mail.subject}`;
                };

                container.appendChild(card);
            });
        }

        function filterMail(filter) {
            currentFilter = filter;
            document.querySelectorAll('.mail-filter-btn').forEach(btn => {
                if (btn.dataset.filter === filter) {
                    btn.className = "mail-filter-btn px-3 py-1.5 text-xs font-mono rounded-lg bg-cyan-500 text-slate-950 font-bold";
                } else {
                    btn.className = "mail-filter-btn px-3 py-1.5 text-xs font-mono rounded-lg bg-slate-800 text-slate-300 hover:bg-slate-700";
                }
            });
            renderMailList();
        }

        // File Attachment Simulation
        function triggerFileSelect() {
            document.getElementById('fileInput').click();
        }

        function handleFileSelect(e) {
            const files = e.target.files;
            if (files.length > 0) {
                document.getElementById('dropZoneText').textContent = `Attached: ${files[0].name} (${(files[0].size/1024).toFixed(1)} KB)`;
                showToast(`Attached file: ${files[0].name}`, 'info');
            }
        }

        // Dispatch Mail Action
        function dispatchMail(e) {
            e.preventDefault();
            const recipient = document.getElementById('mailRecipient').value;
            const subject = document.getElementById('mailSubject').value;
            const body = document.getElementById('mailBody').value;

            const newMail = {
                id: `MSG-${Math.floor(1000 + Math.random() * 9000)}`,
                from: 'you@nexusinfrastructuregroup.com',
                subject: subject,
                date: new Date().toISOString().replace('T', ' ').substring(0, 16) + ' EST',
                status: 'SECURED',
                body: body
            };

            mails.unshift(newMail);
            renderMailList();

            // Clear inputs
            document.getElementById('mailSubject').value = '';
            document.getElementById('mailBody').value = '';
            document.getElementById('dropZoneText').textContent = 'Click or Drag & Drop secure files here to attach';

            showToast(`Encrypted dispatch ${newMail.id} sent successfully!`, 'success');
            printToConsole(`[MAILROOM DISPATCH] Sent ${newMail.id} to ${recipient}`, 'success');
        }

        // Toast Notification System
        function showToast(message, type = 'info') {
            const container = document.getElementById('toastContainer');
            const toast = document.createElement('div');

            const bgColor = type === 'success' 
                ? 'bg-slate-900 border-emerald-500/50 text-emerald-400' 
                : 'bg-slate-900 border-cyan-500/50 text-cyan-400';

            toast.className = `p-3 border rounded-xl shadow-2xl flex items-center gap-3 text-xs font-mono backdrop-blur-md ${bgColor} animate-bounce`;
            toast.innerHTML = `
                <i data-lucide="shield-check" class="w-4 h-4"></i>
                <span>${message}</span>
            `;

            container.appendChild(toast);
            lucide.createIcons();

            setTimeout(() => {
                toast.remove();
            }, 3500);
        }

        // Initial Load
        renderMailList();
    </script>
</body>
</html>