# NIG
NE>&lt;US
html
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