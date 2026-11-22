[modern_knowledge_school_year_3_maths_revision_hub.html](https://github.com/user-attachments/files/35244047/modern_knowledge_school_year_3_maths_revision_hub.html)
# Ms.safa3B
interactive games fun
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Modern Knowledge School — Year 3 Maths Revision Hub</title>
  <!-- Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- Google Fonts: Inter & Fredoka for kid-friendly headers -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Fredoka:wght@500;600;700&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
  <!-- Font Awesome for crisp educational icons -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
  <script>
    tailwind.config = {
      theme: {
        extend: {
          fontFamily: {
            sans: ['Inter', 'sans-serif'],
            display: ['Fredoka', 'sans-serif'],
          },
          colors: {
            mksNavy: '#0f294a',
            mksGold: '#f59e0b',
            mksTeal: '#0d9488',
            mksCoral: '#f43f5e',
            mksIndigo: '#4f46e5',
          }
        }
      }
    }
  </script>
  <style>
    body {
      background-color: #f4f7fb;
      color: #1e293b;
      -webkit-tap-highlight-color: transparent;
    }
    .font-display {
      font-family: 'Fredoka', sans-serif;
    }
    @keyframes popIn {
      0% { transform: scale(0.92); opacity: 0; }
      100% { transform: scale(1); opacity: 1; }
    }
    .animate-pop {
      animation: popIn 0.25s cubic-bezier(0.16, 1, 0.3, 1) forwards;
    }
    @keyframes bounceStar {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.3) rotate(12deg); }
    }
    .star-pulse {
      animation: bounceStar 0.5s ease-in-out;
    }
    /* Custom scrollbar for horizontal pill bars */
    .no-scrollbar::-webkit-scrollbar {
      display: none;
    }
    .no-scrollbar {
      -ms-overflow-style: none;
      scrollbar-width: none;
    }
    @media print {
      .no-print { display: none !important; }
      body { background: white; }
      .print-full { max-width: 100% !important; box-shadow: none !important; }
    }
  </style>
</head>
<body class="min-h-screen flex flex-col pb-24 md:pb-10">

  <!-- Top Sticky Header -->
  <header class="sticky top-0 z-40 bg-mksNavy text-white shadow-lg no-print">
    <div class="max-w-5xl mx-auto px-4 py-3 flex items-center justify-between gap-2">
      <div class="flex items-center gap-3">
        <div class="w-11 h-11 rounded-2xl bg-gradient-to-br from-amber-400 to-orange-500 flex items-center justify-center text-mksNavy font-display font-bold text-xl shadow-md shrink-0">
          MKS
        </div>
        <div>
          <h1 class="font-display font-bold text-base sm:text-xl leading-tight tracking-wide">
            Modern Knowledge School
          </h1>
          <p class="text-xs text-sky-200 font-medium">Year 3 A/B • Term 1 Maths Revision Hub</p>
        </div>
      </div>

      <!-- Star Points & Sound Toggle -->
      <div class="flex items-center gap-2 sm:gap-3">
        <button id="soundToggleBtn" onclick="toggleSound()" title="Toggle Sound Effects" class="w-10 h-10 rounded-xl bg-white/10 hover:bg-white/20 flex items-center justify-center text-sky-200 transition">
          <i id="soundIcon" class="fa-solid fa-volume-high"></i>
        </button>
        <div id="starBadge" class="flex items-center gap-2 bg-amber-500/20 border border-amber-400/40 px-3 py-1.5 rounded-2xl">
          <i class="fa-solid fa-star text-amber-400 text-base"></i>
          <span id="starCount" class="font-display font-bold text-amber-300 text-base sm:text-lg">0</span>
          <span class="hidden sm:inline text-xs text-amber-200 font-medium">Stars</span>
        </div>
      </div>
    </div>

    <!-- Desktop / Tablet Navigation Bar -->
    <nav class="hidden md:block bg-slate-900/40 border-t border-white/10">
      <div class="max-w-5xl mx-auto px-4 flex gap-2 py-2">
        <button onclick="switchTab('notes')" data-tab="notes" class="nav-btn flex-1 py-2.5 px-4 rounded-xl font-display font-semibold text-sm flex items-center justify-center gap-2 transition">
          <i class="fa-solid fa-book-open"></i> Revision Notes
        </button>
        <button onclick="switchTab('practice')" data-tab="practice" class="nav-btn flex-1 py-2.5 px-4 rounded-xl font-display font-semibold text-sm flex items-center justify-center gap-2 transition">
          <i class="fa-solid fa-circle-check"></i> Topic Practice
        </button>
        <button onclick="switchTab('papers')" data-tab="papers" class="nav-btn flex-1 py-2.5 px-4 rounded-xl font-display font-semibold text-sm flex items-center justify-center gap-2 transition">
          <i class="fa-solid fa-file-pen"></i> Past Paper Simulator
        </button>
        <button onclick="switchTab('reference')" data-tab="reference" class="nav-btn flex-1 py-2.5 px-4 rounded-xl font-display font-semibold text-sm flex items-center justify-center gap-2 transition">
          <i class="fa-solid fa-lightbulb"></i> Quick Reference
        </button>
      </div>
    </nav>
  </header>

  <!-- Main Content Container -->
  <main id="appContainer" class="flex-1 max-w-5xl w-full mx-auto px-4 pt-5 pb-8 print-full">
    <!-- Dynamic View Injected Here -->
  </main>

  <!-- Mobile Sticky Bottom Navigation Bar -->
  <nav class="md:hidden fixed bottom-0 inset-x-0 z-40 bg-white border-t border-slate-200 shadow-[0_-4px_16px_rgba(15,41,74,0.08)] px-2 py-1.5 no-print">
    <div class="grid grid-cols-4 gap-1">
      <button onclick="switchTab('notes')" data-tab="notes" class="mobile-nav-btn flex flex-col items-center justify-center py-2 px-1 rounded-xl text-xs font-semibold transition">
        <i class="fa-solid fa-book-open text-lg mb-0.5"></i>
        <span>Notes</span>
      </button>
      <button onclick="switchTab('practice')" data-tab="practice" class="mobile-nav-btn flex flex-col items-center justify-center py-2 px-1 rounded-xl text-xs font-semibold transition">
        <i class="fa-solid fa-circle-check text-lg mb-0.5"></i>
        <span>Practice</span>
      </button>
      <button onclick="switchTab('papers')" data-tab="papers" class="mobile-nav-btn flex flex-col items-center justify-center py-2 px-1 rounded-xl text-xs font-semibold transition">
        <i class="fa-solid fa-file-pen text-lg mb-0.5"></i>
        <span>Past Papers</span>
      </button>
      <button onclick="switchTab('reference')" data-tab="reference" class="mobile-nav-btn flex flex-col items-center justify-center py-2 px-1 rounded-xl text-xs font-semibold transition">
        <i class="fa-solid fa-lightbulb text-lg mb-0.5"></i>
        <span>Cheat Sheet</span>
      </button>
    </div>
  </nav>

  <!-- Toast / Message Box (Replaces alert()) -->
  <div id="toastBox" class="fixed top-20 left-1/2 -translate-x-1/2 z-50 hidden max-w-sm w-[92%] bg-slate-900 text-white px-4 py-3 rounded-2xl shadow-2xl border border-white/15 flex items-center gap-3 animate-pop">
    <span id="toastIcon" class="text-xl">🌟</span>
    <p id="toastText" class="text-sm font-medium leading-snug"></p>
  </div>

  <script>
    // =========================================================================
    // 1. STATE & AUDIO ENGINE (Web Audio API - zero external audio URLs)
    // =========================================================================
    const state = {
      activeTab: 'notes',
      activeTopicFilter: 'all',
      activeNotesTopic: 'time',
      stars: parseInt(localStorage.getItem('mks_y3_stars') || '0', 10),
      solvedQuestions: JSON.parse(localStorage.getItem('mks_y3_solved') || '{}'),
      soundEnabled: true,
      // Past Paper Simulator State
      activePaperId: null,
      paperAnswers: {},
      paperSubmitted: false,
      paperTimed: false,
      timerSeconds: 1800, // 30 minutes
      timerInterval: null,
      // Interactive Clock Demo State in Revision Notes
      demoHour: 4,
      demoMinute: 15,
      // Interactive Angle Checker State
      demoAngleDeg: 90
    };

    let audioCtx = null;
    function playTone(type) {
      if (!state.soundEnabled) return;
      try {
        if (!audioCtx) audioCtx = new (window.AudioContext || window.webkitAudioContext)();
        if (audioCtx.state === 'suspended') audioCtx.resume();
        const osc = audioCtx.createOscillator();
        const gain = audioCtx.createGain();
        osc.connect(gain);
        gain.connect(audioCtx.destination);
        const now = audioCtx.currentTime;

        if (type === 'correct') {
          osc.type = 'triangle';
          osc.frequency.setValueAtTime(523.25, now); // C5
          osc.frequency.setValueAtTime(659.25, now + 0.09); // E5
          osc.frequency.setValueAtTime(783.99, now + 0.18); // G5
          gain.gain.setValueAtTime(0.18, now);
          gain.gain.exponentialRampToValueAtTime(0.001, now + 0.42);
          osc.start(now);
          osc.stop(now + 0.42);
        } else if (type === 'wrong') {
          osc.type = 'sine';
          osc.frequency.setValueAtTime(240, now);
          osc.frequency.linearRampToValueAtTime(185, now + 0.25);
          gain.gain.setValueAtTime(0.14, now);
          gain.gain.exponentialRampToValueAtTime(0.001, now + 0.28);
          osc.start(now);
          osc.stop(now + 0.28);
        } else {
          osc.type = 'sine';
          osc.frequency.setValueAtTime(440, now);
          gain.gain.setValueAtTime(0.08, now);
          gain.gain.exponentialRampToValueAtTime(0.001, now + 0.1);
          osc.start(now);
          osc.stop(now + 0.1);
        }
      } catch (e) {
        // Ignore audio errors on restricted devices
      }
    }

    function toggleSound() {
      state.soundEnabled = !state.soundEnabled;
      const icon = document.getElementById('soundIcon');
      icon.className = state.soundEnabled ? 'fa-solid fa-volume-high' : 'fa-solid fa-volume-xmark text-rose-300';
      showToast(state.soundEnabled ? 'Sound effects turned ON' : 'Sound effects muted', state.soundEnabled ? '🔊' : '🔇');
    }

    function addStars(amount, qId) {
      if (qId && state.solvedQuestions[qId]) return; // Prevent farming same question
      if (qId) {
        state.solvedQuestions[qId] = true;
        localStorage.setItem('mks_y3_solved', JSON.stringify(state.solvedQuestions));
      }
      state.stars += amount;
      localStorage.setItem('mks_y3_stars', String(state.stars));
      const countEl = document.getElementById('starCount');
      const badgeEl = document.getElementById('starBadge');
      countEl.textContent = state.stars;
      badgeEl.classList.remove('star-pulse');
      void badgeEl.offsetWidth;
      badgeEl.classList.add('star-pulse');
    }

    let toastTimeout = null;
    function showToast(msg, icon = '🌟') {
      const box = document.getElementById('toastBox');
      document.getElementById('toastIcon').textContent = icon;
      document.getElementById('toastText').textContent = msg;
      box.classList.remove('hidden');
      clearTimeout(toastTimeout);
      toastTimeout = setTimeout(() => box.classList.add('hidden'), 2800);
    }

    // =========================================================================
    // 2. SVG ILLUSTRATION GENERATORS (All Worksheet Diagrams Built-In)
    // =========================================================================
    function renderAnalogClockSVG(hour, minute, size = 148) {
      const minuteAngle = minute * 6;
      const hourAngle = ((hour % 12) + minute / 60) * 30;
      let ticks = '';
      let numbers = '';

      for (let i = 0; i < 60; i++) {
        const angle = i * 6 * Math.PI / 180;
        const isMajor = i % 5 === 0;
        const r1 = isMajor ? 74 : 78;
        const r2 = 84;
        const x1 = 100 + r1 * Math.sin(angle);
        const y1 = 100 - r1 * Math.cos(angle);
        const x2 = 100 + r2 * Math.sin(angle);
        const y2 = 100 - r2 * Math.cos(angle);
        ticks += `<line x1="${x1.toFixed(1)}" y1="${y1.toFixed(1)}" x2="${x2.toFixed(1)}" y2="${y2.toFixed(1)}" stroke="${isMajor ? '#0f294a' : '#94a3b8'}" stroke-width="${isMajor ? 2.5 : 1.2}" />`;
      }

      for (let n = 1; n <= 12; n++) {
        const angle = n * 30 * Math.PI / 180;
        const x = 100 + 61 * Math.sin(angle);
        const y = 100 - 61 * Math.cos(angle);
        numbers += `<text x="${x.toFixed(1)}" y="${(y + 5).toFixed(1)}" text-anchor="middle" font-size="14" font-weight="700" fill="#0f294a" font-family="Fredoka, sans-serif">${n}</text>`;
      }

      return `
        <svg viewBox="0 0 200 200" width="${size}" height="${size}" class="mx-auto drop-shadow-sm select-none">
          <circle cx="100" cy="100" r="92" fill="#ffffff" stroke="#0f294a" stroke-width="6"/>
          <circle cx="100" cy="100" r="84" fill="#f8fafc" stroke="#cbd5e1" stroke-width="1"/>
          ${ticks}
          ${numbers}
          <!-- Hour hand (Short & Thick) -->
          <g transform="rotate(${hourAngle} 100 100)">
            <line x1="100" y1="106" x2="100" y2="54" stroke="#0f294a" stroke-width="6.5" stroke-linecap="round"/>
          </g>
          <!-- Minute hand (Long & Teal) -->
          <g transform="rotate(${minuteAngle} 100 100)">
            <line x1="100" y1="110" x2="100" y2="30" stroke="#0d9488" stroke-width="4" stroke-linecap="round"/>
          </g>
          <circle cx="100" cy="100" r="6" fill="#f59e0b" stroke="#0f294a" stroke-width="2"/>
        </svg>
      `;
    }

    function renderNumberLineSVG(labels, arcLabel) {
      const count = labels.length;
      const width = 340;
      const padding = 34;
      const step = (width - padding * 2) / (count - 1);
      let points = '';
      let arcs = '';

      labels.forEach((lbl, idx) => {
        const x = padding + idx * step;
        points += `
          <line x1="${x}" y1="54" x2="${x}" y2="70" stroke="#0f294a" stroke-width="3" stroke-linecap="round"/>
          <text x="${x}" y="88" text-anchor="middle" font-size="13" font-weight="700" fill="#0f294a" font-family="Inter, sans-serif">${lbl}</text>
        `;
        if (idx < count - 1) {
          const nextX = padding + (idx + 1) * step;
          const midX = (x + nextX) / 2;
          arcs += `
            <path d="M ${x} 52 Q ${midX} 20 ${nextX} 52" fill="none" stroke="#0d9488" stroke-width="2.5" stroke-dasharray="4 3"/>
            <text x="${midX}" y="26" text-anchor="middle" font-size="11" font-weight="700" fill="#0d9488">${arcLabel}</text>
          `;
        }
      });

      return `
        <svg viewBox="0 0 ${width} 100" class="w-full max-w-md mx-auto">
          <line x1="${padding - 10}" y1="62" x2="${width - padding + 10}" y2="62" stroke="#0f294a" stroke-width="3" stroke-linecap="round"/>
          ${arcs}
          ${points}
        </svg>
      `;
    }

    function renderShapeSVG(type) {
      const shapes = {
        square: `<svg viewBox="0 0 140 120" class="w-32 h-28 mx-auto"><rect x="30" y="20" width="80" height="80" fill="#e0f2fe" stroke="#0f294a" stroke-width="4"/></svg>`,
        rectangle: `<svg viewBox="0 0 160 120" class="w-36 h-28 mx-auto"><rect x="18" y="30" width="124" height="60" fill="#fef3c7" stroke="#0f294a" stroke-width="4"/></svg>`,
        triangle: `<svg viewBox="0 0 140 120" class="w-32 h-28 mx-auto"><polygon points="70,18 20,102 120,102" fill="#dcfce7" stroke="#0f294a" stroke-width="4" stroke-linejoin="round"/></svg>`,
        circle: `<svg viewBox="0 0 140 120" class="w-32 h-28 mx-auto"><circle cx="70" cy="60" r="42" fill="#ffe4e6" stroke="#0f294a" stroke-width="4"/></svg>`,
        pentagon_reg: `<svg viewBox="0 0 140 120" class="w-32 h-28 mx-auto"><polygon points="70,15 118,50 100,105 40,105 22,50" fill="#e0e7ff" stroke="#0f294a" stroke-width="4" stroke-linejoin="round"/></svg>`,
        pentagon_irreg: `<svg viewBox="0 0 140 120" class="w-32 h-28 mx-auto"><polygon points="35,20 112,30 122,82 70,108 18,75" fill="#fae8ff" stroke="#0f294a" stroke-width="4" stroke-linejoin="round"/></svg>`,
        octagon_reg: `<svg viewBox="0 0 140 120" class="w-32 h-28 mx-auto"><polygon points="52,16 88,16 114,42 114,78 88,104 52,104 26,78 26,42" fill="#ccfbf1" stroke="#0f294a" stroke-width="4" stroke-linejoin="round"/></svg>`,
        l_shape: `<svg viewBox="0 0 140 120" class="w-32 h-28 mx-auto"><polygon points="30,18 68,18 68,62 115,62 115,102 30,102" fill="#ffedd5" stroke="#0f294a" stroke-width="4" stroke-linejoin="round"/></svg>`,
        semicircle: `<svg viewBox="0 0 140 120" class="w-32 h-28 mx-auto"><path d="M 25 80 A 45 45 0 0 1 115 80 Z" fill="#fef9c3" stroke="#0f294a" stroke-width="4"/></svg>`,
        // 3D Pyramids & Prisms (Page 10-13)
        tri_pyramid: `<svg viewBox="0 0 160 130" class="w-36 h-32 mx-auto">
          <polygon points="80,15 28,95 95,112" fill="#cbd5e1" stroke="#0f294a" stroke-width="3"/>
          <polygon points="80,15 95,112 135,88" fill="#94a3b8" stroke="#0f294a" stroke-width="3"/>
          <line x1="28" y1="95" x2="135" y2="88" stroke="#0f294a" stroke-width="2" stroke-dasharray="4 3"/>
          <text x="122" y="22" font-size="11" font-weight="700" fill="#e11d48">vertex</text>
          <line x1="84" y1="16" x2="118" y2="18" stroke="#e11d48" stroke-width="1.5"/>
          <text x="115" y="122" font-size="11" font-weight="700" fill="#0d9488">base (3 sides)</text>
        </svg>`,
        rect_pyramid: `<svg viewBox="0 0 160 130" class="w-36 h-32 mx-auto">
          <polygon points="80,15 24,102 96,108" fill="#cbd5e1" stroke="#0f294a" stroke-width="3"/>
          <polygon points="80,15 96,108 136,86" fill="#94a3b8" stroke="#0f294a" stroke-width="3"/>
          <line x1="24" y1="102" x2="62" y2="82" stroke="#0f294a" stroke-width="2" stroke-dasharray="4 3"/>
          <line x1="62" y1="82" x2="136" y2="86" stroke="#0f294a" stroke-width="2" stroke-dasharray="4 3"/>
          <line x1="80" y1="15" x2="62" y2="82" stroke="#0f294a" stroke-width="2" stroke-dasharray="4 3"/>
          <text x="112" y="124" font-size="11" font-weight="700" fill="#0d9488">base (4 sides)</text>
        </svg>`,
        pent_pyramid: `<svg viewBox="0 0 160 130" class="w-36 h-32 mx-auto">
          <polygon points="80,14 25,84 52,110 108,110 135,84" fill="#cbd5e1" stroke="#0f294a" stroke-width="3"/>
          <line x1="80" y1="14" x2="52" y2="110" stroke="#0f294a" stroke-width="2.5"/>
          <line x1="80" y1="14" x2="108" y2="110" stroke="#0f294a" stroke-width="2.5"/>
          <line x1="25" y1="84" x2="80" y2="68" stroke="#0f294a" stroke-width="2" stroke-dasharray="4 3"/>
          <line x1="135" y1="84" x2="80" y2="68" stroke="#0f294a" stroke-width="2" stroke-dasharray="4 3"/>
          <line x1="80" y1="14" x2="80" y2="68" stroke="#0f294a" stroke-width="2" stroke-dasharray="4 3"/>
          <text x="112" y="125" font-size="11" font-weight="700" fill="#0d9488">base (5 sides)</text>
        </svg>`,
        hex_pyramid: `<svg viewBox="0 0 160 130" class="w-36 h-32 mx-auto">
          <polygon points="80,14 24,86 52,108 108,108 136,86" fill="#94a3b8" stroke="#0f294a" stroke-width="3"/>
          <line x1="80" y1="14" x2="52" y2="108" stroke="#0f294a" stroke-width="2.5"/>
          <line x1="80" y1="14" x2="108" y2="108" stroke="#0f294a" stroke-width="2.5"/>
          <line x1="24" y1="86" x2="52" y2="68" stroke="#0f294a" stroke-width="2" stroke-dasharray="4 3"/>
          <line x1="52" y1="68" x2="108" y2="68" stroke="#0f294a" stroke-width="2" stroke-dasharray="4 3"/>
          <line x1="108" y1="68" x2="136" y2="86" stroke="#0f294a" stroke-width="2" stroke-dasharray="4 3"/>
          <text x="112" y="125" font-size="11" font-weight="700" fill="#0d9488">base (6 sides)</text>
        </svg>`,
        tri_prism: `<svg viewBox="0 0 160 120" class="w-36 h-28 mx-auto">
          <polygon points="22,92 52,38 82,92" fill="#bae6fd" stroke="#0f294a" stroke-width="3"/>
          <polygon points="52,38 112,24 142,78 82,92" fill="#7dd3fc" stroke="#0f294a" stroke-width="3"/>
          <line x1="22" y1="92" x2="142" y2="78" stroke="#0f294a" stroke-width="2" stroke-dasharray="4 3"/>
          <text x="80" y="112" text-anchor="middle" font-size="11" font-weight="700" fill="#0369a1">Triangle ends</text>
        </svg>`,
        rect_prism: `<svg viewBox="0 0 160 120" class="w-36 h-28 mx-auto">
          <rect x="24" y="45" width="82" height="48" fill="#fde68a" stroke="#0f294a" stroke-width="3"/>
          <polygon points="24,45 54,24 136,24 106,45" fill="#fcd34d" stroke="#0f294a" stroke-width="3"/>
          <polygon points="106,45 136,24 136,72 106,93" fill="#fbbf24" stroke="#0f294a" stroke-width="3"/>
          <text x="80" y="112" text-anchor="middle" font-size="11" font-weight="700" fill="#b45309">Rectangle ends</text>
        </svg>`,
        pent_prism: `<svg viewBox="0 0 160 120" class="w-36 h-28 mx-auto">
          <polygon points="48,30 76,48 66,84 30,84 20,48" fill="#ddd6fe" stroke="#0f294a" stroke-width="3"/>
          <polygon points="48,30 98,18 126,36 76,48" fill="#c4b5fd" stroke="#0f294a" stroke-width="3"/>
          <polygon points="76,48 126,36 116,72 66,84" fill="#a78bfa" stroke="#0f294a" stroke-width="3"/>
          <text x="80" y="110" text-anchor="middle" font-size="11" font-weight="700" fill="#5b21b6">Pentagon ends (5)</text>
        </svg>`,
        hex_prism: `<svg viewBox="0 0 160 120" class="w-36 h-28 mx-auto">
          <polygon points="36,32 62,32 76,56 62,80 36,80 22,56" fill="#a7f3d0" stroke="#0f294a" stroke-width="3"/>
          <polygon points="62,32 108,20 122,44 76,56" fill="#6ee7b7" stroke="#0f294a" stroke-width="3"/>
          <polygon points="76,56 122,44 108,68 62,80" fill="#34d399" stroke="#0f294a" stroke-width="3"/>
          <text x="80" y="108" text-anchor="middle" font-size="11" font-weight="700" fill="#047857">Hexagon ends (6)</text>
        </svg>`,
        // Composite 3D Block Tower (Page 13)
        block_tower: `<svg viewBox="0 0 240 210" class="w-60 h-52 mx-auto bg-slate-50 rounded-2xl border border-slate-200 p-2">
          <!-- Bottom Left Cylinder (lying down) -->
          <ellipse cx="62" cy="172" rx="26" ry="22" fill="#94a3b8" stroke="#0f294a" stroke-width="2.5"/>
          <path d="M 45 155 L 78 140 A 26 22 0 0 1 85 182 L 62 194" fill="#cbd5e1" stroke="#0f294a" stroke-width="2.5"/>
          <ellipse cx="62" cy="172" rx="24" ry="20" fill="#64748b" stroke="#0f294a" stroke-width="2.5"/>
          <!-- Bottom Right Cube -->
          <rect x="125" y="142" width="46" height="46" fill="#93c5fd" stroke="#0f294a" stroke-width="2.5"/>
          <polygon points="125,142 142,130 188,130 171,142" fill="#bfdbfe" stroke="#0f294a" stroke-width="2.5"/>
          <polygon points="171,142 188,130 188,176 171,188" fill="#60a5fa" stroke="#0f294a" stroke-width="2.5"/>
          <!-- Middle Bridge Cuboid -->
          <rect x="34" y="122" width="102" height="22" fill="#fcd34d" stroke="#0f294a" stroke-width="2.5"/>
          <polygon points="34,122 50,112 152,112 136,122" fill="#fde68a" stroke="#0f294a" stroke-width="2.5"/>
          <polygon points="136,122 152,112 152,134 136,144" fill="#f59e0b" stroke="#0f294a" stroke-width="2.5"/>
          <!-- Top Left Tall Cylinder -->
          <rect x="44" y="46" width="32" height="70" fill="#e2e8f0" stroke="#0f294a" stroke-width="2.5"/>
          <ellipse cx="60" cy="46" rx="16" ry="6" fill="#f8fafc" stroke="#0f294a" stroke-width="2.5"/>
          <path d="M 44 116 A 16 6 0 0 0 76 116" fill="#e2e8f0" stroke="#0f294a" stroke-width="2.5"/>
          <!-- Right Middle Cylinder -->
          <rect x="138" y="80" width="44" height="54" fill="#99f6e4" stroke="#0f294a" stroke-width="2.5"/>
          <path d="M 138 134 A 22 7 0 0 0 182 134" fill="#99f6e4" stroke="#0f294a" stroke-width="2.5"/>
          <!-- Top Right Cone -->
          <polygon points="160,16 138,80 182,80" fill="#fda4af" stroke="#0f294a" stroke-width="2.5" stroke-linejoin="round"/>
          <path d="M 138 80 A 22 7 0 0 0 182 80" fill="#fda4af" stroke="#0f294a" stroke-width="2.5"/>
        </svg>`,
        // Symmetry Lines (Page 13-14)
        sym_heart_yes: `<svg viewBox="0 0 140 120" class="w-32 h-28 mx-auto">
          <path d="M70 100 C20 68 18 25 46 25 C60 25 70 38 70 38 C70 38 80 25 94 25 C122 25 120 68 70 100 Z" fill="#ffe4e6" stroke="#0f294a" stroke-width="3.5"/>
          <line x1="70" y1="10" x2="70" y2="112" stroke="#e11d48" stroke-width="3" stroke-dasharray="6 4"/>
        </svg>`,
        sym_pent_yes: `<svg viewBox="0 0 140 120" class="w-32 h-28 mx-auto">
          <polygon points="70,18 115,50 98,102 42,102 25,50" fill="#e0e7ff" stroke="#0f294a" stroke-width="3.5"/>
          <line x1="70" y1="8" x2="70" y2="112" stroke="#e11d48" stroke-width="3" stroke-dasharray="6 4"/>
        </svg>`,
        sym_star_no: `<svg viewBox="0 0 140 120" class="w-32 h-28 mx-auto">
          <polygon points="70,14 84,46 118,48 92,70 100,104 70,86 40,104 48,70 22,48 56,46" fill="#fef3c7" stroke="#0f294a" stroke-width="3.5"/>
          <line x1="12" y1="68" x2="128" y2="68" stroke="#e11d48" stroke-width="3" stroke-dasharray="6 4"/>
        </svg>`,
        sym_diamond_yes: `<svg viewBox="0 0 140 120" class="w-32 h-28 mx-auto">
          <polygon points="70,16 114,60 70,104 26,60" fill="#ccfbf1" stroke="#0f294a" stroke-width="3.5"/>
          <line x1="12" y1="60" x2="128" y2="60" stroke="#e11d48" stroke-width="3" stroke-dasharray="6 4"/>
        </svg>`,
        sym_l_no: `<svg viewBox="0 0 140 120" class="w-32 h-28 mx-auto">
          <polygon points="32,18 68,18 68,60 112,60 112,100 32,100" fill="#ffedd5" stroke="#0f294a" stroke-width="3.5"/>
          <line x1="68" y1="8" x2="68" y2="112" stroke="#e11d48" stroke-width="3" stroke-dasharray="6 4"/>
        </svg>`,
        sym_sun_yes: `<svg viewBox="0 0 140 120" class="w-32 h-28 mx-auto">
          <circle cx="70" cy="60" r="24" fill="#fde047" stroke="#0f294a" stroke-width="3"/>
          <polygon points="70,14 63,30 77,30" fill="#fbbf24" stroke="#0f294a" stroke-width="2.5"/>
          <polygon points="70,106 63,90 77,90" fill="#fbbf24" stroke="#0f294a" stroke-width="2.5"/>
          <polygon points="24,60 40,53 40,67" fill="#fbbf24" stroke="#0f294a" stroke-width="2.5"/>
          <polygon points="116,60 100,53 100,67" fill="#fbbf24" stroke="#0f294a" stroke-width="2.5"/>
          <line x1="70" y1="6" x2="70" y2="114" stroke="#e11d48" stroke-width="3" stroke-dasharray="6 4"/>
        </svg>`,
        sym_right_tri_no: `<svg viewBox="0 0 140 120" class="w-32 h-28 mx-auto">
          <polygon points="34,18 34,100 112,100" fill="#dbeafe" stroke="#0f294a" stroke-width="3.5"/>
          <line x1="16" y1="58" x2="124" y2="58" stroke="#e11d48" stroke-width="3" stroke-dasharray="6 4"/>
        </svg>`,
        // Reflections (Page 15-16)
        reflect_trap_choice: `<svg viewBox="0 0 240 110" class="w-60 h-28 mx-auto bg-white rounded-xl border border-slate-200">
          <!-- Left original trapezoid touching mirror line at bottom-right -->
          <polygon points="45,25 85,25 115,90 25,90" fill="#bae6fd" stroke="#0f294a" stroke-width="3"/>
          <!-- Mirror Line -->
          <line x1="120" y1="10" x2="120" y2="102" stroke="#e11d48" stroke-width="3.5"/>
          <text x="120" y="9" text-anchor="middle" font-size="9" font-weight="700" fill="#e11d48">MIRROR</text>
          <!-- Correct Mirrored Trapezoid on Right -->
          <polygon points="155,25 195,25 215,90 125,90" fill="#fef08a" stroke="#0d9488" stroke-width="3" stroke-dasharray="5 3"/>
        </svg>`,
        reflect_parallelogram: `<svg viewBox="0 0 240 115" class="w-60 h-28 mx-auto bg-white rounded-xl border border-slate-200">
          <!-- Original slanted parallelogram on left -->
          <polygon points="52,25 116,25 96,92 32,92" fill="#ddd6fe" stroke="#0f294a" stroke-width="3"/>
          <line x1="120" y1="10" x2="120" y2="105" stroke="#e11d48" stroke-width="3.5"/>
          <text x="120" y="9" text-anchor="middle" font-size="9" font-weight="700" fill="#e11d48">MIRROR</text>
          <text x="178" y="62" text-anchor="middle" font-size="13" font-weight="700" fill="#64748b">?</text>
        </svg>`,
        // Angles (Page 16-18)
        angle_right: `<svg viewBox="0 0 150 115" class="w-36 h-28 mx-auto">
          <polyline points="42,22 42,92 115,92" fill="none" stroke="#0f294a" stroke-width="4" stroke-linecap="round"/>
          <polyline points="42,74 60,74 60,92" fill="none" stroke="#e11d48" stroke-width="2.5"/>
        </svg>`,
        angle_acute: `<svg viewBox="0 0 150 115" class="w-36 h-28 mx-auto">
          <polyline points="112,32 34,90 122,90" fill="none" stroke="#0f294a" stroke-width="4" stroke-linecap="round"/>
          <path d="M 62 90 A 28 28 0 0 0 56 73" fill="none" stroke="#0d9488" stroke-width="3"/>
        </svg>`,
        angle_obtuse: `<svg viewBox="0 0 150 115" class="w-36 h-28 mx-auto">
          <polyline points="24,26 52,90 126,90" fill="none" stroke="#0f294a" stroke-width="4" stroke-linecap="round"/>
          <path d="M 78 90 A 26 26 0 0 0 41 66" fill="none" stroke="#f59e0b" stroke-width="3"/>
        </svg>`,
        // Compass Squirrel Diagram (Page 19)
        compass_squirrel: `<svg viewBox="0 0 260 220" class="w-64 h-56 mx-auto bg-emerald-50/60 rounded-2xl border border-emerald-200">
          <!-- Crosshair lines -->
          <line x1="130" y1="48" x2="130" y2="172" stroke="#0f294a" stroke-width="3" stroke-linecap="round"/>
          <polygon points="130,42 124,54 136,54" fill="#0f294a"/>
          <line x1="65" y1="110" x2="195" y2="110" stroke="#0f294a" stroke-width="3" stroke-linecap="round"/>
          <!-- Labels N, S, E, W -->
          <circle cx="146" cy="56" r="11" fill="#0f294a"/><text x="146" y="60" text-anchor="middle" font-size="12" font-weight="700" fill="#fff">N</text>
          <circle cx="146" cy="164" r="11" fill="#64748b"/><text x="146" y="168" text-anchor="middle" font-size="12" font-weight="700" fill="#fff">S</text>
          <circle cx="186" cy="94" r="11" fill="#64748b"/><text x="186" y="98" text-anchor="middle" font-size="12" font-weight="700" fill="#fff">E</text>
          <circle cx="74" cy="94" r="11" fill="#64748b"/><text x="74" y="98" text-anchor="middle" font-size="12" font-weight="700" fill="#fff">W</text>
          <!-- Center Squirrel Emoji/Badge -->
          <circle cx="130" cy="110" r="24" fill="#fef3c7" stroke="#f59e0b" stroke-width="3"/>
          <text x="130" y="119" text-anchor="middle" font-size="26">🐿️</text>
          <!-- North: Apple -->
          <text x="130" y="32" text-anchor="middle" font-size="26">🍎</text>
          <!-- South: Acorn/Nut -->
          <text x="130" y="204" text-anchor="middle" font-size="26">🌰</text>
          <!-- East: Carrot -->
          <text x="225" y="119" text-anchor="middle" font-size="26">🥕</text>
          <!-- West: Strawberry -->
          <text x="35" y="119" text-anchor="middle" font-size="26">🍓</text>
        </svg>`
      };
      return shapes[type] || '';
    }

    // =========================================================================
    // 3. QUESTION BANK (Directly mapped from MKS Year 3 A/B PDF + Past Papers)
    // =========================================================================
    const practiceQuestions = [
      // --- TOPIC 1: TIME ---
      {
        id: 't1',
        topic: 'time',
        subtopic: 'Suitable Units of Time',
        prompt: 'Mr Lee sprints 100 m in a race. Which is the most suitable unit of time?',
        options: ['Seconds', 'Hours', 'Days'],
        answer: 'Seconds',
        hint: 'Running 100 m is very fast—less than a minute!',
        explanation: 'A 100 m sprint takes about 10 to 20 seconds, so Seconds is the best unit.'
      },
      {
        id: 't2',
        topic: 'time',
        subtopic: 'Suitable Units of Time',
        prompt: 'A baby grows into an adult. Which unit of time best measures this?',
        options: ['Days', 'Weeks', 'Years'],
        answer: 'Years',
        hint: 'Think about how old adults are (18 or 20+).',
        explanation: 'Growing from a baby into an adult takes many years.'
      },
      {
        id: 't3',
        topic: 'time',
        subtopic: 'Suitable Units of Time',
        prompt: 'Jerry eats an apple during break time. Which unit of time is best?',
        options: ['Seconds', 'Minutes', 'Hours'],
        answer: 'Minutes',
        hint: 'It takes longer than a few claps, but much less than a movie.',
        explanation: 'Eating an apple takes a few minutes.'
      },
      {
        id: 't4',
        topic: 'time',
        subtopic: 'Suitable Units of Time',
        prompt: 'Claire watches a full movie at the cinema. Which unit of time is best?',
        options: ['Days', 'Hours', 'Seconds'],
        answer: 'Hours',
        hint: 'Most movies are around 90 to 120 minutes long.',
        explanation: 'Watching a movie usually takes about 2 hours.'
      },
      {
        id: 't5',
        topic: 'time',
        subtopic: 'Suitable Units of Time',
        prompt: 'An egg hatches into a chick (takes about 21 days). Which unit of time fits best?',
        options: ['Weeks', 'Minutes', 'Hours'],
        answer: 'Weeks',
        hint: '21 days is equal to 3 _____!',
        explanation: '21 days is 3 weeks, so Weeks is the most suitable unit.'
      },
      {
        id: 't6',
        topic: 'time',
        subtopic: 'Suitable Units of Time',
        prompt: 'Thomas claps his hands two times. Which unit of time is best?',
        options: ['Minutes', 'Seconds', 'Hours'],
        answer: 'Seconds',
        hint: 'Clapping twice happens almost right away!',
        explanation: 'Clapping twice takes only 1 or 2 seconds.'
      },
      {
        id: 't7',
        topic: 'time',
        subtopic: 'Read & Write Time',
        prompt: 'Look at the clock. What time does it show?',
        visual: () => renderAnalogClockSVG(4, 15, 145),
        options: ['4:15 (15 minutes past 4)', '3:20 (20 minutes past 3)', '4:03 (3 minutes past 4)'],
        answer: '4:15 (15 minutes past 4)',
        hint: 'The short hour hand is just past 4, and the long minute hand is on 3 (3 × 5 = 15).',
        explanation: 'The minute hand on 3 means 15 minutes past the hour. The time is 4:15.'
      },
      {
        id: 't8',
        topic: 'time',
        subtopic: 'Read & Write Time',
        prompt: 'Read the analog clock carefully. What is the time?',
        visual: () => renderAnalogClockSVG(4, 45, 145),
        options: ['4:45 (15 minutes to 5)', '5:45 (15 minutes to 6)', '9:25 (25 minutes past 9)'],
        answer: '4:45 (15 minutes to 5)',
        hint: 'The hour hand is between 4 and 5 (not at 5 yet!). The minute hand is on 9 (45 minutes).',
        explanation: 'It is 45 minutes past 4, which is 4:45 or 15 minutes to 5.'
      },
      {
        id: 't9',
        topic: 'time',
        subtopic: 'Read & Write Time',
        prompt: 'Watch out for the worksheet trap! What time is shown on this clock?',
        visual: () => renderAnalogClockSVG(7, 0, 145),
        options: ['7:00 (7 o\'clock)', '7:12', '12:07'],
        answer: '7:00 (7 o\'clock)',
        hint: 'When the long minute hand points straight up at 12, it is o\'clock (:00), NOT :12!',
        explanation: 'The short hand is on 7 and the long hand is on 12, so it is 7:00 (7 o\'clock).'
      },
      {
        id: 't10',
        topic: 'time',
        subtopic: 'Find Time Intervals',
        prompt: 'Sam started cleaning his room at 8:00 and finished at 11:00. How long did he take?',
        visual: () => renderNumberLineSVG(['8:00', '9:00', '10:00', '11:00'], '+1 hr'),
        options: ['2 hours', '3 hours', '4 hours'],
        answer: '3 hours',
        hint: 'Count the jumps on the number line from 8:00 to 11:00.',
        explanation: 'From 8:00 to 9:00 (1 hr), 9:00 to 10:00 (2 hrs), 10:00 to 11:00 (3 hrs). Sam took 3 hours.'
      },
      {
        id: 't11',
        topic: 'time',
        subtopic: 'Find Time Intervals',
        prompt: 'A school trip started at 1:30 and ended 5 hours later. When did the school trip end?',
        visual: () => renderNumberLineSVG(['1:30', '2:30', '3:30', '4:30', '5:30', '6:30'], '+1 hr'),
        options: ['5:30', '6:00', '6:30'],
        answer: '6:30',
        hint: 'Add 5 hours to 1:30 (1 + 5 = 6). Keep the :30 minutes!',
        explanation: '1:30 + 5 hours = 6:30.'
      },
      {
        id: 't12',
        topic: 'time',
        subtopic: 'Use Timetables',
        prompt: 'Restaurant Timetable: Mon–Wed (8:30–3:00 & 6:00–10:00), Thu (CLOSED), Fri–Sun (8:30–3:00 & 5:00–11:00). Elijah arrives at 5:00 on Tuesday. How long must he wait?',
        options: ['1 hour', '2 hours', '30 minutes'],
        answer: '1 hour',
        hint: 'On Tuesday evening, the restaurant opens at 6:00.',
        explanation: 'From 5:00 to 6:00 is 1 hour.'
      },

      // --- TOPIC 2: 2D & 3D SHAPES ---
      {
        id: 's1',
        topic: 'shapes',
        subtopic: 'Classify 2D Shapes',
        prompt: 'Is a circle a polygon?',
        visual: () => renderShapeSVG('circle'),
        options: ['Yes', 'No'],
        answer: 'No',
        hint: 'A polygon must have ONLY straight sides.',
        explanation: 'No! A circle has a curved edge, so it is NOT a polygon.'
      },
      {
        id: 's2',
        topic: 'shapes',
        subtopic: 'Classify 2D Shapes',
        prompt: 'Is this 5-sided pentagon a polygon?',
        visual: () => renderShapeSVG('pentagon_reg'),
        options: ['Yes', 'No'],
        answer: 'Yes',
        hint: 'Check if all sides are straight and the shape is completely closed.',
        explanation: 'Yes! It is a closed 2D shape made of 5 straight sides.'
      },
      {
        id: 's3',
        topic: 'shapes',
        subtopic: 'Regular & Irregular Polygons',
        prompt: 'Is this L-shaped polygon a REGULAR polygon?',
        visual: () => renderShapeSVG('l_shape'),
        options: ['Yes', 'No'],
        answer: 'No',
        hint: 'A regular polygon must have ALL sides equal in length and ALL angles equal.',
        explanation: 'No! Its sides have different lengths, so it is an irregular polygon.'
      },
      {
        id: 's4',
        topic: 'shapes',
        subtopic: 'Regular & Irregular Polygons',
        prompt: 'All 8 sides and all 8 angles of this octagon are equal. Is it a regular polygon?',
        visual: () => renderShapeSVG('octagon_reg'),
        options: ['Yes', 'No'],
        answer: 'Yes',
        hint: 'Equal sides + equal angles = regular!',
        explanation: 'Yes! Because all 8 sides and all 8 angles are equal, it is a regular octagon.'
      },
      {
        id: 's5',
        topic: 'shapes',
        subtopic: '3D Shapes (Pyramids & Prisms)',
        prompt: 'Identify this 3D pyramid by counting the sides of its base.',
        visual: () => renderShapeSVG('pent_pyramid'),
        options: ['Triangular pyramid', 'Pentagonal pyramid', 'Hexagonal pyramid'],
        answer: 'Pentagonal pyramid',
        hint: 'The base has 5 sides (a pentagon) and meets at 1 top vertex.',
        explanation: 'A pyramid with a 5-sided pentagon base is a pentagonal pyramid.'
      },
      {
        id: 's6',
        topic: 'shapes',
        subtopic: '3D Shapes (Pyramids & Prisms)',
        prompt: 'Identify this 3D prism.',
        visual: () => renderShapeSVG('tri_prism'),
        options: ['Triangular prism', 'Triangular pyramid', 'Rectangular prism'],
        answer: 'Triangular prism',
        hint: 'It has two matching triangle ends joined by rectangles.',
        explanation: 'It has a triangle base at both ends, so it is a triangular prism.'
      },
      {
        id: 's7',
        topic: 'shapes',
        subtopic: 'Recognise 3D Objects',
        prompt: 'Look at the 3D block tower. How many CYLINDERS are in the structure?',
        visual: () => renderShapeSVG('block_tower'),
        options: ['1', '2', '3'],
        answer: '3',
        hint: 'Count the round tubes: one lying at the bottom-left, one tall on the bridge, and one under the cone!',
        explanation: 'There are 3 cylinders in total (bottom-left, top-left, and middle-right under the cone).'
      },
      {
        id: 's8',
        topic: 'shapes',
        subtopic: 'Recognise 3D Objects',
        prompt: 'Look at the same 3D block tower. How many SPHERES are in the structure?',
        visual: () => renderShapeSVG('block_tower'),
        options: ['0', '1', '2'],
        answer: '0',
        hint: 'Are there any round balls in the tower?',
        explanation: 'There are 0 spheres in this block tower.'
      },

      // --- TOPIC 3: SYMMETRY & REFLECTIONS ---
      {
        id: 'sym1',
        topic: 'symmetry',
        subtopic: 'Lines of Symmetry',
        prompt: 'Is the red dashed line a valid line of symmetry for the star?',
        visual: () => renderShapeSVG('sym_star_no'),
        options: ['Yes', 'No'],
        answer: 'No',
        hint: 'If you fold along the dashed line, the top 1 point does not match the bottom 2 points!',
        explanation: 'No! The top half and bottom half do not match when folded along that horizontal line.'
      },
      {
        id: 'sym2',
        topic: 'symmetry',
        subtopic: 'Lines of Symmetry',
        prompt: 'Is the red dashed line a valid line of symmetry for the sun?',
        visual: () => renderShapeSVG('sym_sun_yes'),
        options: ['Yes', 'No'],
        answer: 'Yes',
        hint: 'Compare the left side and right side of the vertical dashed line.',
        explanation: 'Yes! Both halves are exact mirror images of each other.'
      },
      {
        id: 'sym3',
        topic: 'symmetry',
        subtopic: 'Lines of Symmetry',
        prompt: 'Is the red dashed line a line of symmetry for this L-shape?',
        visual: () => renderShapeSVG('sym_l_no'),
        options: ['Yes', 'No'],
        answer: 'No',
        hint: 'The left side is tall and the right side is short.',
        explanation: 'No! Folding along the dashed line will not make the two halves match.'
      },
      {
        id: 'sym4',
        topic: 'symmetry',
        subtopic: 'Reflections of 2D Shapes',
        prompt: 'Which statement describes a true mirror reflection across the red line?',
        visual: () => renderShapeSVG('reflect_parallelogram'),
        options: [
          'The reflected shape slants in the opposite direction, touching the mirror at the top-right corner',
          'The reflected shape slants in the exact same direction (a slide)',
          'The reflected shape is upside down at the bottom'
        ],
        answer: 'The reflected shape slants in the opposite direction, touching the mirror at the top-right corner',
        hint: 'In a mirror, every point stays the exact same distance from the mirror line on the opposite side.',
        explanation: 'A reflection flips the shape over the mirror line so the top corner still touches the mirror, and the bottom slants away to the right.'
      },

      // --- TOPIC 4: ANGLES, DIRECTIONS & POSITIONS ---
      {
        id: 'a1',
        topic: 'angles',
        subtopic: 'Compare Angles with a Right Angle',
        prompt: 'Compare this angle with a right angle (the corner of a folded paper).',
        visual: () => renderShapeSVG('angle_right'),
        options: ['Smaller than a right angle', 'Equal to a right angle', 'Greater than a right angle'],
        answer: 'Equal to a right angle',
        hint: 'Notice the square corner! It matches a folded paper corner perfectly.',
        explanation: 'This angle is equal to a right angle (90°).'
      },
      {
        id: 'a2',
        topic: 'angles',
        subtopic: 'Compare Angles with a Right Angle',
        prompt: 'Compare this closed, sharp angle with a right angle.',
        visual: () => renderShapeSVG('angle_acute'),
        options: ['Smaller than a right angle', 'Equal to a right angle', 'Greater than a right angle'],
        answer: 'Smaller than a right angle',
        hint: 'It is narrower than the corner of a square.',
        explanation: 'It opens less than a square corner, so it is smaller than a right angle.'
      },
      {
        id: 'a3',
        topic: 'angles',
        subtopic: 'Compare Angles with a Right Angle',
        prompt: 'Compare this wide-open angle with a right angle.',
        visual: () => renderShapeSVG('angle_obtuse'),
        options: ['Smaller than a right angle', 'Equal to a right angle', 'Greater than a right angle'],
        answer: 'Greater than a right angle',
        hint: 'It opens wider than the corner of a folded sheet of paper.',
        explanation: 'It opens wider than a right angle, so it is greater than a right angle.'
      },
      {
        id: 'a4',
        topic: 'angles',
        subtopic: 'Positions & Directions (Compass)',
        prompt: 'Look at the squirrel compass map. The carrot is _____ of the squirrel.',
        visual: () => renderShapeSVG('compass_squirrel'),
        options: ['North', 'South', 'East', 'West'],
        answer: 'East',
        hint: 'Look at the letter E pointing to the right.',
        explanation: 'The carrot is on the right side (E), which is East of the squirrel.'
      },
      {
        id: 'a5',
        topic: 'angles',
        subtopic: 'Positions & Directions (Compass)',
        prompt: 'Using the same map, the strawberry is _____ of the squirrel.',
        visual: () => renderShapeSVG('compass_squirrel'),
        options: ['North', 'South', 'East', 'West'],
        answer: 'West',
        hint: 'Look at the letter W pointing to the left.',
        explanation: 'The strawberry is on the left side (W), which is West of the squirrel.'
      },
      {
        id: 'a6',
        topic: 'angles',
        subtopic: 'Positions & Directions (Compass)',
        prompt: 'Using the same map, the nut (acorn) is _____ of the squirrel.',
        visual: () => renderShapeSVG('compass_squirrel'),
        options: ['North', 'South', 'East', 'West'],
        answer: 'South',
        hint: 'Look at the letter S pointing straight down.',
        explanation: 'The nut is below the squirrel (S), which is South.'
      }
    ];

    // =========================================================================
    // 4. PAST PAPERS DATA (2 Full Auto-Grading Mock Exams)
    // =========================================================================
    const pastPapers = {
      paperA: {
        id: 'paperA',
        title: 'Past Paper A: MKS Final-Term 1 Enrichment Exam',
        subtitle: 'Official Worksheet Style • 12 Questions • All 4 Units',
        durationMinutes: 25,
        questions: [
          {
            id: 'pa1',
            topic: 'Time',
            prompt: '1. Kieran irons his school shirt. Which is the most suitable unit of time?',
            options: ['Minutes', 'Days', 'Hours'],
            answer: 'Minutes',
            explanation: 'Ironing one shirt takes around 5 to 10 minutes.'
          },
          {
            id: 'pa2',
            topic: 'Time',
            prompt: '2. Summer starts and ends. Which unit of time best measures a season?',
            options: ['Days', 'Months', 'Hours'],
            answer: 'Months',
            explanation: 'A season like Summer lasts about 3 months.'
          },
          {
            id: 'pa3',
            topic: 'Time',
            prompt: '3. Read the clock and choose the matching time.',
            visual: () => renderAnalogClockSVG(10, 30, 130),
            options: ['10:30 (30 minutes past 10)', '6:50 (10 minutes to 7)', '11:30 (30 minutes past 11)'],
            answer: '10:30 (30 minutes past 10)',
            explanation: 'The short hour hand is halfway between 10 and 11, and the minute hand is on 6 (:30).'
          },
          {
            id: 'pa4',
            topic: 'Time',
            prompt: '4. The football World Cup happens once every 4 years. There was a World Cup in 2022. When is the next World Cup?',
            visual: () => renderNumberLineSVG(['2022', '2023', '2024', '2025', '2026'], '+1 yr'),
            options: ['2024', '2025', '2026'],
            answer: '2026',
            explanation: '2022 + 4 years = 2026.'
          },
          {
            id: 'pa5',
            topic: 'Time',
            prompt: '5. Restaurant Timetable: Mon–Wed (8:30–3:00 & 6:00–10:00), Thu (CLOSED), Fri–Sun (8:30–3:00 & 5:00–11:00). Zoey wants to have dinner at the restaurant. Which day should she NOT visit?',
            options: ['Wednesday', 'Thursday', 'Sunday'],
            answer: 'Thursday',
            explanation: 'The timetable shows the restaurant is CLOSED all day on Thursday.'
          },
          {
            id: 'pa6',
            topic: '2D & 3D Shapes',
            prompt: '6. Look at this shape. Is it a polygon?',
            visual: () => renderShapeSVG('semicircle'),
            options: ['Yes', 'No'],
            answer: 'No',
            explanation: 'No, because a semicircle has a curved side. Polygons only have straight sides.'
          },
          {
            id: 'pa7',
            topic: '2D & 3D Shapes',
            prompt: '7. Is this pentagon a REGULAR polygon?',
            visual: () => renderShapeSVG('pentagon_irreg'),
            options: ['Yes', 'No'],
            answer: 'No',
            explanation: 'No, its sides are not equal in length, so it is irregular.'
          },
          {
            id: 'pa8',
            topic: '2D & 3D Shapes',
            prompt: '8. Fill in the blank: A hexagonal prism has a _______ base.',
            visual: () => renderShapeSVG('hex_prism'),
            options: ['triangular', 'pentagonal', 'hexagonal'],
            answer: 'hexagonal',
            explanation: 'A hexagonal prism gets its name from its 6-sided hexagonal base.'
          },
          {
            id: 'pa9',
            topic: '2D & 3D Shapes',
            prompt: '9. Count the number of CONES in this 3D structure.',
            visual: () => renderShapeSVG('block_tower'),
            options: ['0', '1', '2'],
            answer: '1',
            explanation: 'There is 1 cone on the very top right of the tower.'
          },
          {
            id: 'pa10',
            topic: 'Symmetry & Reflections',
            prompt: '10. Is the dashed line a line of symmetry for this heart?',
            visual: () => renderShapeSVG('sym_heart_yes'),
            options: ['Yes', 'No'],
            answer: 'Yes',
            explanation: 'Yes, folding along the vertical dashed line matches both halves perfectly.'
          },
          {
            id: 'pa11',
            topic: 'Angles & Directions',
            prompt: '11. Compare this angle with a right angle.',
            visual: () => renderShapeSVG('angle_obtuse'),
            options: ['Smaller than a right angle', 'Equal to a right angle', 'Greater than a right angle'],
            answer: 'Greater than a right angle',
            explanation: 'It is wider than 90°, so it is greater than a right angle.'
          },
          {
            id: 'pa12',
            topic: 'Angles & Directions',
            prompt: '12. Look at the squirrel compass diagram. The apple is _____ of the squirrel.',
            visual: () => renderShapeSVG('compass_squirrel'),
            options: ['North', 'South', 'East', 'West'],
            answer: 'North',
            explanation: 'The apple is straight above the squirrel in the North (N) direction.'
          }
        ]
      },
      paperB: {
        id: 'paperB',
        title: 'Past Paper B: Term 1 Challenge Mock Exam',
        subtitle: 'Extra Exam Practice • 10 Questions • Time, Shapes, Symmetry & Compass',
        durationMinutes: 20,
        questions: [
          {
            id: 'pb1',
            topic: 'Time',
            prompt: '1. A plane flies from Singapore to Bangkok. Which is the best unit of time?',
            options: ['Seconds', 'Hours', 'Weeks'],
            answer: 'Hours',
            explanation: 'An international flight between countries takes about 2 to 3 hours.'
          },
          {
            id: 'pb2',
            topic: 'Time',
            prompt: '2. Read the clock. What time is it?',
            visual: () => renderAnalogClockSVG(11, 15, 130),
            options: ['11:15 (15 minutes past 11)', '3:55 (5 minutes to 4)', '11:03'],
            answer: '11:15 (15 minutes past 11)',
            explanation: 'The hour hand is just past 11 and the minute hand is on 3 (15 minutes).'
          },
          {
            id: 'pb3',
            topic: 'Time',
            prompt: '3. On Sunday, the restaurant opens 8:30–3:00 in the afternoon and 5:00–11:00 at night. For how many hours is it closed in the afternoon?',
            options: ['1 hour', '2 hours', '3 hours'],
            answer: '2 hours',
            explanation: 'From 3:00 in the afternoon to 5:00 in the evening is 2 hours.'
          },
          {
            id: 'pb4',
            topic: '2D & 3D Shapes',
            prompt: '4. Which 3D shape is shown below?',
            visual: () => renderShapeSVG('rect_pyramid'),
            options: ['Triangular pyramid', 'Rectangular pyramid', 'Rectangular prism'],
            answer: 'Rectangular pyramid',
            explanation: 'It has a 4-sided rectangular base and triangular faces meeting at one top vertex.'
          },
          {
            id: 'pb5',
            topic: '2D & 3D Shapes',
            prompt: '5. How many CUBES and CUBOIDS together are in the 3D tower?',
            visual: () => renderShapeSVG('block_tower'),
            options: ['1', '2', '3'],
            answer: '2',
            explanation: 'There is 1 cube (bottom right) and 1 cuboid (the middle horizontal bridge) = 2 in total.'
          },
          {
            id: 'pb6',
            topic: 'Symmetry & Reflections',
            prompt: '6. Is the dashed horizontal line a line of symmetry for this right-angled triangle?',
            visual: () => renderShapeSVG('sym_right_tri_no'),
            options: ['Yes', 'No'],
            answer: 'No',
            explanation: 'No, the top piece is a small triangle while the bottom piece is a wide trapezoid.'
          },
          {
            id: 'pb7',
            topic: 'Symmetry & Reflections',
            prompt: '7. Does this diamond (rhombus) show a true horizontal line of symmetry?',
            visual: () => renderShapeSVG('sym_diamond_yes'),
            options: ['Yes', 'No'],
            answer: 'Yes',
            explanation: 'Yes! Folding top-to-bottom matches both triangles identically.'
          },
          {
            id: 'pb8',
            topic: 'Angles & Directions',
            prompt: '8. Compare this angle with a right angle.',
            visual: () => renderShapeSVG('angle_acute'),
            options: ['Smaller than a right angle', 'Equal to a right angle', 'Greater than a right angle'],
            answer: 'Smaller than a right angle',
            explanation: 'This sharp angle is smaller than a right angle.'
          },
          {
            id: 'pb9',
            topic: 'Angles & Directions',
            prompt: '9. The squirrel walks North to eat the apple, then turns around and walks straight South past its starting spot to the nut. How many compass steps South did it walk?',
            visual: () => renderShapeSVG('compass_squirrel'),
            options: ['1 step', '2 steps', '3 steps'],
            answer: '2 steps',
            explanation: '1 step South returns to the center, and 1 more step South reaches the nut (2 steps).'
          },
          {
            id: 'pb10',
            topic: '2D & 3D Shapes',
            prompt: '10. Which property is TRUE for every regular polygon?',
            options: [
              'All sides are equal and all angles are equal',
              'It has at least one curved side',
              'It has a vertex at the top like a pyramid'
            ],
            answer: 'All sides are equal and all angles are equal',
            explanation: 'Regular polygons are 2D closed straight-sided shapes where every side and angle is equal.'
          }
        ]
      }
    };

    // =========================================================================
    // 5. NAVIGATION & VIEW CONTROLLERS
    // =========================================================================
    function switchTab(tab) {
      state.activeTab = tab;
      if (tab !== 'papers') {
        clearInterval(state.timerInterval);
      }
      updateNavUI();
      renderCurrentTab();
      window.scrollTo({ top: 0, behavior: 'smooth' });
    }

    function updateNavUI() {
      // Desktop nav buttons
      document.querySelectorAll('.nav-btn').forEach(btn => {
        const isActive = btn.dataset.tab === state.activeTab;
        btn.className = isActive
          ? 'nav-btn flex-1 py-2.5 px-4 rounded-xl font-display font-semibold text-sm flex items-center justify-center gap-2 transition bg-amber-400 text-mksNavy shadow-md'
          : 'nav-btn flex-1 py-2.5 px-4 rounded-xl font-display font-semibold text-sm flex items-center justify-center gap-2 transition text-white/85 hover:bg-white/10';
      });
      // Mobile bottom nav buttons
      document.querySelectorAll('.mobile-nav-btn').forEach(btn => {
        const isActive = btn.dataset.tab === state.activeTab;
        btn.className = isActive
          ? 'mobile-nav-btn flex flex-col items-center justify-center py-2 px-1 rounded-xl text-xs font-bold transition bg-indigo-50 text-mksIndigo'
          : 'mobile-nav-btn flex flex-col items-center justify-center py-2 px-1 rounded-xl text-xs font-medium transition text-slate-500 hover:text-slate-800';
      });
    }

    function renderCurrentTab() {
      const container = document.getElementById('appContainer');
      if (state.activeTab === 'notes') {
        container.innerHTML = renderNotesView();
      } else if (state.activeTab === 'practice') {
        container.innerHTML = renderPracticeView();
      } else if (state.activeTab === 'papers') {
        container.innerHTML = renderPastPapersView();
      } else if (state.activeTab === 'reference') {
        container.innerHTML = renderReferenceView();
      }
    }

    // =========================================================================
    // 6. VIEW 1: REVISION NOTES (Interactive Study Cards + Live Simulators)
    // =========================================================================
    function setNotesTopic(topic) {
      playTone('click');
      state.activeNotesTopic = topic;
      renderCurrentTab();
    }

    function updateDemoClock(h, m) {
      playTone('click');
      state.demoHour = h;
      state.demoMinute = m;
      renderCurrentTab();
    }

    function updateDemoAngle(deg) {
      state.demoAngleDeg = parseInt(deg, 10);
      const svgEl = document.getElementById('liveAngleSvg');
      const labelEl = document.getElementById('liveAngleLabel');
      if (svgEl && labelEl) {
        const rad = (state.demoAngleDeg * Math.PI) / 180;
        const x2 = 120 + 75 * Math.cos(rad);
        const y2 = 110 - 75 * Math.sin(rad);
        const isRight = state.demoAngleDeg === 90;
        const color = isRight ? '#e11d48' : state.demoAngleDeg < 90 ? '#0d9488' : '#f59e0b';
        svgEl.innerHTML = `
          <line x1="120" y1="110" x2="195" y2="110" stroke="#0f294a" stroke-width="4" stroke-linecap="round"/>
          <line x1="120" y1="110" x2="${x2.toFixed(1)}" y2="${y2.toFixed(1)}" stroke="${color}" stroke-width="4" stroke-linecap="round"/>
          ${isRight
            ? `<polyline points="120,90 140,90 140,110" fill="none" stroke="#e11d48" stroke-width="2.5"/>`
            : `<path d="M 150 110 A 30 30 0 0 0 ${(120 + 30 * Math.cos(rad)).toFixed(1)} ${(110 - 30 * Math.sin(rad)).toFixed(1)}" fill="none" stroke="${color}" stroke-width="3"/>`
          }
          <circle cx="120" cy="110" r="5" fill="#0f294a"/>
        `;
        if (isRight) {
          labelEl.innerHTML = `<span class="text-rose-600 font-bold">Equal to a Right Angle (90°) — Square Corner!</span>`;
        } else if (state.demoAngleDeg < 90) {
          labelEl.innerHTML = `<span class="text-teal-700 font-bold">Smaller than a Right Angle (${state.demoAngleDeg}°)</span>`;
        } else {
          labelEl.innerHTML = `<span class="text-amber-600 font-bold">Greater than a Right Angle (${state.demoAngleDeg}°)</span>`;
        }
      }
    }

    function renderNotesView() {
      const topics = [
        { id: 'time', label: '1. Time', icon: 'fa-clock', color: 'bg-sky-600' },
        { id: 'shapes', label: '2. 2D & 3D Shapes', icon: 'fa-shapes', color: 'bg-indigo-600' },
        { id: 'symmetry', label: '3. Symmetry', icon: 'fa-wand-magic-sparkles', color: 'bg-rose-600' },
        { id: 'angles', label: '4. Angles & Compass', icon: 'fa-compass', color: 'bg-teal-600' }
      ];

      const pills = topics.map(t => {
        const active = state.activeNotesTopic === t.id;
        return `
          <button onclick="setNotesTopic('${t.id}')" class="shrink-0 px-4 py-2.5 rounded-2xl font-display font-semibold text-sm flex items-center gap-2 transition shadow-sm ${active ? `${t.color} text-white scale-[1.02]` : 'bg-white text-slate-700 border border-slate-200 hover:bg-slate-50'}">
            <i class="fa-solid ${t.icon}"></i> ${t.label}
          </button>
        `;
      }).join('');

      let content = '';
      if (state.activeNotesTopic === 'time') {
        const h = state.demoHour;
        const m = state.demoMinute;
        const mStr = m < 10 ? `0${m}` : `${m}`;
        let phrase = `${m} minutes past ${h}`;
        if (m === 0) phrase = `${h} o'clock`;
        else if (m === 30) phrase = `Half past ${h} (30 minutes past ${h})`;
        else if (m > 30) phrase = `${60 - m} minutes to ${(h % 12) + 1}`;

        content = `
          <div class="space-y-5 animate-pop">
            <!-- Interactive Clock Explorer -->
            <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200/80">
              <div class="flex flex-wrap items-center justify-between gap-2 mb-3">
                <h3 class="font-display font-bold text-lg text-mksNavy flex items-center gap-2">
                  <span class="w-8 h-8 rounded-xl bg-sky-100 text-sky-700 flex items-center justify-center"><i class="fa-solid fa-clock"></i></span>
                  Interactive Clock Explorer
                </h3>
                <span class="text-xs font-semibold bg-amber-100 text-amber-800 px-3 py-1 rounded-full">Tap a time below!</span>
              </div>
              <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 items-center">
                <div class="bg-slate-50 rounded-2xl p-4 flex flex-col items-center">
                  ${renderAnalogClockSVG(h, m, 165)}
                  <div class="mt-2 flex gap-4 text-xs font-semibold">
                    <span class="flex items-center gap-1.5 text-mksNavy"><span class="w-3 h-1.5 bg-mksNavy rounded"></span> Short = Hour</span>
                    <span class="flex items-center gap-1.5 text-teal-700"><span class="w-3 h-1.5 bg-teal-600 rounded"></span> Long = Minute</span>
                  </div>
                </div>
                <div class="space-y-3">
                  <div class="bg-sky-50 border border-sky-200 rounded-2xl p-4 text-center">
                    <div class="font-display font-bold text-3xl text-mksNavy">${h}:${mStr}</div>
                    <div class="text-sm font-semibold text-sky-800 mt-1">${phrase}</div>
                  </div>
                  <div class="grid grid-cols-2 gap-2">
                    <button onclick="updateDemoClock(4, 15)" class="py-2.5 px-3 rounded-xl bg-slate-100 hover:bg-sky-100 text-xs font-bold text-slate-800 transition">4:15 (15 past 4)</button>
                    <button onclick="updateDemoClock(10, 30)" class="py-2.5 px-3 rounded-xl bg-slate-100 hover:bg-sky-100 text-xs font-bold text-slate-800 transition">10:30 (Half past)</button>
                    <button onclick="updateDemoClock(4, 45)" class="py-2.5 px-3 rounded-xl bg-slate-100 hover:bg-sky-100 text-xs font-bold text-slate-800 transition">4:45 (15 to 5)</button>
                    <button onclick="updateDemoClock(7, 0)" class="py-2.5 px-3 rounded-xl bg-amber-100 hover:bg-amber-200 text-xs font-bold text-amber-900 transition">7:00 (Not 7:12!)</button>
                  </div>
                  <p class="text-xs text-slate-500 bg-rose-50 border border-rose-100 p-2.5 rounded-xl">
                    <strong class="text-rose-700">Exam Tip:</strong> When the long minute hand is on 12, write <strong>:00</strong> (e.g., 7:00), never 7:12!
                  </p>
                </div>
              </div>
            </div>

            <!-- Suitable Units of Time Card -->
            <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200/80">
              <h3 class="font-display font-bold text-lg text-mksNavy mb-3">Choosing Suitable Units of Time</h3>
              <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-3 text-sm">
                <div class="p-3.5 rounded-2xl bg-emerald-50 border border-emerald-200">
                  <div class="font-bold text-emerald-900 mb-1">⚡ Seconds (Very Fast)</div>
                  <ul class="text-emerald-800 text-xs space-y-1">
                    <li>• Clapping hands twice</li>
                    <li>• Sprinting 100 m</li>
                  </ul>
                </div>
                <div class="p-3.5 rounded-2xl bg-sky-50 border border-sky-200">
                  <div class="font-bold text-sky-900 mb-1">🍎 Minutes (Short Tasks)</div>
                  <ul class="text-sky-800 text-xs space-y-1">
                    <li>• Eating an apple</li>
                    <li>• Ironing a shirt</li>
                  </ul>
                </div>
                <div class="p-3.5 rounded-2xl bg-indigo-50 border border-indigo-200">
                  <div class="font-bold text-indigo-900 mb-1">✈️ Hours (Longer Events)</div>
                  <ul class="text-indigo-800 text-xs space-y-1">
                    <li>• Watching a full movie</li>
                    <li>• Flight from Singapore to Bangkok</li>
                  </ul>
                </div>
                <div class="p-3.5 rounded-2xl bg-amber-50 border border-amber-200">
                  <div class="font-bold text-amber-900 mb-1">🐣 Days & Weeks</div>
                  <ul class="text-amber-800 text-xs space-y-1">
                    <li>• A week passing by = 7 <strong>Days</strong></li>
                    <li>• Egg hatching into a chick = ~3 <strong>Weeks</strong></li>
                  </ul>
                </div>
                <div class="p-3.5 rounded-2xl bg-rose-50 border border-rose-200 sm:col-span-2">
                  <div class="font-bold text-rose-900 mb-1">🎂 Months & Years</div>
                  <ul class="text-rose-800 text-xs space-y-1">
                    <li>• Summer starting and ending = <strong>Months</strong></li>
                    <li>• A baby growing into an adult = <strong>Years</strong></li>
                  </ul>
                </div>
              </div>
            </div>

            <!-- Timetables & Intervals Card -->
            <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200/80">
              <h3 class="font-display font-bold text-lg text-mksNavy mb-2">Reading Timetables & Time Intervals</h3>
              <p class="text-xs text-slate-600 mb-3">Study the restaurant timetable from Page 7 of your worksheet:</p>
              <div class="overflow-x-auto rounded-2xl border border-slate-200">
                <table class="w-full text-left text-xs sm:text-sm">
                  <thead class="bg-mksNavy text-white">
                    <tr>
                      <th class="p-3">Days</th>
                      <th class="p-3">Opening Hours</th>
                    </tr>
                  </thead>
                  <tbody class="divide-y divide-slate-200 bg-white">
                    <tr>
                      <td class="p-3 font-semibold">Monday to Wednesday</td>
                      <td class="p-3">8:30 am – 3:00 pm &amp; 6:00 pm – 10:00 pm</td>
                    </tr>
                    <tr class="bg-rose-50">
                      <td class="p-3 font-semibold text-rose-800">Thursday</td>
                      <td class="p-3 font-bold text-rose-700">CLOSED</td>
                    </tr>
                    <tr>
                      <td class="p-3 font-semibold">Friday, Saturday, Sunday</td>
                      <td class="p-3">8:30 am – 3:00 pm &amp; 5:00 pm – 11:00 pm</td>
                    </tr>
                  </tbody>
                </table>
              </div>
              <div class="mt-3 grid grid-cols-1 sm:grid-cols-2 gap-2.5 text-xs">
                <div class="p-3 rounded-xl bg-slate-50 border border-slate-200">
                  <strong>Waiting Time Tip:</strong> Arriving at 5:00 on Tuesday means waiting until 6:00 = <strong>1 hour</strong>.
                </div>
                <div class="p-3 rounded-xl bg-slate-50 border border-slate-200">
                  <strong>Afternoon Break:</strong> Closed from 3:00 pm to 5:00 pm on Sunday = <strong>2 hours</strong>.
                </div>
              </div>
            </div>
          </div>
        `;
      } else if (state.activeNotesTopic === 'shapes') {
        content = `
          <div class="space-y-5 animate-pop">
            <!-- Polygons vs Non-Polygons -->
            <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200/80">
              <h3 class="font-display font-bold text-lg text-mksNavy mb-1">2D Shapes: Polygons vs Non-Polygons</h3>
              <p class="text-xs text-slate-600 mb-4">A <strong>polygon</strong> is a closed 2D shape made of <strong>straight sides only</strong>.</p>
              <div class="grid grid-cols-2 sm:grid-cols-4 gap-3 text-center">
                <div class="p-3 rounded-2xl bg-emerald-50 border border-emerald-200">
                  ${renderShapeSVG('triangle')}
                  <div class="font-bold text-sm text-emerald-900 mt-1">Triangle</div>
                  <span class="inline-block mt-1 px-2 py-0.5 rounded-full bg-emerald-600 text-white text-xs font-bold">Polygon: YES</span>
                </div>
                <div class="p-3 rounded-2xl bg-emerald-50 border border-emerald-200">
                  ${renderShapeSVG('pentagon_reg')}
                  <div class="font-bold text-sm text-emerald-900 mt-1">Regular Pentagon</div>
                  <span class="inline-block mt-1 px-2 py-0.5 rounded-full bg-emerald-600 text-white text-xs font-bold">Regular: YES</span>
                </div>
                <div class="p-3 rounded-2xl bg-amber-50 border border-amber-200">
                  ${renderShapeSVG('l_shape')}
                  <div class="font-bold text-sm text-amber-900 mt-1">L-Shape (6 sides)</div>
                  <span class="inline-block mt-1 px-2 py-0.5 rounded-full bg-amber-600 text-white text-xs font-bold">Irregular Polygon</span>
                </div>
                <div class="p-3 rounded-2xl bg-rose-50 border border-rose-200">
                  ${renderShapeSVG('circle')}
                  <div class="font-bold text-sm text-rose-900 mt-1">Circle</div>
                  <span class="inline-block mt-1 px-2 py-0.5 rounded-full bg-rose-600 text-white text-xs font-bold">Polygon: NO</span>
                </div>
              </div>
            </div>

            <!-- 3D Pyramids & Prisms -->
            <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200/80">
              <h3 class="font-display font-bold text-lg text-mksNavy mb-1">3D Shapes: Pyramids &amp; Prisms</h3>
              <p class="text-xs text-slate-600 mb-4">
                <strong>Pyramids</strong> have 1 base and triangular faces meeting at a top <strong>vertex</strong>. <strong>Prisms</strong> have 2 identical bases at opposite ends!
              </p>
              <div class="grid grid-cols-2 sm:grid-cols-4 gap-3 text-center">
                <div class="p-3 rounded-2xl bg-slate-50 border border-slate-200">
                  ${renderShapeSVG('tri_pyramid')}
                  <div class="font-bold text-xs sm:text-sm text-mksNavy mt-1">Triangular Pyramid</div>
                </div>
                <div class="p-3 rounded-2xl bg-slate-50 border border-slate-200">
                  ${renderShapeSVG('rect_pyramid')}
                  <div class="font-bold text-xs sm:text-sm text-mksNavy mt-1">Rectangular Pyramid</div>
                </div>
                <div class="p-3 rounded-2xl bg-slate-50 border border-slate-200">
                  ${renderShapeSVG('pent_prism')}
                  <div class="font-bold text-xs sm:text-sm text-mksNavy mt-1">Pentagonal Prism</div>
                </div>
                <div class="p-3 rounded-2xl bg-slate-50 border border-slate-200">
                  ${renderShapeSVG('hex_prism')}
                  <div class="font-bold text-xs sm:text-sm text-mksNavy mt-1">Hexagonal Prism</div>
                </div>
              </div>
            </div>
          </div>
        `;
      } else if (state.activeNotesTopic === 'symmetry') {
        content = `
          <div class="space-y-5 animate-pop">
            <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200/80">
              <h3 class="font-display font-bold text-lg text-mksNavy mb-1">Lines of Symmetry</h3>
              <p class="text-xs text-slate-600 mb-4">
                A <strong>line of symmetry</strong> divides a shape into two <strong>exact mirror halves</strong> that match when folded.
              </p>
              <div class="grid grid-cols-2 sm:grid-cols-4 gap-3 text-center">
                <div class="p-3 rounded-2xl bg-emerald-50 border border-emerald-200">
                  ${renderShapeSVG('sym_heart_yes')}
                  <div class="font-bold text-xs text-emerald-900 mt-1">Heart (Vertical)</div>
                  <span class="inline-block mt-1 px-2.5 py-0.5 rounded-full bg-emerald-600 text-white text-xs font-bold">YES ✓</span>
                </div>
                <div class="p-3 rounded-2xl bg-emerald-50 border border-emerald-200">
                  ${renderShapeSVG('sym_sun_yes')}
                  <div class="font-bold text-xs text-emerald-900 mt-1">Sun (Vertical)</div>
                  <span class="inline-block mt-1 px-2.5 py-0.5 rounded-full bg-emerald-600 text-white text-xs font-bold">YES ✓</span>
                </div>
                <div class="p-3 rounded-2xl bg-rose-50 border border-rose-200">
                  ${renderShapeSVG('sym_star_no')}
                  <div class="font-bold text-xs text-rose-900 mt-1">Star (Horizontal)</div>
                  <span class="inline-block mt-1 px-2.5 py-0.5 rounded-full bg-rose-600 text-white text-xs font-bold">NO ✗</span>
                </div>
                <div class="p-3 rounded-2xl bg-rose-50 border border-rose-200">
                  ${renderShapeSVG('sym_l_no')}
                  <div class="font-bold text-xs text-rose-900 mt-1">L-Shape (Vertical)</div>
                  <span class="inline-block mt-1 px-2.5 py-0.5 rounded-full bg-rose-600 text-white text-xs font-bold">NO ✗</span>
                </div>
              </div>
            </div>

            <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200/80">
              <h3 class="font-display font-bold text-lg text-mksNavy mb-1">Sketching Reflections Across a Mirror Line</h3>
              <p class="text-xs text-slate-600 mb-3">
                When reflecting a shape across a mirror line, <strong>flip</strong> it so every corner is the exact same distance from the mirror on the opposite side.
              </p>
              <div class="bg-slate-50 p-4 rounded-2xl border border-slate-200 text-center">
                ${renderShapeSVG('reflect_trap_choice')}
                <p class="text-xs font-semibold text-slate-700 mt-2">Notice how the touching corner stays on the mirror line, and the shape flips like a butterfly's wings!</p>
              </div>
            </div>
          </div>
        `;
      } else {
        content = `
          <div class="space-y-5 animate-pop">
            <!-- Interactive Angle Tester -->
            <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200/80">
              <h3 class="font-display font-bold text-lg text-mksNavy mb-1">Interactive Right-Angle Checker</h3>
              <p class="text-xs text-slate-600 mb-3">
                Slide to change the angle and compare it with a <strong>Right Angle</strong> (the square corner of a folded sheet of paper):
              </p>
              <div class="bg-slate-50 rounded-2xl p-4 border border-slate-200 flex flex-col items-center">
                <svg id="liveAngleSvg" viewBox="0 0 240 135" class="w-60 h-32">
                  <line x1="120" y1="110" x2="195" y2="110" stroke="#0f294a" stroke-width="4" stroke-linecap="round"/>
                  <line x1="120" y1="110" x2="120" y2="35" stroke="#e11d48" stroke-width="4" stroke-linecap="round"/>
                  <polyline points="120,90 140,90 140,110" fill="none" stroke="#e11d48" stroke-width="2.5"/>
                  <circle cx="120" cy="110" r="5" fill="#0f294a"/>
                </svg>
                <div id="liveAngleLabel" class="text-sm mt-1">
                  <span class="text-rose-600 font-bold">Equal to a Right Angle (90°) — Square Corner!</span>
                </div>
                <input type="range" min="25" max="155" value="90" oninput="updateDemoAngle(this.value)" class="w-full max-w-xs mt-3 accent-mksIndigo cursor-pointer">
                <div class="flex gap-2 mt-3">
                  <button onclick="document.querySelector('input[type=range]').value=45; updateDemoAngle(45)" class="px-3 py-1.5 rounded-xl bg-teal-100 text-teal-900 text-xs font-bold">Smaller (45°)</button>
                  <button onclick="document.querySelector('input[type=range]').value=90; updateDemoAngle(90)" class="px-3 py-1.5 rounded-xl bg-rose-100 text-rose-900 text-xs font-bold">Right Angle (90°)</button>
                  <button onclick="document.querySelector('input[type=range]').value=135; updateDemoAngle(135)" class="px-3 py-1.5 rounded-xl bg-amber-100 text-amber-900 text-xs font-bold">Greater (135°)</button>
                </div>
              </div>
            </div>

            <!-- Compass Directions Card -->
            <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200/80">
              <h3 class="font-display font-bold text-lg text-mksNavy mb-1">Compass Directions: North, South, East, West</h3>
              <p class="text-xs text-slate-600 mb-3">Remember: <strong>N</strong>ever <strong>E</strong>at <strong>S</strong>oggy <strong>W</strong>affles (clockwise from top!)</p>
              <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 items-center">
                ${renderShapeSVG('compass_squirrel')}
                <div class="space-y-2 text-sm">
                  <div class="p-3 rounded-xl bg-sky-50 border border-sky-200 font-semibold text-sky-900">⬆️ <strong>North (N):</strong> The apple is north of the squirrel.</div>
                  <div class="p-3 rounded-xl bg-amber-50 border border-amber-200 font-semibold text-amber-900">⬇️ <strong>South (S):</strong> The nut is south of the squirrel.</div>
                  <div class="p-3 rounded-xl bg-orange-50 border border-orange-200 font-semibold text-orange-900">➡️ <strong>East (E):</strong> The carrot is east of the squirrel.</div>
                  <div class="p-3 rounded-xl bg-rose-50 border border-rose-200 font-semibold text-rose-900">⬅️ <strong>West (W):</strong> The strawberry is west of the squirrel.</div>
                </div>
              </div>
            </div>
          </div>
        `;
      }

      return `
        <div class="space-y-4">
          <div class="bg-gradient-to-r from-mksNavy to-indigo-900 text-white rounded-3xl p-5 shadow-md">
            <h2 class="font-display font-bold text-xl sm:text-2xl">Interactive Revision Notes</h2>
            <p class="text-xs sm:text-sm text-sky-200 mt-1">Explore visual study cards from your Modern Knowledge School Year 3 Term 1 worksheets.</p>
          </div>

          <!-- Topic Selector Pills -->
          <div class="flex gap-2 overflow-x-auto no-scrollbar pb-1">
            ${pills}
          </div>

          ${content}

          <div class="pt-2 text-center">
            <button onclick="switchTab('practice')" class="inline-flex items-center gap-2 bg-amber-400 hover:bg-amber-500 text-mksNavy font-display font-bold px-6 py-3.5 rounded-2xl shadow-md transition">
              <span>Ready to Test Yourself? Go to Topic Practice</span>
              <i class="fa-solid fa-arrow-right"></i>
            </button>
          </div>
        </div>
      `;
    }

    // =========================================================================
    // 7. VIEW 2: SELF-CORRECTING TOPIC PRACTICE
    // =========================================================================
    const userQuizSelections = {};
    const revealedHints = {};

    function setPracticeFilter(filter) {
      playTone('click');
      state.activeTopicFilter = filter;
      renderCurrentTab();
    }

    function selectPracticeOption(qId, optIndex) {
      const q = practiceQuestions.find(item => item.id === qId);
      if (!q) return;
      const chosen = q.options[optIndex];
      userQuizSelections[qId] = chosen;

      if (chosen === q.answer) {
        playTone('correct');
        const wasSolved = !!state.solvedQuestions[qId];
        addStars(10, qId);
        if (!wasSolved) {
          showToast('Awesome job! +10 Stars earned!', '⭐');
        }
      } else {
        playTone('wrong');
      }
      renderCurrentTab();
    }

    function toggleHint(qId) {
      playTone('click');
      revealedHints[qId] = !revealedHints[qId];
      renderCurrentTab();
    }

    function renderPracticeView() {
      const filters = [
        { id: 'all', label: 'All Topics (24)' },
        { id: 'time', label: 'Time' },
        { id: 'shapes', label: '2D & 3D Shapes' },
        { id: 'symmetry', label: 'Symmetry' },
        { id: 'angles', label: 'Angles & Compass' }
      ];

      const filtered = state.activeTopicFilter === 'all'
        ? practiceQuestions
        : practiceQuestions.filter(q => q.topic === state.activeTopicFilter);

      const solvedInFilter = filtered.filter(q => state.solvedQuestions[q.id]).length;

      const filterHTML = filters.map(f => {
        const active = state.activeTopicFilter === f.id;
        return `
          <button onclick="setPracticeFilter('${f.id}')" class="shrink-0 px-4 py-2 rounded-2xl font-display font-semibold text-xs sm:text-sm transition ${active ? 'bg-mksIndigo text-white shadow-sm' : 'bg-white text-slate-700 border border-slate-200 hover:bg-slate-50'}">
            ${f.label}
          </button>
        `;
      }).join('');

      const cardsHTML = filtered.map((q, idx) => {
        const selected = userQuizSelections[q.id];
        const isCorrect = selected === q.answer;
        const isWrong = selected && selected !== q.answer;
        const alreadyMastered = !!state.solvedQuestions[q.id];

        const optionsHTML = q.options.map((opt, oIdx) => {
          let btnStyle = 'bg-slate-50 hover:bg-indigo-50/70 border-slate-200 text-slate-800';
          let badge = `<span class="w-7 h-7 rounded-lg bg-white border border-slate-300 flex items-center justify-center text-xs font-bold text-slate-600 shrink-0">${String.fromCharCode(65 + oIdx)}</span>`;

          if (selected === opt) {
            if (opt === q.answer) {
              btnStyle = 'bg-emerald-50 border-emerald-500 text-emerald-950 ring-2 ring-emerald-500/20';
              badge = `<span class="w-7 h-7 rounded-lg bg-emerald-600 text-white flex items-center justify-center text-xs font-bold shrink-0"><i class="fa-solid fa-check"></i></span>`;
            } else {
              btnStyle = 'bg-rose-50 border-rose-500 text-rose-950 ring-2 ring-rose-500/20';
              badge = `<span class="w-7 h-7 rounded-lg bg-rose-600 text-white flex items-center justify-center text-xs font-bold shrink-0"><i class="fa-solid fa-xmark"></i></span>`;
            }
          } else if (selected && opt === q.answer && isWrong) {
            // Highlight correct answer gently after wrong attempt so child learns immediately
            btnStyle = 'bg-emerald-50/70 border-emerald-400 text-emerald-900';
          }

          return `
            <button onclick="selectPracticeOption('${q.id}', ${oIdx})" class="w-full text-left p-3.5 rounded-2xl border-2 transition flex items-center gap-3 font-medium text-sm sm:text-base ${btnStyle}">
              ${badge}
              <span>${opt}</span>
            </button>
          `;
        }).join('');

        return `
          <div class="bg-white rounded-3xl p-5 shadow-sm border ${alreadyMastered ? 'border-emerald-200' : 'border-slate-200/80'} space-y-3.5">
            <div class="flex items-center justify-between gap-2">
              <span class="text-xs font-bold uppercase tracking-wider px-2.5 py-1 rounded-lg bg-slate-100 text-slate-600">
                Q${idx + 1} • ${q.subtopic}
              </span>
              <div class="flex items-center gap-2">
                ${alreadyMastered ? `<span class="text-xs font-bold text-emerald-700 bg-emerald-100 px-2.5 py-1 rounded-full"><i class="fa-solid fa-star text-amber-500 mr-1"></i>Mastered</span>` : ''}
                <button onclick="toggleHint('${q.id}')" class="text-xs font-semibold text-indigo-600 hover:text-indigo-800 bg-indigo-50 px-2.5 py-1 rounded-lg">
                  <i class="fa-regular fa-lightbulb mr-1"></i>Hint
                </button>
              </div>
            </div>

            <p class="font-semibold text-base sm:text-lg text-mksNavy leading-snug">${q.prompt}</p>

            ${q.visual ? `<div class="py-2">${q.visual()}</div>` : ''}

            ${revealedHints[q.id] ? `
              <div class="p-3 rounded-2xl bg-amber-50 border border-amber-200 text-xs sm:text-sm text-amber-900 flex items-start gap-2">
                <i class="fa-solid fa-lightbulb text-amber-500 mt-0.5"></i>
                <span><strong>Hint:</strong> ${q.hint}</span>
              </div>
            ` : ''}

            <div class="space-y-2.5 pt-1">
              ${optionsHTML}
            </div>

            ${selected ? `
              <div class="p-3.5 rounded-2xl ${isCorrect ? 'bg-emerald-50 border border-emerald-200 text-emerald-900' : 'bg-rose-50 border border-rose-200 text-rose-900'} text-xs sm:text-sm animate-pop">
                <div class="font-bold mb-0.5">
                  ${isCorrect ? '🎉 Correct! Well done!' : '💡 Not quite — check the explanation:'}
                </div>
                <p>${q.explanation}</p>
              </div>
            ` : ''}
          </div>
        `;
      }).join('');

      return `
        <div class="space-y-4">
          <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200/80 flex flex-col sm:flex-row sm:items-center justify-between gap-4">
            <div>
              <h2 class="font-display font-bold text-xl text-mksNavy">Self-Correcting Topic Practice</h2>
              <p class="text-xs sm:text-sm text-slate-600">Tap an answer to check immediately and earn +10 Stars per question!</p>
            </div>
            <div class="bg-indigo-50 border border-indigo-100 px-4 py-2.5 rounded-2xl text-center shrink-0">
              <div class="text-xs font-semibold text-indigo-700">Completed</div>
              <div class="font-display font-bold text-lg text-mksNavy">${solvedInFilter} / ${filtered.length}</div>
            </div>
          </div>

          <div class="flex gap-2 overflow-x-auto no-scrollbar pb-1">
            ${filterHTML}
          </div>

          <div class="space-y-4">
            ${cardsHTML}
          </div>
        </div>
      `;
    }

    // =========================================================================
    // 8. VIEW 3: PAST PAPER SIMULATOR (Timed/Untimed + Auto-Grade Report Card)
    // =========================================================================
    function startPastPaper(paperId, timed = false) {
      playTone('click');
      const paper = pastPapers[paperId];
      if (!paper) return;

      state.activePaperId = paperId;
      state.paperAnswers = {};
      state.paperSubmitted = false;
      state.paperTimed = timed;
      state.timerSeconds = paper.durationMinutes * 60;

      clearInterval(state.timerInterval);
      if (timed) {
        state.timerInterval = setInterval(() => {
          state.timerSeconds--;
          const timerEl = document.getElementById('examTimerDisplay');
          if (timerEl) {
            timerEl.textContent = formatSeconds(state.timerSeconds);
          }
          if (state.timerSeconds <= 0) {
            clearInterval(state.timerInterval);
            submitPastPaper(true);
          }
        }, 1000);
      }

      renderCurrentTab();
      window.scrollTo({ top: 0, behavior: 'smooth' });
    }

    function formatSeconds(sec) {
      const m = Math.floor(Math.max(0, sec) / 60);
      const s = Math.max(0, sec) % 60;
      return `${m}:${s < 10 ? '0' : ''}${s}`;
    }

    function selectPaperOption(qId, optIndex) {
      if (state.paperSubmitted) return;
      const paper = pastPapers[state.activePaperId];
      const q = paper.questions.find(item => item.id === qId);
      if (!q) return;
      playTone('click');
      state.paperAnswers[qId] = q.options[optIndex];
      renderCurrentTab();
    }

    function submitPastPaper(autoTimeUp = false) {
      const paper = pastPapers[state.activePaperId];
      if (!paper) return;

      const answeredCount = Object.keys(state.paperAnswers).length;
      if (!autoTimeUp && answeredCount < paper.questions.length) {
        const missing = paper.questions.length - answeredCount;
        showToast(`You still have ${missing} unanswered question(s). Please answer all questions before submitting!`, '📝');
        return;
      }

      clearInterval(state.timerInterval);
      state.paperSubmitted = true;

      let score = 0;
      paper.questions.forEach(q => {
        if (state.paperAnswers[q.id] === q.answer) score++;
      });

      const bonusStars = score * 15;
      addStars(bonusStars, `paper_${paper.id}_${Date.now()}`);
      playTone('correct');
      showToast(`Exam Marked! You scored ${score}/${paper.questions.length} (+${bonusStars} Stars!)`, '🏆');
      renderCurrentTab();
      window.scrollTo({ top: 0, behavior: 'smooth' });
    }

    function exitPastPaper() {
      clearInterval(state.timerInterval);
      state.activePaperId = null;
      state.paperSubmitted = false;
      renderCurrentTab();
    }

    function renderPastPapersView() {
      // Paper Selection Screen
      if (!state.activePaperId) {
        return `
          <div class="space-y-5 animate-pop">
            <div class="bg-gradient-to-r from-mksNavy to-teal-900 text-white rounded-3xl p-5 shadow-md">
              <h2 class="font-display font-bold text-xl sm:text-2xl">Term 1 Past Paper Simulator</h2>
              <p class="text-xs sm:text-sm text-teal-100 mt-1">Practice real exam papers on your phone or tablet with automatic grading and detailed review.</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
              <!-- Paper A Card -->
              <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200 flex flex-col justify-between space-y-4">
                <div>
                  <span class="inline-block px-3 py-1 rounded-full bg-amber-100 text-amber-800 text-xs font-bold mb-2">Official Enrichment Paper</span>
                  <h3 class="font-display font-bold text-lg text-mksNavy">${pastPapers.paperA.title}</h3>
                  <p class="text-xs text-slate-600 mt-1">${pastPapers.paperA.subtitle}</p>
                  <ul class="mt-3 text-xs text-slate-600 space-y-1">
                    <li><i class="fa-solid fa-check text-teal-600 mr-1.5"></i>12 Exam Questions (Time, Shapes, Symmetry, Compass)</li>
                    <li><i class="fa-solid fa-check text-teal-600 mr-1.5"></i>Instant auto-marking &amp; topic strength report</li>
                  </ul>
                </div>
                <div class="grid grid-cols-2 gap-2 pt-2">
                  <button onclick="startPastPaper('paperA', false)" class="py-3 px-3 rounded-2xl bg-mksIndigo hover:bg-indigo-700 text-white font-display font-bold text-xs sm:text-sm shadow-sm transition">
                    <i class="fa-solid fa-play mr-1"></i> Untimed Mode
                  </button>
                  <button onclick="startPastPaper('paperA', true)" class="py-3 px-3 rounded-2xl bg-amber-400 hover:bg-amber-500 text-mksNavy font-display font-bold text-xs sm:text-sm shadow-sm transition">
                    <i class="fa-solid fa-stopwatch mr-1"></i> Timed (25m)
                  </button>
                </div>
              </div>

              <!-- Paper B Card -->
              <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200 flex flex-col justify-between space-y-4">
                <div>
                  <span class="inline-block px-3 py-1 rounded-full bg-sky-100 text-sky-800 text-xs font-bold mb-2">Practice Past Paper B</span>
                  <h3 class="font-display font-bold text-lg text-mksNavy">${pastPapers.paperB.title}</h3>
                  <p class="text-xs text-slate-600 mt-1">${pastPapers.paperB.subtitle}</p>
                  <ul class="mt-3 text-xs text-slate-600 space-y-1">
                    <li><i class="fa-solid fa-check text-teal-600 mr-1.5"></i>10 Fresh Past Paper Questions</li>
                    <li><i class="fa-solid fa-check text-teal-600 mr-1.5"></i>Includes Restaurant Timetable &amp; 3D Tower problems</li>
                  </ul>
                </div>
                <div class="grid grid-cols-2 gap-2 pt-2">
                  <button onclick="startPastPaper('paperB', false)" class="py-3 px-3 rounded-2xl bg-mksIndigo hover:bg-indigo-700 text-white font-display font-bold text-xs sm:text-sm shadow-sm transition">
                    <i class="fa-solid fa-play mr-1"></i> Untimed Mode
                  </button>
                  <button onclick="startPastPaper('paperB', true)" class="py-3 px-3 rounded-2xl bg-amber-400 hover:bg-amber-500 text-mksNavy font-display font-bold text-xs sm:text-sm shadow-sm transition">
                    <i class="fa-solid fa-stopwatch mr-1"></i> Timed (20m)
                  </button>
                </div>
              </div>
            </div>
          </div>
        `;
      }

      // Active Exam or Graded Report View
      const paper = pastPapers[state.activePaperId];
      const total = paper.questions.length;
      const answeredCount = Object.keys(state.paperAnswers).length;

      let reportBanner = '';
      if (state.paperSubmitted) {
        let correctCount = 0;
        const topicStats = {};
        paper.questions.forEach(q => {
          if (!topicStats[q.topic]) topicStats[q.topic] = { total: 0, right: 0 };
          topicStats[q.topic].total++;
          if (state.paperAnswers[q.id] === q.answer) {
            correctCount++;
            topicStats[q.topic].right++;
          }
        });
        const pct = Math.round((correctCount / total) * 100);
        const gradeMsg = pct >= 85 ? 'Outstanding! Exam Ready! 🌟' : pct >= 65 ? 'Great Job! Keep Practicing! 👍' : 'Good Effort! Review the red items below. 💪';

        const breakdownHTML = Object.entries(topicStats).map(([tName, stat]) => {
          const tPct = Math.round((stat.right / stat.total) * 100);
          return `
            <div class="bg-white/10 rounded-2xl p-3">
              <div class="flex justify-between text-xs font-bold mb-1">
                <span>${tName}</span>
                <span>${stat.right}/${stat.total} (${tPct}%)</span>
              </div>
              <div class="w-full h-2 bg-white/20 rounded-full overflow-hidden">
                <div class="h-full bg-amber-400 rounded-full" style="width: ${tPct}%"></div>
              </div>
            </div>
          `;
        }).join('');

        reportBanner = `
          <div class="bg-gradient-to-br from-mksNavy to-indigo-900 text-white rounded-3xl p-6 shadow-lg space-y-4 animate-pop">
            <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-4 border-b border-white/15 pb-4">
              <div>
                <span class="text-xs font-bold uppercase tracking-wider text-amber-300">Official Auto-Graded Report</span>
                <h3 class="font-display font-bold text-2xl mt-0.5">${gradeMsg}</h3>
                <p class="text-xs text-sky-200 mt-1">Scroll down to review every question and explanation.</p>
              </div>
              <div class="bg-white text-mksNavy rounded-2xl px-5 py-3 text-center shrink-0">
                <div class="font-display font-bold text-3xl text-mksIndigo">${correctCount} / ${total}</div>
                <div class="text-xs font-bold text-slate-500">Score: ${pct}%</div>
              </div>
            </div>
            <div class="grid grid-cols-1 sm:grid-cols-2 gap-2.5">
              ${breakdownHTML}
            </div>
            <div class="flex flex-wrap gap-2 pt-1 no-print">
              <button onclick="startPastPaper('${paper.id}', ${state.paperTimed})" class="px-4 py-2.5 rounded-xl bg-amber-400 text-mksNavy font-display font-bold text-xs sm:text-sm">
                <i class="fa-solid fa-rotate-right mr-1"></i> Retake Paper
              </button>
              <button onclick="window.print()" class="px-4 py-2.5 rounded-xl bg-white/15 hover:bg-white/25 text-white font-display font-semibold text-xs sm:text-sm">
                <i class="fa-solid fa-print mr-1"></i> Print / Save PDF
              </button>
              <button onclick="exitPastPaper()" class="px-4 py-2.5 rounded-xl bg-white/15 hover:bg-white/25 text-white font-display font-semibold text-xs sm:text-sm">
                Choose Another Paper
              </button>
            </div>
          </div>
        `;
      }

      const questionsHTML = paper.questions.map(q => {
        const chosen = state.paperAnswers[q.id];
        const isCorrect = state.paperSubmitted && chosen === q.answer;
        const isWrong = state.paperSubmitted && chosen !== q.answer;

        const optsHTML = q.options.map((opt, oIdx) => {
          let cls = 'bg-slate-50 border-slate-200 text-slate-800 hover:bg-slate-100';
          if (!state.paperSubmitted && chosen === opt) {
            cls = 'bg-indigo-50 border-mksIndigo text-mksNavy ring-2 ring-indigo-500/20 font-semibold';
          } else if (state.paperSubmitted) {
            if (opt === q.answer) {
              cls = 'bg-emerald-50 border-emerald-500 text-emerald-950 font-bold';
            } else if (chosen === opt && opt !== q.answer) {
              cls = 'bg-rose-50 border-rose-500 text-rose-950 line-through';
            }
          }

          return `
            <button ${state.paperSubmitted ? 'disabled' : ''} onclick="selectPaperOption('${q.id}', ${oIdx})" class="w-full text-left p-3.5 rounded-2xl border-2 transition flex items-center gap-3 text-sm sm:text-base ${cls}">
              <span class="w-7 h-7 rounded-lg bg-white border border-slate-300 flex items-center justify-center text-xs font-bold shrink-0">${String.fromCharCode(65 + oIdx)}</span>
              <span>${opt}</span>
            </button>
          `;
        }).join('');

        return `
          <div class="bg-white rounded-3xl p-5 shadow-sm border ${state.paperSubmitted ? (isCorrect ? 'border-emerald-300' : 'border-rose-300') : 'border-slate-200'} space-y-3">
            <div class="flex items-center justify-between">
              <span class="text-xs font-bold text-slate-500 uppercase">${q.topic}</span>
              ${state.paperSubmitted ? (isCorrect
                ? `<span class="text-xs font-bold text-emerald-700 bg-emerald-100 px-2.5 py-1 rounded-full">✓ Correct (1 mark)</span>`
                : `<span class="text-xs font-bold text-rose-700 bg-rose-100 px-2.5 py-1 rounded-full">✗ Incorrect (0 marks)</span>`
              ) : ''}
            </div>
            <p class="font-semibold text-base sm:text-lg text-mksNavy">${q.prompt}</p>
            ${q.visual ? `<div class="py-1">${q.visual()}</div>` : ''}
            <div class="space-y-2">${optsHTML}</div>
            ${state.paperSubmitted ? `
              <div class="p-3 rounded-2xl bg-slate-50 border border-slate-200 text-xs sm:text-sm text-slate-700">
                <strong>Marking Scheme:</strong> ${q.explanation}
              </div>
            ` : ''}
          </div>
        `;
      }).join('');

      return `
        <div class="space-y-4">
          <!-- Top Sticky Exam Bar -->
          <div class="bg-white rounded-2xl p-3.5 shadow-sm border border-slate-200 flex items-center justify-between gap-2 no-print">
            <button onclick="exitPastPaper()" class="text-xs sm:text-sm font-bold text-slate-600 hover:text-mksNavy flex items-center gap-1.5 px-2.5 py-1.5 rounded-xl bg-slate-100">
              <i class="fa-solid fa-arrow-left"></i> Exit
            </button>
            <div class="text-center">
              <div class="font-display font-bold text-sm sm:text-base text-mksNavy truncate max-w-[180px] sm:max-w-none">${paper.title}</div>
              <div class="text-xs text-slate-500">Answered: <strong>${answeredCount}/${total}</strong></div>
            </div>
            ${state.paperTimed && !state.paperSubmitted ? `
              <div class="px-3 py-1.5 rounded-xl bg-rose-50 border border-rose-200 text-rose-700 font-display font-bold text-sm flex items-center gap-1.5">
                <i class="fa-solid fa-stopwatch"></i>
                <span id="examTimerDisplay">${formatSeconds(state.timerSeconds)}</span>
              </div>
            ` : `<span class="text-xs font-bold text-teal-700 bg-teal-50 px-2.5 py-1.5 rounded-xl">${state.paperSubmitted ? 'Graded' : 'Untimed'}</span>`}
          </div>

          ${reportBanner}

          <div class="space-y-4">
            ${questionsHTML}
          </div>

          ${!state.paperSubmitted ? `
            <div class="pt-2 pb-4 text-center no-print">
              <button onclick="submitPastPaper(false)" class="w-full sm:w-auto bg-emerald-600 hover:bg-emerald-700 text-white font-display font-bold text-base sm:text-lg px-8 py-4 rounded-2xl shadow-lg transition">
                <i class="fa-solid fa-paper-plane mr-2"></i> Submit &amp; Auto-Grade Exam (${answeredCount}/${total})
              </button>
            </div>
          ` : ''}
        </div>
      `;
    }

    // =========================================================================
    // 9. VIEW 4: QUICK REFERENCE / CHEAT SHEET
    // =========================================================================
    function renderReferenceView() {
      return `
        <div class="space-y-4 animate-pop">
          <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200 flex items-center justify-between gap-3">
            <div>
              <h2 class="font-display font-bold text-xl text-mksNavy">Year 3 Term 1 Quick Reference Sheet</h2>
              <p class="text-xs sm:text-sm text-slate-600">Last-minute revision checklist for students and parents.</p>
            </div>
            <button onclick="window.print()" class="no-print shrink-0 px-4 py-2.5 rounded-2xl bg-mksNavy text-white font-display font-semibold text-xs sm:text-sm flex items-center gap-2">
              <i class="fa-solid fa-print"></i> Print
            </button>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
            <!-- Unit 1 -->
            <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200 space-y-2">
              <div class="flex items-center gap-2 text-sky-700 font-display font-bold text-lg">
                <i class="fa-solid fa-clock"></i> 1. Time Key Facts
              </div>
              <ul class="text-xs sm:text-sm text-slate-700 space-y-1.5 leading-relaxed">
                <li>• <strong>1 minute</strong> = 60 seconds | <strong>1 hour</strong> = 60 minutes</li>
                <li>• <strong>1 day</strong> = 24 hours | <strong>1 week</strong> = 7 days</li>
                <li>• <strong>1 year</strong> = 12 months (or 365 days)</li>
                <li>• <strong>Short hand</strong> = Hour | <strong>Long hand</strong> = Minutes (count by 5s around the clock).</li>
                <li>• <strong>O'clock rule:</strong> Long hand on 12 means <strong>:00</strong> (e.g., 7:00, NOT 7:12).</li>
              </ul>
            </div>

            <!-- Unit 2 -->
            <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200 space-y-2">
              <div class="flex items-center gap-2 text-indigo-700 font-display font-bold text-lg">
                <i class="fa-solid fa-shapes"></i> 2. 2D &amp; 3D Shapes
              </div>
              <ul class="text-xs sm:text-sm text-slate-700 space-y-1.5 leading-relaxed">
                <li>• <strong>Polygon:</strong> Closed 2D shape with <strong>straight sides only</strong> (Circles are NOT polygons).</li>
                <li>• <strong>Regular Polygon:</strong> All sides equal AND all angles equal.</li>
                <li>• <strong>Pyramid:</strong> Named after its base (triangular, rectangular, pentagonal, hexagonal) + meets at 1 top <strong>vertex</strong>.</li>
                <li>• <strong>Prism:</strong> Has 2 matching bases at both ends connected by rectangles.</li>
              </ul>
            </div>

            <!-- Unit 3 -->
            <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200 space-y-2">
              <div class="flex items-center gap-2 text-rose-700 font-display font-bold text-lg">
                <i class="fa-solid fa-wand-magic-sparkles"></i> 3. Symmetry &amp; Reflections
              </div>
              <ul class="text-xs sm:text-sm text-slate-700 space-y-1.5 leading-relaxed">
                <li>• <strong>Line of Symmetry:</strong> Both sides match exactly when folded along the dashed line.</li>
                <li>• <strong>Mirror Reflection:</strong> Flips the shape across the mirror line. Every corner stays the exact same distance from the mirror line.</li>
              </ul>
            </div>

            <!-- Unit 4 -->
            <div class="bg-white rounded-3xl p-5 shadow-sm border border-slate-200 space-y-2">
              <div class="flex items-center gap-2 text-teal-700 font-display font-bold text-lg">
                <i class="fa-solid fa-compass"></i> 4. Angles &amp; Compass
              </div>
              <ul class="text-xs sm:text-sm text-slate-700 space-y-1.5 leading-relaxed">
                <li>• <strong>Right Angle (90°):</strong> Forms a square corner (like a folded paper corner).</li>
                <li>• <strong>Smaller than a right angle:</strong> Sharp/narrow opening.</li>
                <li>• <strong>Greater than a right angle:</strong> Wide opening.</li>
                <li>• <strong>Compass:</strong> <strong>N</strong>orth (Up), <strong>E</strong>ast (Right), <strong>S</strong>outh (Down), <strong>W</strong>est (Left).</li>
              </ul>
            </div>
          </div>
        </div>
      `;
    }

    // =========================================================================
    // 10. INITIALIZATION
    // =========================================================================
    window.addEventListener('DOMContentLoaded', () => {
      document.getElementById('starCount').textContent = state.stars;
      updateNavUI();
      renderCurrentTab();
    });
  </script>
</body>
</html>
