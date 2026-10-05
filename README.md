```html
<!DOCTYPE html>
<html lang="vi" class="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HungAimlock VIP Pro Max - Hack Simulator</title>
    
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        cyber: {
                            black: '#030307',
                            card: '#0a0d16',
                            border: '#162032',
                            cyan: '#00f0ff',
                            magenta: '#ff007f',
                            yellow: '#ffe600',
                            red: '#ff003c',
                            green: '#00ff66',
                            purple: '#a855f7'
                        }
                    },
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        mono: ['Fira Code', 'monospace']
                    }
                }
            }
        }
    </script>
    
    <!-- FontAwesome CDN -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <style>
        @import url('https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;600;700&family=Inter:wght@400;600;700;900&display=swap');

        body {
            background-color: #030307;
            color: #f1f5f9;
            font-family: 'Inter', sans-serif;
            overflow-x: hidden;
            user-select: none;
            -webkit-user-select: none;
        }

        /* Canvas particles */
        #bg-canvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            z-index: 0;
            pointer-events: none;
        }

        /* Ambient Dynamic Light Rays */
        .ambient-ray {
            position: fixed;
            width: 450px;
            height: 450px;
            border-radius: 50%;
            filter: blur(130px);
            opacity: 0.18;
            pointer-events: none;
            z-index: 1;
            animation: pulseRay 8s infinite alternate ease-in-out;
        }

        @keyframes pulseRay {
            0% { transform: scale(1) translate(0, 0); opacity: 0.15; }
            50% { transform: scale(1.3) translate(40px, -30px); opacity: 0.25; }
            100% { transform: scale(0.9) translate(-40px, 40px); opacity: 0.18; }
        }

        /* Interactive Card Light Streak Sweep Effect */
        .card-cyber {
            position: relative;
            overflow: hidden;
            transition: all 0.25s ease;
            background: linear-gradient(135deg, rgba(10, 13, 22, 0.95), rgba(6, 8, 14, 0.95));
        }

        .card-cyber::before {
            content: '';
            position: absolute;
            top: 0;
            left: -150%;
            width: 80%;
            height: 100%;
            background: linear-gradient(
                90deg, 
                transparent, 
                rgba(0, 240, 255, 0.2), 
                rgba(255, 0, 127, 0.3), 
                transparent
            );
            transform: skewX(-25deg);
            pointer-events: none;
        }

        .card-cyber.trigger-streak::before {
            animation: lightSweep 0.65s ease-out forwards;
        }

        @keyframes lightSweep {
            0% { left: -150%; opacity: 1; }
            100% { left: 200%; opacity: 0; }
        }

        /* Touch/Cursor Pointer Click Spark Trail */
        .spark-trail {
            position: fixed;
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: radial-gradient(circle, #00f0ff 0%, #ff007f 100%);
            box-shadow: 0 0 15px #00f0ff, 0 0 30px #ff007f;
            pointer-events: none;
            z-index: 9999;
            transform: translate(-50%, -50%) scale(1);
            animation: sparkFade 0.5s ease-out forwards;
        }

        @keyframes sparkFade {
            0% { opacity: 1; transform: translate(-50%, -50%) scale(1); }
            100% { opacity: 0; transform: translate(-50%, -50%) scale(2.5); }
        }

        /* Key Input Shake Error Animation */
        @keyframes shakeError {
            0%, 100% { transform: translateX(0); }
            15%, 45%, 75% { transform: translateX(-12px) rotate(-1deg); }
            30%, 60%, 90% { transform: translateX(12px) rotate(1deg); }
        }

        .shake-error {
            animation: shakeError 0.45s ease-in-out;
            border-color: #ff003c !important;
            box-shadow: 0 0 30px rgba(255, 0, 60, 0.8), inset 0 0 10px rgba(255, 0, 60, 0.4) !important;
        }

        /* Light Blast Animation on Login Success */
        .light-blast {
            position: fixed;
            inset: 0;
            background: radial-gradient(circle, rgba(0,240,255,1) 0%, rgba(255,0,127,1) 50%, rgba(255,255,255,1) 100%);
            z-index: 999;
            pointer-events: none;
            animation: blastFade 0.8s ease-out forwards;
        }

        @keyframes blastFade {
            0% { opacity: 1; transform: scale(0.5); }
            50% { opacity: 0.9; transform: scale(1.2); }
            100% { opacity: 0; transform: scale(2); }
        }

        /* Neon Glow Utility Classes */
        .glow-cyan { box-shadow: 0 0 20px rgba(0, 240, 255, 0.35); }
        .glow-magenta { box-shadow: 0 0 20px rgba(255, 0, 127, 0.35); }
        .glow-red { box-shadow: 0 0 25px rgba(255, 0, 60, 0.5); }
        .text-glow-cyan { text-shadow: 0 0 10px rgba(0, 240, 255, 0.8); }
        .text-glow-magenta { text-shadow: 0 0 10px rgba(255, 0, 127, 0.8); }
        .text-glow-red { text-shadow: 0 0 10px rgba(255, 0, 60, 0.9); }

        /* Laser Sweep Progress Bar */
        .laser-bar {
            position: relative;
            overflow: hidden;
        }

        .laser-bar::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            bottom: 0;
            width: 40px;
            background: linear-gradient(90deg, transparent, #ffffff, transparent);
            animation: laserMove 1.2s infinite linear;
        }

        @keyframes laserMove {
            0% { left: -40px; }
            100% { left: 100%; }
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar { width: 6px; }
        ::-webkit-scrollbar-track { background: #030307; }
        ::-webkit-scrollbar-thumb { background: #162032; border-radius: 3px; }
        ::-webkit-scrollbar-thumb:hover { background: #00f0ff; }
    </style>
</head>
<body class="relative min-h-screen flex flex-col items-center justify-center p-3 sm:p-6 overflow-x-hidden">

    <!-- Particle Background Canvas -->
    <canvas id="bg-canvas"></canvas>

    <!-- Dynamic Glowing Ambient Rays -->
    <div class="ambient-ray bg-cyber-cyan top-5 left-5"></div>
    <div class="ambient-ray bg-cyber-magenta bottom-5 right-5"></div>

    <!-- MAIN CONTAINER -->
    <main class="relative z-10 w-full max-w-4xl bg-cyber-card/90 backdrop-blur-2xl border border-cyber-border/80 rounded-2xl p-4 sm:p-8 shadow-2xl shadow-cyan-950/40 my-auto">
        
        <!-- APP HEADER -->
        <header class="flex flex-col sm:flex-row items-center justify-between gap-4 pb-6 mb-6 border-b border-cyber-border/80">
            <div class="flex items-center gap-3">
                <div class="relative flex items-center justify-center w-14 h-14 rounded-2xl bg-gradient-to-br from-cyber-cyan via-cyber-purple to-cyber-magenta p-[2px] glow-cyan">
                    <div class="w-full h-full bg-cyber-black rounded-[14px] flex items-center justify-center">
                        <i class="fa-solid fa-crosshairs text-cyber-cyan text-2xl animate-pulse"></i>
                    </div>
                </div>
                <div class="text-center sm:text-left">
                    <h1 class="text-2xl sm:text-3xl font-black italic tracking-wider bg-gradient-to-r from-cyber-cyan via-white to-cyber-magenta bg-clip-text text-transparent">
                        HUNG AIMLOCK <span class="text-xs non-italic text-cyber-yellow border border-cyber-yellow/40 bg-cyber-yellow/10 px-2.5 py-0.5 rounded-full font-mono uppercase tracking-normal">VIP PRO MAX</span>
                    </h1>
                    <p class="text-xs text-gray-400 flex items-center justify-center sm:justify-start gap-2 mt-1 font-mono">
                        <span class="w-2 h-2 rounded-full bg-cyber-green animate-ping"></span>
                        BYPASS ENGINE: <span class="text-cyber-green font-semibold">ANTI-BAN 100% ACTIVE</span>
                    </p>
                </div>
            </div>

            <!-- OS SELECTOR TAB SWITCHER (Revealed after Key Auth) -->
            <div id="os-selector-header" class="hidden flex items-center p-1.5 bg-cyber-black/90 rounded-xl border border-cyber-border shadow-inner">
                <button id="btn-tab-android" onclick="switchOS('android')" class="flex items-center gap-2 px-5 py-2.5 rounded-lg text-xs font-bold transition-all bg-cyber-cyan/20 text-cyber-cyan border border-cyber-cyan/50 glow-cyan">
                    <i class="fa-brands fa-android text-base"></i>
                    TAB 1: ADR (ANDROID)
                </button>
                <button id="btn-tab-ios" onclick="switchOS('ios')" class="flex items-center gap-2 px-5 py-2.5 rounded-lg text-xs font-bold transition-all text-gray-400 hover:text-white">
                    <i class="fa-brands fa-apple text-base"></i>
                    TAB 2: IOS (APPLE)
                </button>
            </div>
        </header>

        <!-- 1. KEY VALIDATION GATEWAY -->
        <section id="auth-section" class="py-10 sm:py-16 flex flex-col items-center justify-center text-center">
            <div class="w-20 h-20 mb-5 rounded-2xl bg-cyber-red/10 border border-cyber-red/40 flex items-center justify-center text-cyber-red glow-red animate-pulse">
                <i class="fa-solid fa-user-shield text-4xl"></i>
            </div>
            
            <h2 class="text-2xl sm:text-3xl font-black text-white mb-2 tracking-wider uppercase font-mono">XÁC THỰC QUYỀN TRUY CẬP</h2>
            <p class="text-xs sm:text-sm text-gray-400 max-w-md mb-8 leading-relaxed font-sans">
                Vui lòng nhập Khóa VIP License Key cá nhân của bạn để mở khóa toàn bộ menu chức năng HungAimlock FF.
            </p>

            <div class="w-full max-w-md space-y-4">
                <div class="relative">
                    <input type="password" id="key-input" placeholder="Nhập Key VIP..." 
                        onkeydown="if(event.key==='Enter') validateKey()"
                        class="w-full bg-cyber-black/90 border border-cyber-border focus:border-cyber-cyan rounded-xl px-4 py-4 pl-12 pr-12 text-white placeholder-gray-500 outline-none transition-all duration-300 font-mono text-sm tracking-wider">
                    <i class="fa-solid fa-key absolute left-4 top-1/2 -translate-y-1/2 text-gray-500"></i>
                    <button type="button" onclick="toggleKeyVisibility()" class="absolute right-4 top-1/2 -translate-y-1/2 text-gray-500 hover:text-white p-1">
                        <i id="eye-icon" class="fa-solid fa-eye"></i>
                    </button>
                </div>

                <!-- Error Alert Box -->
                <div id="auth-error-msg" class="hidden p-3.5 rounded-xl bg-cyber-red/20 border border-cyber-red/60 text-cyber-red text-xs font-bold flex items-center justify-center gap-2 text-glow-red">
                    <i class="fa-solid fa-circle-exclamation text-base"></i>
                    <span id="auth-error-text">KEY KHÔNG CHÍNH XÁC!</span>
                </div>

                <button onclick="validateKey()" class="w-full py-4 rounded-xl font-black text-sm tracking-widest uppercase bg-gradient-to-r from-cyber-cyan via-blue-600 to-cyber-magenta hover:brightness-110 active:scale-[0.99] transition-all text-black shadow-lg shadow-cyan-500/20 flex items-center justify-center gap-2">
                    <i class="fa-solid fa-unlock-keyhole"></i>
                    XÁC NHẬN KEY
                </button>
            </div>
        </section>

        <!-- 2. MAIN DASHBOARD CONTENT (Revealed After Key Auth) -->
        <section id="dashboard-section" class="hidden space-y-6">
            
            <!-- VIP STATUS BAR -->
            <div class="flex flex-col sm:flex-row items-center justify-between gap-4 p-4 rounded-xl bg-cyber-black/80 border border-cyber-border">
                <div class="flex items-center gap-3">
                    <div class="w-10 h-10 rounded-xl bg-gradient-to-br from-cyber-cyan to-cyber-magenta p-[1px]">
                        <div class="w-full h-full bg-cyber-black rounded-[10px] flex items-center justify-center text-cyber-cyan">
                            <i class="fa-solid fa-id-badge text-lg"></i>
                        </div>
                    </div>
                    <div>
                        <div class="text-sm font-bold text-white flex items-center gap-2">
                            HUNGAIMLOCK VIP SUBSCRIBER
                            <span class="text-[10px] bg-cyber-green/20 text-cyber-green border border-cyber-green/40 px-2 py-0.5 rounded font-mono">VERIFIED</span>
                        </div>
                        <div class="text-xs text-gray-400 font-mono">MEMORY ADDRESS: 0x7FFA89B200 - OK</div>
                    </div>
                </div>
                <button onclick="lockSystem()" class="px-4 py-2 rounded-lg border border-cyber-red/50 bg-cyber-red/10 text-cyber-red text-xs font-bold hover:bg-cyber-red/20 transition-all flex items-center gap-2 font-mono">
                    <i class="fa-solid fa-right-from-bracket"></i> ĐỔI KEY / KHÓA
                </button>
            </div>

            <!-- TAB 1: ANDROID (ADR) MENU -->
            <div id="panel-android" class="space-y-5">
                <div class="flex items-center justify-between border-b border-cyber-border/60 pb-2">
                    <h3 class="text-sm font-bold text-cyber-cyan tracking-wider uppercase flex items-center gap-2 font-mono">
                        <i class="fa-brands fa-android text-base"></i> DANH SÁCH CHỨC NĂNG (ANDROID VIP)
                    </h3>
                    <span class="text-[11px] text-gray-500 font-mono">ADR BYPASS v6.0</span>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                    <!-- Feature Item 1 -->
                    <div class="card-cyber p-4 rounded-xl border border-cyber-border hover:border-cyber-cyan/60 flex items-center justify-between cursor-pointer" onclick="triggerLightStreak(this)">
                        <div>
                            <div class="text-sm font-semibold text-white flex items-center gap-2">
                                <i class="fa-solid fa-crosshairs text-cyber-cyan"></i> Aimlock 100% Đau Đầu
                            </div>
                            <div class="text-xs text-gray-400 mt-1">Tự động găm cứng tâm vào đầu đối thủ</div>
                        </div>
                        <label class="relative inline-flex items-center cursor-pointer" onclick="event.stopPropagation()">
                            <input type="checkbox" class="sr-only peer" onchange="playToggleSound(this)">
                            <div class="w-11 h-6 bg-gray-800 peer-focus:outline-none rounded-full peer peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all peer-checked:bg-cyber-cyan"></div>
                        </label>
                    </div>

                    <!-- Feature Item 2 -->
                    <div class="card-cyber p-4 rounded-xl border border-cyber-border hover:border-cyber-cyan/60 flex items-center justify-between cursor-pointer" onclick="triggerLightStreak(this)">
                        <div>
                            <div class="text-sm font-semibold text-white flex items-center gap-2">
                                <i class="fa-solid fa-bullseye text-cyber-magenta"></i> Aimbot Đạn Đuổi
                            </div>
                            <div class="text-xs text-gray-400 mt-1">Đường đạn tự bẻ cong xoáy thẳng vào địch</div>
                        </div>
                        <label class="relative inline-flex items-center cursor-pointer" onclick="event.stopPropagation()">
                            <input type="checkbox" class="sr-only peer" onchange="playToggleSound(this)">
                            <div class="w-11 h-6 bg-gray-800 peer-focus:outline-none rounded-full peer peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all peer-checked:bg-cyber-cyan"></div>
                        </label>
                    </div>

                    <!-- Feature Item 3 -->
                    <div class="card-cyber p-4 rounded-xl border border-cyber-border hover:border-cyber-cyan/60 flex items-center justify-between cursor-pointer" onclick="triggerLightStreak(this)">
                        <div>
                            <div class="text-sm font-semibold text-white flex items-center gap-2">
                                <i class="fa-solid fa-gauge-high text-cyber-yellow"></i> Ghì Tâm Anti-Recoil 99%
                            </div>
                            <div class="text-xs text-gray-400 mt-1">Triệt tiêu độ rung găm súng tuyệt đối</div>
                        </div>
                        <label class="relative inline-flex items-center cursor-pointer" onclick="event.stopPropagation()">
                            <input type="checkbox" class="sr-only peer" onchange="playToggleSound(this)">
                            <div class="w-11 h-6 bg-gray-800 peer-focus:outline-none rounded-full peer peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all peer-checked:bg-cyber-cyan"></div>
                        </label>
                    </div>

                    <!-- Feature Item 4 -->
                    <div class="card-cyber p-4 rounded-xl border border-cyber-border hover:border-cyber-cyan/60 flex items-center justify-between cursor-pointer" onclick="triggerLightStreak(this)">
                        <div>
                            <div class="text-sm font-semibold text-white flex items-center gap-2">
                                <i class="fa-solid fa-eye text-cyber-green"></i> ESP Nam Tỏ Tường
                            </div>
                            <div class="text-xs text-gray-400 mt-1">Hiện vị trí, thanh máu và khoảng cách địch</div>
                        </div>
                        <label class="relative inline-flex items-center cursor-pointer" onclick="event.stopPropagation()">
                            <input type="checkbox" class="sr-only peer" onchange="playToggleSound(this)">
                            <div class="w-11 h-6 bg-gray-800 peer-focus:outline-none rounded-full peer peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all peer-checked:bg-cyber-cyan"></div>
                        </label>
                    </div>

                    <!-- Feature Item 5 -->
                    <div class="card-cyber p-4 rounded-xl border border-cyber-border hover:border-cyber-cyan/60 flex items-center justify-between cursor-pointer" onclick="triggerLightStreak(this)">
                        <div>
                            <div class="text-sm font-semibold text-white flex items-center gap-2">
                                <i class="fa-solid fa-bolt text-cyber-purple"></i> Tăng Tốc Độ Đạn 2x
                            </div>
                            <div class="text-xs text-gray-400 mt-1">Tăng tốc độ đạn găm ngay lập tức</div>
                        </div>
                        <label class="relative inline-flex items-center cursor-pointer" onclick="event.stopPropagation()">
                            <input type="checkbox" class="sr-only peer" onchange="playToggleSound(this)">
                            <div class="w-11 h-6 bg-gray-800 peer-focus:outline-none rounded-full peer peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all peer-checked:bg-cyber-cyan"></div>
                        </label>
                    </div>

                    <!-- Feature Item 6 -->
                    <div class="card-cyber p-4 rounded-xl border border-cyber-border hover:border-cyber-cyan/60 flex items-center justify-between cursor-pointer" onclick="triggerLightStreak(this)">
                        <div>
                            <div class="text-sm font-semibold text-white flex items-center gap-2">
                                <i class="fa-solid fa-wind text-blue-400"></i> Xóa Sương Mờ & Giảm Lag
                            </div>
                            <div class="text-xs text-gray-400 mt-1">Xóa cỏ, sương mù và tối ưu hóa 120 FPS</div>
                        </div>
                        <label class="relative inline-flex items-center cursor-pointer" onclick="event.stopPropagation()">
                            <input type="checkbox" class="sr-only peer" onchange="playToggleSound(this)">
                            <div class="w-11 h-6 bg-gray-800 peer-focus:outline-none rounded-full peer peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all peer-checked:bg-cyber-cyan"></div>
                        </label>
                    </div>

                    <!-- Feature Item 7 -->
                    <div class="card-cyber p-4 rounded-xl border border-cyber-border hover:border-cyber-cyan/60 flex items-center justify-between cursor-pointer" onclick="triggerLightStreak(this)">
                        <div>
                            <div class="text-sm font-semibold text-white flex items-center gap-2">
                                <i class="fa-solid fa-shield-halved text-cyber-green"></i> Bypass Anticheat FF Max
                            </div>
                            <div class="text-xs text-gray-400 mt-1">Vượt qua khiên quét anticheat mới nhất</div>
                        </div>
                        <label class="relative inline-flex items-center cursor-pointer" onclick="event.stopPropagation()">
                            <input type="checkbox" checked class="sr-only peer" onchange="playToggleSound(this)">
                            <div class="w-11 h-6 bg-gray-800 peer-focus:outline-none rounded-full peer peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all peer-checked:bg-cyber-cyan"></div>
                        </label>
                    </div>

                    <!-- Feature Item 8 -->
                    <div class="card-cyber p-4 rounded-xl border border-cyber-border hover:border-cyber-cyan/60 flex items-center justify-between cursor-pointer" onclick="triggerLightStreak(this)">
                        <div>
                            <div class="text-sm font-semibold text-white flex items-center gap-2">
                                <i class="fa-solid fa-hand-pointer text-pink-400"></i> Auto Headshot Drag Scope
                            </div>
                            <div class="text-xs text-gray-400 mt-1">Mở ống ngắm tự động kéo tâm vào đầu</div>
                        </div>
                        <label class="relative inline-flex items-center cursor-pointer" onclick="event.stopPropagation()">
                            <input type="checkbox" class="sr-only peer" onchange="playToggleSound(this)">
                            <div class="w-11 h-6 bg-gray-800 peer-focus:outline-none rounded-full peer peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all peer-checked:bg-cyber-cyan"></div>
                        </label>
                    </div>
                </div>
            </div>

            <!-- TAB 2: IOS (APPLE) MENU -->
            <div id="panel-ios" class="hidden space-y-5">
                <div class="flex items-center justify-between border-b border-cyber-border/60 pb-2">
                    <h3 class="text-sm font-bold text-cyber-magenta tracking-wider uppercase flex items-center gap-2 font-mono">
                        <i class="fa-brands fa-apple text-base"></i> DANH SÁCH CHỨC NĂNG (IOS APPLE)
                    </h3>
                    <span class="text-[11px] text-gray-500 font-mono">IOS DNS PROFILE v6.0</span>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                    <!-- iOS Feature 1 -->
                    <div class="card-cyber p-4 rounded-xl border border-cyber-border hover:border-cyber-magenta/60 flex items-center justify-between cursor-pointer" onclick="triggerLightStreak(this)">
                        <div>
                            <div class="text-sm font-semibold text-white flex items-center gap-2">
                                <i class="fa-solid fa-crosshairs text-cyber-magenta"></i> Aimlock 100% Đau Đầu (iOS)
                            </div>
                            <div class="text-xs text-gray-400 mt-1">Dính tâm đầu siêu mượt trên màn hình Apple</div>
                        </div>
                        <label class="relative inline-flex items-center cursor-pointer" onclick="event.stopPropagation()">
                            <input type="checkbox" class="sr-only peer" onchange="playToggleSound(this)">
                            <div class="w-11 h-6 bg-gray-800 peer-focus:outline-none rounded-full peer peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all peer-checked:bg-cyber-magenta"></div>
                        </label>
                    </div>

                    <!-- iOS Feature 2 -->
                    <div class="card-cyber p-4 rounded-xl border border-cyber-border hover:border-cyber-magenta/60 flex items-center justify-between cursor-pointer" onclick="triggerLightStreak(this)">
                        <div>
                            <div class="text-sm font-semibold text-white flex items-center gap-2">
                                <i class="fa-solid fa-bullseye text-cyber-cyan"></i> Aimbot Đạn Đuổi (iOS)
                            </div>
                            <div class="text-xs text-gray-400 mt-1">Bẻ cong đường đạn không cần Jailbreak</div>
                        </div>
                        <label class="relative inline-flex items-center cursor-pointer" onclick="event.stopPropagation()">
                            <input type="checkbox" class="sr-only peer" onchange="playToggleSound(this)">
                            <div class="w-11 h-6 bg-gray-800 peer-focus:outline-none rounded-full peer peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all peer-checked:bg-cyber-magenta"></div>
                        </label>
                    </div>

                    <!-- iOS Feature 3 -->
                    <div class="card-cyber p-4 rounded-xl border border-cyber-border hover:border-cyber-magenta/60 flex items-center justify-between cursor-pointer" onclick="triggerLightStreak(this)">
                        <div>
                            <div class="text-sm font-semibold text-white flex items-center gap-2">
                                <i class="fa-solid fa-mobile-screen text-cyber-yellow"></i> Tăng Độ Nhạy Touch iOS 3x
                            </div>
                            <div class="text-xs text-gray-400 mt-1">Tăng phản hồi vuốt cảm ứng nhạy bén</div>
                        </div>
                        <label class="relative inline-flex items-center cursor-pointer" onclick="event.stopPropagation()">
                            <input type="checkbox" class="sr-only peer" onchange="playToggleSound(this)">
                            <div class="w-11 h-6 bg-gray-800 peer-focus:outline-none rounded-full peer peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all peer-checked:bg-cyber-magenta"></div>
                        </label>
                    </div>

                    <!-- iOS Feature 4 -->
                    <div class="card-cyber p-4 rounded-xl border border-cyber-border hover:border-cyber-magenta/60 flex items-center justify-between cursor-pointer" onclick="triggerLightStreak(this)">
                        <div>
                            <div class="text-sm font-semibold text-white flex items-center gap-2">
                                <i class="fa-solid fa-network-wired text-cyber-green"></i> Custom DNS Profile Bypass
                            </div>
                            <div class="text-xs text-gray-400 mt-1">Tối ưu Ping & chặn máy chủ kiểm duyệt Garena</div>
                        </div>
                        <label class="relative inline-flex items-center cursor-pointer" onclick="event.stopPropagation()">
                            <input type="checkbox" checked class="sr-only peer" onchange="playToggleSound(this)">
                            <div class="w-11 h-6 bg-gray-800 peer-focus:outline-none rounded-full peer peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all peer-checked:bg-cyber-magenta"></div>
                        </label>
                    </div>

                    <!-- iOS Feature 5 -->
                    <div class="card-cyber p-4 rounded-xl border border-cyber-border hover:border-cyber-magenta/60 flex items-center justify-between cursor-pointer" onclick="triggerLightStreak(this)">
                        <div>
                            <div class="text-sm font-semibold text-white flex items-center gap-2">
                                <i class="fa-solid fa-rocket text-cyber-purple"></i> 120 FPS Promotion Unlocked
                            </div>
                            <div class="text-xs text-gray-400 mt-1">Mở khóa đồ họa tần số quét tối đa</div>
                        </div>
                        <label class="relative inline-flex items-center cursor-pointer" onclick="event.stopPropagation()">
                            <input type="checkbox" class="sr-only peer" onchange="playToggleSound(this)">
                            <div class="w-11 h-6 bg-gray-800 peer-focus:outline-none rounded-full peer peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all peer-checked:bg-cyber-magenta"></div>
                        </label>
                    </div>

                    <!-- iOS Feature 6 -->
                    <div class="card-cyber p-4 rounded-xl border border-cyber-border hover:border-cyber-magenta/60 flex items-center justify-between cursor-pointer" onclick="triggerLightStreak(this)">
                        <div>
                            <div class="text-sm font-semibold text-white flex items-center gap-2">
                                <i class="fa-solid fa-shield-cat text-pink-400"></i> Anti-Revoke Cert Shield
                            </div>
                            <div class="text-xs text-gray-400 mt-1">Chống văng app & thu hồi chứng chỉ IPA</div>
                        </div>
                        <label class="relative inline-flex items-center cursor-pointer" onclick="event.stopPropagation()">
                            <input type="checkbox" checked class="sr-only peer" onchange="playToggleSound(this)">
                            <div class="w-11 h-6 bg-gray-800 peer-focus:outline-none rounded-full peer peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all peer-checked:bg-cyber-magenta"></div>
                        </label>
                    </div>
                </div>
            </div>

            <!-- 3. INJECTOR TERMINAL & PROGRESS BAR -->
            <div class="card-cyber p-5 rounded-2xl border border-cyber-border font-mono text-xs space-y-4">
                <div class="flex items-center justify-between text-gray-400 border-b border-cyber-border/70 pb-3">
                    <span class="flex items-center gap-2 font-bold text-white">
                        <i class="fa-solid fa-terminal text-cyber-cyan"></i>
                        HUNGAIMLOCK INJECTOR CONSOLE v6.0
                    </span>
                    <span id="inject-status" class="text-cyber-yellow font-bold">READY TO INJECT</span>
                </div>

                <!-- Terminal Logs -->
                <div id="terminal-logs" class="h-32 overflow-y-auto space-y-1.5 text-gray-400 pr-2 bg-cyber-black/70 p-3 rounded-xl border border-cyber-border/50">
                    <p class="text-gray-500">[SYSTEM] Core System Ready.</p>
                    <p class="text-gray-500">[SYSTEM] VIP License Validated.</p>
                </div>

                <!-- Laser Progress Bar Container -->
                <div id="progress-container" class="hidden space-y-2">
                    <div class="flex justify-between text-xs font-bold">
                        <span class="text-cyber-cyan">INJECTION PROGRESS</span>
                        <span id="progress-percent" class="text-cyber-magenta">0%</span>
                    </div>
                    <div class="w-full bg-gray-900 rounded-full h-3 p-0.5 border border-cyber-border/80">
                        <div id="progress-bar" class="laser-bar h-full bg-gradient-to-r from-cyber-cyan via-blue-500 to-cyber-magenta rounded-full w-0 transition-all duration-300"></div>
                    </div>
                </div>

                <!-- Inject Button -->
                <div>
                    <button id="btn-inject" onclick="startInjection()" class="w-full py-4 rounded-xl font-black tracking-widest uppercase bg-gradient-to-r from-cyber-cyan via-blue-600 to-cyber-magenta hover:brightness-110 active:scale-[0.99] transition-all text-black flex items-center justify-center gap-2 shadow-lg glow-cyan text-sm">
                        <i class="fa-solid fa-bolt-lightning"></i>
                        KÍCH HOẠT MENU AIMLOCK
                    </button>
                </div>
            </div>
        </section>

        <!-- FOOTER -->
        <footer class="mt-8 pt-4 border-t border-cyber-border/50 flex flex-col sm:flex-row items-center justify-between text-xs text-gray-500 gap-2 font-mono">
            <div>
                © 2026 <span class="text-cyber-cyan font-bold">HungAimlock VIP Team</span>. All rights reserved.
            </div>
            <div class="flex gap-4">
                <span class="hover:text-cyber-cyan cursor-pointer"><i class="fa-solid fa-shield-halved"></i> Anti-Cheat Shield</span>
                <span class="hover:text-cyber-magenta cursor-pointer"><i class="fa-solid fa-microchip"></i> Engine v6.0</span>
            </div>
        </footer>
    </main>

    <!-- SUCCESS DIALOG MODAL -->
    <div id="success-modal" class="hidden fixed inset-0 z-50 bg-black/80 backdrop-blur-md flex items-center justify-center p-4">
        <div class="card-cyber w-full max-w-md p-6 sm:p-8 rounded-2xl border border-cyber-cyan glow-cyan text-center space-y-5 animate-bounce-short">
            <div class="w-16 h-16 mx-auto rounded-2xl bg-cyber-green/20 border border-cyber-green text-cyber-green flex items-center justify-center text-3xl">
                <i class="fa-solid fa-circle-check"></i>
            </div>
            <div>
                <h3 class="text-xl font-black text-white font-mono tracking-wide uppercase">THÀNH CÔNG!</h3>
                <p class="text-xs text-cyber-cyan font-mono mt-1 font-semibold">SUCCESSFULLY INJECTED INTO GAME MEMORY!</p>
            </div>
            <p class="text-xs text-gray-300 leading-relaxed font-sans">
                Các chức năng Aimlock đã được tiêm ngầm vào bộ nhớ Free Fire thành công. Hãy vào game và tận hưởng chiến thắng!
            </p>
            <button onclick="closeSuccessModal()" class="w-full py-3.5 rounded-xl font-bold bg-cyber-green text-black uppercase tracking-wider hover:brightness-110 transition-all font-mono">
                ĐỒNG Ý (VÀO GAME)
            </button>
        </div>
    </div>

    <!-- SCRIPT SECTION -->
    <script>
        /* 1. NATIVE WEB AUDIO SYNTH SOUND GENERATOR (No external library dependency) */
        const audioCtx = new (window.AudioContext || window.webkitAudioContext)();

        function playSound(freq, duration, type = 'sine') {
            try {
                if (audioCtx.state === 'suspended') {
                    audioCtx.resume();
                }
                const osc = audioCtx.createOscillator();
                const gain = audioCtx.createGain();
                osc.type = type;
                osc.frequency.setValueAtTime(freq, audioCtx.currentTime);
                gain.gain.setValueAtTime(0.1, audioCtx.currentTime);
                gain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + duration);
                osc.connect(gain);
                gain.connect(audioCtx.destination);
                osc.start();
                osc.stop(audioCtx.currentTime + duration);
            } catch(e){}
        }

        function playBeepSound(freq = 600) {
            playSound(freq, 0.08, 'sine');
        }

        function playErrorFx() {
            playSound(150, 0.12, 'sawtooth');
            setTimeout(() => playSound(100, 0.2, 'sawtooth'), 80);
        }

        function playSuccessFx() {
            playSound(523, 0.08, 'sine');
            setTimeout(() => playSound(659, 0.08, 'sine'), 70);
            setTimeout(() => playSound(783, 0.15, 'sine'), 140);
        }

        function playToggleSound(elem) {
            if (elem.checked) {
                playBeepSound(880);
            } else {
                playBeepSound(350);
            }
        }

        /* 2. SPARK TRAIL & LIGHT STREAK VISUAL EFFECTS */
        window.addEventListener('pointerdown', (e) => {
            createSparkTrail(e.clientX, e.clientY);
        });

        function createSparkTrail(x, y) {
            const spark = document.createElement('div');
            spark.className = 'spark-trail';
            spark.style.left = x + 'px';
            spark.style.top = y + 'px';
            document.body.appendChild(spark);
            setTimeout(() => spark.remove(), 500);
        }

        function triggerLightStreak(card) {
            playBeepSound(700);
            card.classList.remove('trigger-streak');
            void card.offsetWidth; // Force Reflow
            card.classList.add('trigger-streak');
        }

        /* 3. SECRET OBFUSCATED KEY AUTHENTICATION */
        // Key 1: "HungBaKhi"   -> Base64: "SHVuZ0JhS2hp"
        // Key 2: "KeyHungLock" -> Base64: "S2V5SHVuZ0xvY2s="
        const _keys = ["SHVuZ0JhS2hp", "S2V5SHVuZ0xvY2s="];

        function _verifyInput(str) {
            try {
                return _keys.includes(btoa(str.trim()));
            } catch(e) {
                return false;
            }
        }

        function validateKey() {
            const inputField = document.getElementById('key-input');
            const errorMsg = document.getElementById('auth-error-msg');

            if (_verifyInput(inputField.value)) {
                // Correct Key
                playSuccessFx();
                localStorage.setItem('hungaimlock_auth', 'TRUE');
                
                // Create Light Blast
                const blast = document.createElement('div');
                blast.className = 'light-blast';
                document.body.appendChild(blast);
                setTimeout(() => blast.remove(), 800);

                showDashboard();
            } else {
                // Incorrect Key
                playErrorFx();
                errorMsg.classList.remove('hidden');
                inputField.classList.remove('shake-error');
                void inputField.offsetWidth;
                inputField.classList.add('shake-error');
            }
        }

        function showDashboard() {
            document.getElementById('auth-section').classList.add('hidden');
            document.getElementById('dashboard-section').classList.remove('hidden');
            document.getElementById('os-selector-header').classList.remove('hidden');
            logTerminal("[AUTH] VIP License authenticated successfully.");
        }

        function lockSystem() {
            playBeepSound(400);
            localStorage.removeItem('hungaimlock_auth');
            document.getElementById('auth-section').classList.remove('hidden');
            document.getElementById('dashboard-section').classList.add('hidden');
            document.getElementById('os-selector-header').classList.add('hidden');
            document.getElementById('key-input').value = '';
            document.getElementById('auth-error-msg').classList.add('hidden');
        }

        function toggleKeyVisibility() {
            const input = document.getElementById('key-input');
            const icon = document.getElementById('eye-icon');
            if (input.type === 'password') {
                input.type = 'text';
                icon.className = 'fa-solid fa-eye-slash';
            } else {
                input.type = 'password';
                icon.className = 'fa-solid fa-eye';
            }
        }

        /* 4. OS SWITCHER */
        function switchOS(os) {
            playBeepSound(600);
            const btnAndroid = document.getElementById('btn-tab-android');
            const btnIos = document.getElementById('btn-tab-ios');
            const panelAndroid = document.getElementById('panel-android');
            const panelIos = document.getElementById('panel-ios');

            if (os === 'android') {
                btnAndroid.className = "flex items-center gap-2 px-5 py-2.5 rounded-lg text-xs font-bold transition-all bg-cyber-cyan/20 text-cyber-cyan border border-cyber-cyan/50 glow-cyan";
                btnIos.className = "flex items-center gap-2 px-5 py-2.5 rounded-lg text-xs font-bold transition-all text-gray-400 hover:text-white";
                panelAndroid.classList.remove('hidden');
                panelIos.classList.add('hidden');
                logTerminal("[OS] Switched to ANDROID (ADR) Mode");
            } else {
                btnIos.className = "flex items-center gap-2 px-5 py-2.5 rounded-lg text-xs font-bold transition-all bg-cyber-magenta/20 text-cyber-magenta border border-cyber-magenta/50 glow-magenta";
                btnAndroid.className = "flex items-center gap-2 px-5 py-2.5 rounded-lg text-xs font-bold transition-all text-gray-400 hover:text-white";
                panelIos.classList.remove('hidden');
                panelAndroid.classList.add('hidden');
                logTerminal("[OS] Switched to iOS (APPLE) Mode");
            }
        }

        /* 5. TERMINAL & INJECTION PROGRESS LOGIC */
        function logTerminal(text) {
            const container = document.getElementById('terminal-logs');
            const p = document.createElement('p');
            const time = new Date().toLocaleTimeString();
            p.innerHTML = `<span class="text-cyber-cyan">[${time}]</span> ${text}`;
            container.appendChild(p);
            container.scrollTop = container.scrollHeight;
        }

        let isInjecting = false;
        function startInjection() {
            if (isInjecting) return;
            isInjecting = true;
            
            playBeepSound(800);
            const btn = document.getElementById('btn-inject');
            const status = document.getElementById('inject-status');
            const progressContainer = document.getElementById('progress-container');
            const progressBar = document.getElementById('progress-bar');
            const progressPercent = document.getElementById('progress-percent');
            
            btn.disabled = true;
            btn.innerHTML = `<i class="fa-solid fa-spinner animate-spin"></i> ĐANG INJECT BỘ NHỚ GAME...`;
            status.innerText = "INJECTING...";
            status.className = "text-cyber-yellow animate-pulse font-bold";
            progressContainer.classList.remove('hidden');

            const steps = [
                { percent: 15, msg: "Injecting bypassed memory..." },
                { percent: 35, msg: "Overriding FF_AIM_AXIS offsets..." },
                { percent: 60, msg: "Bypassing Garena Anti-Cheat System..." },
                { percent: 85, msg: "Hooking Auto Aimlock & ESP offsets..." },
                { percent: 100, msg: "Done! Injection completed successfully." }
            ];

            let idx = 0;
            const interval = setInterval(() => {
                if (idx < steps.length) {
                    const step = steps[idx];
                    progressBar.style.width = step.percent + '%';
                    progressPercent.innerText = step.percent + '%';
                    logTerminal(step.msg);
                    playBeepSound(600 + step.percent * 4);
                    idx++;
                } else {
                    clearInterval(interval);
                    isInjecting = false;
                    btn.disabled = false;
                    btn.innerHTML = `<i class="fa-solid fa-circle-check"></i> ĐÃ TIÊM THÀNH CÔNG! (TIÊM LẠI)`;
                    status.innerText = "INJECTED";
                    status.className = "text-cyber-green font-bold";
                    playSuccessFx();

                    // Show success modal
                    setTimeout(() => {
                        document.getElementById('success-modal').classList.remove('hidden');
                    }, 400);
                }
            }, 700);
        }

        function closeSuccessModal() {
            playBeepSound(500);
            document.getElementById('success-modal').classList.add('hidden');
        }

        /* 6. CANVAS PARTICLES BACKGROUND ENGINE */
        const canvas = document.getElementById('bg-canvas');
        const ctx = canvas.getContext('2d');

        function resizeCanvas() {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        }
        window.addEventListener('resize', resizeCanvas);
        resizeCanvas();

        const particles = [];
        const numParticles = 45;

        for (let i = 0; i < numParticles; i++) {
            particles.push({
                x: Math.random() * canvas.width,
                y: Math.random() * canvas.height,
                radius: Math.random() * 2 + 0.5,
                color: Math.random() > 0.5 ? '#00f0ff' : '#ff007f',
                vx: (Math.random() - 0.5) * 0.6,
                vy: (Math.random() - 0.5) * 0.6
            });
        }

        function animateBg() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);

            for (let i = 0; i < particles.length; i++) {
                let p = particles[i];
                p.x += p.vx;
                p.y += p.vy;

                if (p.x < 0 || p.x > canvas.width) p.vx *= -1;
                if (p.y < 0 || p.y > canvas.height) p.vy *= -1;

                ctx.beginPath();
                ctx.arc(p.x, p.y, p.radius, 0, Math.PI * 2);
                ctx.fillStyle = p.color;
                ctx.globalAlpha = 0.6;
                ctx.shadowBlur = 8;
                ctx.shadowColor = p.color;
                ctx.fill();

                for (let j = i + 1; j < particles.length; j++) {
                    let p2 = particles[j];
                    let dist = Math.hypot(p.x - p2.x, p.y - p2.y);
                    if (dist < 120) {
                        ctx.beginPath();
                        ctx.moveTo(p.x, p.y);
                        ctx.lineTo(p2.x, p2.y);
                        ctx.strokeStyle = p.color;
                        ctx.globalAlpha = (1 - dist / 120) * 0.18;
                        ctx.lineWidth = 0.6;
                        ctx.stroke();
                    }
                }
            }
            requestAnimationFrame(animateBg);
        }

        /* AUTO LOGIN CHECK FROM LOCALSTORAGE */
        window.onload = function() {
            animateBg();
            if (localStorage.getItem('hungaimlock_auth') === 'TRUE') {
                showDashboard();
            }
        }
    </script>
</body>
</html>
```
