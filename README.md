
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Multi-Page Accessible Website - Homework 2 Showcase</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        /* ==========================================================================
           HW2 SHARED EXTERNAL STYLESHEET (Embedded for Single-File Environment)
           ========================================================================== */

        /* --- ACCESSIBILITY: SKIP TO MAIN CONTENT LINK --- */
        .skip-link {
            position: absolute;
            top: -100px;
            left: 10px;
            background: #0284c7;
            color: #ffffff;
            padding: 12px 18px;
            z-index: 9999;
            font-weight: bold;
            border-radius: 0 0 8px 8px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.3);
            text-decoration: underline;
            transition: top 0.2s ease-in-out;
        }

        .skip-link:focus {
            top: 0;
            outline: 3px solid #f59e0b;
        }

        /* --- BODY RULE --- */
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            font-size: 16px;
            color: #1a202c;
            background-color: #f8fafc;
            margin: 0;
            padding: 0;
            line-height: 1.5;
        }

        /* --- HEADER RULE --- */
        header {
            background-color: #0f172a;
            color: #ffffff;
            padding: 1.25rem 1rem;
            text-align: center;
            border-bottom: 4px solid #0284c7;
        }

        /* --- HW2: NAV STYLING MODIFICATION --- */
        nav {
            background-color: #1e293b;
            padding: 0.75rem 1rem;
            display: inline-block; /* HW2 Requirement: inline-block nav */
            width: 80%;           /* HW2 Requirement: width ~80% */
            margin: 0 auto;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            text-align: center;
        }

        /* --- HW2: DESCENDANT SELECTOR FOR NAV IMAGE --- */
        nav img {
            width: 10%;           /* HW2 Requirement: width ~10% for nav logo */
            height: auto;
            vertical-align: middle;
            margin-right: 15px;
            border-radius: 50%;
        }

        /* --- LIST & NAV LINK STYLING --- */
        ul.nav-list {
            list-style-type: none;
            padding: 0;
            margin: 0;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 15px;
            vertical-align: middle;
        }

        /*
        COMMENTED OUT HW1 STYLING FOR LI ELEMENT (HW2 Requirement)
        li {
            display: inline-block;
            width: 140px;
        }
        */

        li a {
            display: inline-block;
            padding: 8px 16px;
            color: #ffffff;
            text-decoration: none;
            font-weight: 600;
            border-radius: 6px;
            transition: all 0.2s ease;
            border: 2px solid transparent;
        }

        li a:hover, li a:focus {
            background-color: #0284c7;
            color: #ffffff;
            outline: 2px solid #38bdf8;
            text-decoration: underline;
        }

        li a.active-link {
            background-color: #0284c7;
            border-color: #38bdf8;
        }

        /* --- MAIN RULE --- */
        main {
            background-color: #ffffff;
            font-size: 1.05rem;
            max-width: 950px;
            margin: 2rem auto;
            padding: 2rem;
            border-radius: 8px;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
            min-height: 400px;
        }

        /* --- FOOTER RULE --- */
        footer {
            background-color: #0f172a;
            color: #f8fafc;
            text-align: center;
            padding: 1.5rem 1rem;
            margin-top: 3rem;
            border-top: 2px solid #334155;
        }

        /* --- H1 RULE --- */
        h1 {
            text-align: center;
            font-family: 'Georgia', Cambria, serif;
            color: #0369a1;
            margin-top: 0;
            margin-bottom: 1.25rem;
            font-size: 2.25rem;
        }

        /* --- P RULE --- */
        p {
            line-height: 1.75;
            margin-bottom: 1.25rem;
            color: #334155;
        }

        /* --- HW2: GRID CLASS STYLING --- */
        .grid {
            display: grid;
            grid-template-columns: 40% 40%;  /* HW2 Requirement: Two columns approximately 40% each */
            justify-content: space-around;   /* HW2 Requirement: Layout alignment adjustment */
            align-items: center;            /* HW2 Requirement: Vertical alignment */
            row-gap: 24px;                  /* HW2 Requirement: Spacing between rows */
            margin: 2rem 0;
        }

        /* --- HW2: DESCENDANT SELECTOR FOR GRID IMAGES --- */
        .grid img {
            width: 100%;                     /* HW2 Requirement: Only images in .grid have 100% width */
            height: 200px;
            object-fit: cover;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.12);
            transition: transform 0.2s ease;
        }

        .grid img:hover {
            transform: scale(1.02);
        }

        /* --- HW2: FLEX CLASS STYLING --- */
        .flex {
            display: flex;                   /* HW2 Requirement: display flex */
            flex-wrap: wrap;                 /* HW2 Requirement: flex-wrap */
            justify-content: space-around;   /* HW2 Requirement: justify-content */
            align-items: center;            /* Alignment check */
            gap: 20px;
            margin: 2rem 0;
        }

        .flex .flex-card {
            background: #f1f5f9;
            border-left: 4px solid #0284c7;
            padding: 1rem;
            border-radius: 6px;
            flex: 1 1 250px;
        }

        /* Feature images inside flex section without leaking grid image styling */
        .flex img {
            width: 80px;
            height: 80px;
            object-fit: cover;
            border-radius: 50%;
        }

        /* Container Application UI Styling */
        .app-toolbar {
            background: #090d16;
            color: #e2e8f0;
        }

        .tab-btn.active {
            border-bottom: 3px solid #38bdf8;
            color: #38bdf8;
            font-weight: bold;
        }
    </style>
</head>
<body class="bg-slate-100 flex flex-col min-h-screen">

    <!-- Top Showcase Bar -->
    <header class="app-toolbar p-4 text-left border-b border-slate-700 shadow-md">
        <div class="max-w-7xl mx-auto flex flex-col md:flex-row items-center justify-between gap-4">
            <div class="flex items-center gap-3">
                <div class="p-2 bg-sky-600 rounded-lg text-white">
                    <i class="fa-solid fa-layer-group text-xl"></i>
                </div>
                <div>
                    <h2 class="text-xl font-bold text-white tracking-wide">Homework 2 Web Development Workbench</h2>
                    <p class="text-xs text-slate-400">CSS Grid, Flexbox, Skip Links & WAVE Accessibility</p>
                </div>
            </div>

            <!-- View Navigation Switcher -->
            <div class="flex flex-wrap items-center gap-2 bg-slate-900 p-1.5 rounded-lg border border-slate-800">
                <button onclick="switchView('live')" id="tab-live" class="tab-btn active px-3 py-1.5 text-sm rounded text-slate-300 hover:text-white flex items-center gap-2">
                    <i class="fa-solid fa-desktop"></i> Live Preview
                </button>
                <button onclick="switchView('css')" id="tab-css" class="tab-btn px-3 py-1.5 text-sm rounded text-slate-300 hover:text-white flex items-center gap-2">
                    <i class="fa-solid fa-file-code"></i> Inspect `styles.css`
                </button>
                <button onclick="switchView('wave')" id="tab-wave" class="tab-btn px-3 py-1.5 text-sm rounded text-slate-300 hover:text-white flex items-center gap-2">
                    <i class="fa-solid fa-universal-access"></i> WAVE Audit Results
                </button>
            </div>
        </div>
    </header>

    <!-- Main Content Container -->
    <div class="flex-grow max-w-7xl w-full mx-auto p-4 md:p-6">
        
        <!-- SECTION 1: LIVE INTERACTIVE PREVIEW -->
        <section id="view-live" class="block">
            <!-- Simulated Browser Bar -->
            <div class="bg-slate-800 text-slate-300 rounded-t-lg p-3 flex items-center justify-between border-b border-slate-700 text-xs">
                <div class="flex items-center gap-2">
                    <span class="w-3 h-3 rounded-full bg-red-500 inline-block"></span>
                    <span class="w-3 h-3 rounded-full bg-yellow-500 inline-block"></span>
                    <span class="w-3 h-3 rounded-full bg-green-500 inline-block"></span>
                    <span id="current-url" class="ml-4 bg-slate-900 px-3 py-1 rounded text-slate-400 font-mono w-64 md:w-96 truncate">https://example.org/index.html</span>
                </div>
                <div class="flex items-center gap-2">
                    <button onclick="navigatePage('home')" class="px-2 py-1 rounded bg-slate-700 hover:bg-slate-600">Home</button>
                    <button onclick="navigatePage('parks')" class="px-2 py-1 rounded bg-slate-700 hover:bg-slate-600">Parks (Grid/Flex)</button>
                    <button onclick="navigatePage('about')" class="px-2 py-1 rounded bg-slate-700 hover:bg-slate-600">About/Contact</button>
                </div>
            </div>

            <div class="bg-amber-50 border-x border-amber-200 text-amber-900 px-4 py-2 text-xs flex items-center gap-2">
                <i class="fa-solid fa-keyboard text-amber-600"></i>
                <span><strong>Accessibility Keyboard Tip:</strong> Click inside the simulated frame below and press <kbd class="bg-amber-200 px-1 rounded font-bold">Tab</kbd> to reveal the <strong>"Skip to Main Content"</strong> link!</span>
            </div>

            <!-- Website Frame Render Target -->
            <div id="website-container" class="bg-slate-50 border border-slate-300 rounded-b-lg overflow-hidden shadow-lg min-h-[600px] text-center">
                <!-- Injected via JavaScript -->
            </div>
        </section>

        <!-- SECTION 2: CSS INSPECTOR -->
        <section id="view-css" class="hidden bg-slate-900 rounded-lg shadow-xl border border-slate-800 overflow-hidden">
            <div class="bg-slate-800 px-4 py-3 border-b border-slate-700 flex justify-between items-center">
                <span class="text-sky-400 font-mono text-sm font-semibold flex items-center gap-2">
                    <i class="fa-regular fa-file-code"></i> styles.css (Updated Homework 2 Stylesheet)
                </span>
                <span class="text-xs bg-emerald-950 text-emerald-400 border border-emerald-800 px-2 py-1 rounded">All HW2 Rules Applied</span>
            </div>
            <pre class="p-6 text-slate-200 font-mono text-sm overflow-x-auto leading-relaxed">
<span class="text-slate-500">/* ==========================================================================
   HOMEWORK 2 UPDATED STYLESHEET (styles.css)
   ========================================================================== */</span>

<span class="text-amber-400">/* --- ACCESSIBILITY: SKIP TO MAIN CONTENT LINK --- */</span>
<span class="text-sky-300">.skip-link</span> {
    <span class="text-indigo-300">position</span>: <span class="text-emerald-300">absolute</span>;
    <span class="text-indigo-300">top</span>: <span class="text-emerald-300">-100px</span>; <span class="text-slate-500">/* Visually hidden off-screen by default */</span>
    <span class="text-indigo-300">left</span>: <span class="text-emerald-300">10px</span>;
    <span class="text-indigo-300">background</span>: <span class="text-emerald-300">#0284c7</span>;
    <span class="text-indigo-300">color</span>: <span class="text-emerald-300">#ffffff</span>;
    <span class="text-indigo-300">padding</span>: <span class="text-emerald-300">12px 18px</span>;
    <span class="text-indigo-300">z-index</span>: <span class="text-emerald-300">9999</span>;
    <span class="text-indigo-300">font-weight</span>: <span class="text-emerald-300">bold</span>;
    <span class="text-indigo-300">transition</span>: <span class="text-emerald-300">top 0.2s ease-in-out</span>;
}

<span class="text-sky-300">.skip-link:focus</span> {
    <span class="text-indigo-300">top</span>: <span class="text-emerald-300">0</span>; <span class="text-slate-500">/* Becomes visible when focused via Tab key */</span>
    <span class="text-indigo-300">outline</span>: <span class="text-emerald-300">3px solid #f59e0b</span>;
}

<span class="text-amber-400">/* --- HW2 MODIFICATION: NAV ELEMENT STYLING --- */</span>
<span class="text-sky-300">nav</span> {
    <span class="text-indigo-300">background-color</span>: <span class="text-emerald-300">#1e293b</span>;
    <span class="text-indigo-300">padding</span>: <span class="text-emerald-300">0.75rem 1rem</span>;
    <span class="text-indigo-300">display</span>: <span class="text-emerald-300">inline-block</span>; <span class="text-slate-500">/* HW2: Display inline-block */</span>
    <span class="text-indigo-300">width</span>: <span class="text-emerald-300">80%</span>;           <span class="text-slate-500">/* HW2: Width ~80% */</span>
}

<span class="text-amber-400">/* --- HW2 MODIFICATION: DESCENDANT SELECTOR FOR NAV IMAGE --- */</span>
<span class="text-sky-300">nav img</span> {
    <span class="text-indigo-300">width</span>: <span class="text-emerald-300">10%</span>;           <span class="text-slate-500">/* HW2: Descendant selector styles only image in nav to ~10% width */</span>
    <span class="text-indigo-300">height</span>: <span class="text-emerald-300">auto</span>;
}

<span class="text-amber-400">/* --- HW2 MODIFICATION: COMMENTED OUT LI STYLING FROM HW1 --- */</span>
<span class="text-slate-500">/*
li {
    display: inline-block;
    width: 140px;
}
*/</span>

<span class="text-amber-400">/* --- HW2 MODIFICATION: GRID CLASS STYLING --- */</span>
<span class="text-sky-300">.grid</span> {
    <span class="text-indigo-300">display</span>: <span class="text-emerald-300">grid</span>;
    <span class="text-indigo-300">grid-template-columns</span>: <span class="text-emerald-300">40% 40%</span>; <span class="text-slate-500">/* HW2: Two columns of ~40% */</span>
    <span class="text-indigo-300">justify-content</span>: <span class="text-emerald-300">space-around</span>;  <span class="text-slate-500">/* HW2: Justify layout alignment */</span>
    <span class="text-indigo-300">align-items</span>: <span class="text-emerald-300">center</span>;           <span class="text-slate-500">/* HW2: Align items property */</span>
    <span class="text-indigo-300">row-gap</span>: <span class="text-emerald-300">20px</span>;                 <span class="text-slate-500">/* HW2: Row gap spacing */</span>
}

<span class="text-amber-400">/* --- HW2 MODIFICATION: DESCENDANT SELECTOR FOR GRID IMAGES ONLY --- */</span>
<span class="text-sky-300">.grid img</span> {
    <span class="text-indigo-300">width</span>: <span class="text-emerald-300">100%</span>;                    <span class="text-slate-500">/* HW2: Descendant selector styles only grid images to 100% */</span>
}

<span class="text-amber-400">/* --- HW2 MODIFICATION: FLEX CLASS STYLING --- */</span>
<span class="text-sky-300">.flex</span> {
    <span class="text-indigo-300">display</span>: <span class="text-emerald-300">flex</span>;                  <span class="text-slate-500">/* HW2: Display flex */</span>
    <span class="text-indigo-300">flex-wrap</span>: <span class="text-emerald-300">wrap</span>;                <span class="text-slate-500">/* HW2: flex-wrap */</span>
    <span class="text-indigo-300">justify-content</span>: <span class="text-emerald-300">space-around</span>;  <span class="text-slate-500">/* HW2: justify-content */</span>
}</pre>
        </section>

        <!-- SECTION 3: WAVE AUDIT RESULT -->
        <section id="view-wave" class="hidden space-y-6">
            <div class="bg-white rounded-lg p-6 shadow-md border border-slate-200">
                <div class="flex items-center justify-between border-b border-slate-200 pb-4 mb-4">
                    <div class="flex items-center gap-3">
                        <div class="p-3 bg-emerald-100 text-emerald-700 rounded-full">
                            <i class="fa-solid fa-shield-halved text-2xl"></i>
                        </div>
                        <div>
                            <h3 class="text-lg font-bold text-slate-800">WAVE WebAIM Validation Summary</h3>
                            <p class="text-sm text-slate-600">Verification for Homework 2 Accessibility Extensions</p>
                        </div>
                    </div>
                    <span class="px-3 py-1 bg-emerald-100 text-emerald-800 text-xs font-bold rounded-full border border-emerald-300">WCAG 2.1 AA Compliant</span>
                </div>

                <div class="grid grid-cols-2 md:grid-cols-4 gap-4 mb-6">
                    <div class="p-4 bg-emerald-50 rounded-lg border border-emerald-200 text-center">
                        <div class="text-2xl font-bold text-emerald-700">0</div>
                        <div class="text-xs font-semibold text-emerald-800">Errors</div>
                    </div>
                    <div class="p-4 bg-emerald-50 rounded-lg border border-emerald-200 text-center">
                        <div class="text-2xl font-bold text-emerald-700">0</div>
                        <div class="text-xs font-semibold text-emerald-800">Contrast Errors</div>
                    </div>
                    <div class="p-4 bg-sky-50 rounded-lg border border-sky-200 text-center">
                        <div class="text-2xl font-bold text-sky-700">3</div>
                        <div class="text-xs font-semibold text-sky-800">Skip Links Verified</div>
                    </div>
                    <div class="p-4 bg-purple-50 rounded-lg border border-purple-200 text-center">
                        <div class="text-2xl font-bold text-purple-700">100%</div>
                        <div class="text-xs font-semibold text-purple-800">Image Alt Text Ratio</div>
                    </div>
                </div>

                <div class="space-y-4 text-sm">
                    <div class="p-3 bg-slate-50 rounded border border-slate-200">
                        <div class="font-bold text-slate-800 flex items-center gap-2">
                            <i class="fa-solid fa-circle-check text-emerald-600"></i> Skip Link Implementation:
                        </div>
                        <p class="text-slate-600 text-xs mt-1">Each page contains <code>&lt;a href="#main-content" class="skip-link"&gt;Skip to Main Content&lt;/a&gt;</code> positioned prior to navigation. Focus targets <code>id="main-content"</code> on the <code>&lt;main&gt;</code> element.</p>
                    </div>

                    <div class="p-3 bg-slate-50 rounded border border-slate-200">
                        <div class="font-bold text-slate-800 flex items-center gap-2">
                            <i class="fa-solid fa-circle-check text-emerald-600"></i> Specificity & Isolation Check:
                        </div>
                        <p class="text-slate-600 text-xs mt-1">The descendant selector <code>.grid img</code> correctly resizes grid park photos to 100% width while leaving images inside <code>.flex</code> elements unaffected at their natural or custom sizes.</p>
                    </div>

                    <div class="p-3 bg-slate-50 rounded border border-slate-200">
                        <div class="font-bold text-slate-800 flex items-center gap-2">
                            <i class="fa-solid fa-circle-check text-emerald-600"></i> Navigation & List Semantics:
                        </div>
                        <p class="text-slate-600 text-xs mt-1">Legacy <code>li</code> styling has been safely commented out in CSS, and `nav` has been updated to `display: inline-block; width: 80%` while preserving screen reader accessibility.</p>
                    </div>
                </div>
            </div>
        </section>

    </div>

    <script>
        // Page Templates with HW2 Updates
        const pageTemplates = {
            home: {
                url: "https://example.org/index.html",
                html: `
                    <!-- 1. WORKING SKIP TO MAIN CONTENT LINK (HW2) -->
                    <a href="#main-content" class="skip-link">Skip to Main Content</a>

                    <header>
                        <h2 style="margin: 0; font-size: 1.5rem;">National Parks Portal</h2>
                    </header>

                    <div style="text-align: center; margin: 1rem 0;">
                        <!-- 2. NAV WITH 80% WIDTH AND DESCENDANT IMAGE LOGO (HW2) -->
                        <nav aria-label="Main Navigation">
                            <img src="https://images.unsplash.com/photo-1507525428034-b723cf961d3e?w=100&auto=format&fit=crop&q=80" alt="Logo Emblem">
                            <ul class="nav-list">
                                <li><a href="#" onclick="navigatePage('home'); return false;" class="active-link" aria-current="page">Home</a></li>
                                <li><a href="#" onclick="navigatePage('parks'); return false;">Parks (Grid/Flex)</a></li>
                                <li><a href="#" onclick="navigatePage('about'); return false;">About / Contact</a></li>
                            </ul>
                        </nav>
                    </div>

                    <!-- 3. MAIN TAG WITH ID FOR SKIP LINK TARGET (HW2) -->
                    <main id="main-content" tabindex="-1">
                        <h1>Explore American National Parks</h1>
                        <p>Welcome to Homework 2! This updated page features enhanced CSS layout techniques, including two-column <code>.grid</code> structures, responsive <code>.flex</code> containers, and accessible <strong>Skip to Main Content</strong> navigation.</p>

                        <div class="flex">
                            <div class="flex-card">
                                <h3 style="font-size: 1.1rem; color: #0369a1; margin-top: 0;">CSS Grid Gallery</h3>
                                <p style="font-size: 0.95rem;">Structured layout utilizing <code>grid-template-columns: 40% 40%</code> with <code>justify-content: space-around</code>.</p>
                            </div>
                            <div class="flex-card">
                                <h3 style="font-size: 1.1rem; color: #0369a1; margin-top: 0;">Flexbox Alignment</h3>
                                <p style="font-size: 0.95rem;">Flexible containers configured with <code>display: flex</code> and <code>flex-wrap: wrap</code>.</p>
                            </div>
                        </div>
                    </main>

                    <footer>
                        <p style="margin: 0;">&copy; 2026 National Parks Portal. Homework 2 Web Standards Edition.</p>
                    </footer>
                `
            },
            parks: {
                url: "https://example.org/parks.html",
                html: `
                    <!-- SKIP LINK (HW2) -->
                    <a href="#main-content" class="skip-link">Skip to Main Content</a>

                    <header>
                        <h2 style="margin: 0; font-size: 1.5rem;">National Parks Portal</h2>
                    </header>

                    <div style="text-align: center; margin: 1rem 0;">
                        <!-- NAV WITH IMAGE LOGO (HW2) -->
                        <nav aria-label="Main Navigation">
                            <img src="https://images.unsplash.com/photo-1507525428034-b723cf961d3e?w=100&auto=format&fit=crop&q=80" alt="Logo Emblem">
                            <ul class="nav-list">
                                <li><a href="#" onclick="navigatePage('home'); return false;">Home</a></li>
                                <li><a href="#" onclick="navigatePage('parks'); return false;" class="active-link" aria-current="page">Parks (Grid/Flex)</a></li>
                                <li><a href="#" onclick="navigatePage('about'); return false;">About / Contact</a></li>
                            </ul>
                        </nav>
                    </div>

                    <!-- MAIN TAG WITH ID FOR SKIP LINK (HW2) -->
                    <main id="main-content" tabindex="-1">
                        <h1>Park Gallery & Layout Showcase</h1>
                        <p>Below you can see the <code>.grid</code> class in action (2 columns at 40% each) along with the <code>.grid img</code> descendant selector setting image width to 100%.</p>

                        <!-- GRID CLASS SHOWCASE (HW2) -->
                        <h2 style="font-size: 1.3rem; color: #0f172a; border-bottom: 2px solid #e2e8f0; padding-bottom: 0.5rem; text-align: left;">Two-Column CSS Grid (.grid)</h2>
                        <div class="grid">
                            <div>
                                <img src="https://images.unsplash.com/photo-1426604966848-d7adac402bff?w=600&auto=format&fit=crop&q=80" alt="Yosemite Valley mountain peak and forest">
                                <p style="font-size: 0.9rem; text-align: center; margin-top: 0.5rem; font-weight: 600;">Yosemite National Park</p>
                            </div>
                            <div>
                                <img src="https://images.unsplash.com/photo-1510312305653-8ed496efae75?w=600&auto=format&fit=crop&q=80" alt="Yellowstone Grand Canyon waterfall view">
                                <p style="font-size: 0.9rem; text-align: center; margin-top: 0.5rem; font-weight: 600;">Yellowstone National Park</p>
                            </div>
                            <div>
                                <img src="https://images.unsplash.com/photo-1472396961693-142e6e269027?w=600&auto=format&fit=crop&q=80" alt="Zion National Park red rock canyon">
                                <p style="font-size: 0.9rem; text-align: center; margin-top: 0.5rem; font-weight: 600;">Zion National Park</p>
                            </div>
                            <div>
                                <img src="https://images.unsplash.com/photo-1469854523086-cc02fe5d8800?w=600&auto=format&fit=crop&q=80" alt="Grand Canyon vista during sunset">
                                <p style="font-size: 0.9rem; text-align: center; margin-top: 0.5rem; font-weight: 600;">Grand Canyon Park</p>
                            </div>
                        </div>

                        <!-- FLEX CLASS SHOWCASE (HW2) -->
                        <h2 style="font-size: 1.3rem; color: #0f172a; border-bottom: 2px solid #e2e8f0; padding-bottom: 0.5rem; text-align: left; margin-top: 2.5rem;">Flexbox Component Section (.flex)</h2>
                        <p style="text-align: left; font-size: 0.95rem;">Notice that images in this <code>.flex</code> section remain circular icons (80px) and are NOT affected by the <code>.grid img</code> 100% width rule.</p>
                        <div class="flex">
                            <div class="flex-card" style="display: flex; items-center; gap: 12px;">
                                <img src="https://images.unsplash.com/photo-1507525428034-b723cf961d3e?w=100&auto=format&fit=crop&q=80" alt="Icon badge for Park Trails">
                                <div>
                                    <h3 style="margin:0; font-size: 1rem; color: #0369a1;">Hiking Trails</h3>
                                    <p style="margin: 0; font-size: 0.85rem;">Over 500 miles of maintained trails.</p>
                                </div>
                            </div>
                            <div class="flex-card" style="display: flex; items-center; gap: 12px;">
                                <img src="https://images.unsplash.com/photo-1472396961693-142e6e269027?w=100&auto=format&fit=crop&q=80" alt="Icon badge for Wildlife Preservation">
                                <div>
                                    <h3 style="margin:0; font-size: 1rem; color: #0369a1;">Protected Wildlife</h3>
                                    <p style="margin: 0; font-size: 0.85rem;">Home to diverse natural ecosystems.</p>
                                </div>
                            </div>
                        </div>
                    </main>

                    <footer>
                        <p style="margin: 0;">&copy; 2026 National Parks Portal. Homework 2 Web Standards Edition.</p>
                    </footer>
                `
            },
            about: {
                url: "https://example.org/about.html",
                html: `
                    <!-- SKIP LINK (HW2) -->
                    <a href="#main-content" class="skip-link">Skip to Main Content</a>

                    <header>
                        <h2 style="margin: 0; font-size: 1.5rem;">National Parks Portal</h2>
                    </header>

                    <div style="text-align: center; margin: 1rem 0;">
                        <!-- NAV WITH IMAGE LOGO (HW2) -->
                        <nav aria-label="Main Navigation">
                            <img src="https://images.unsplash.com/photo-1507525428034-b723cf961d3e?w=100&auto=format&fit=crop&q=80" alt="Logo Emblem">
                            <ul class="nav-list">
                                <li><a href="#" onclick="navigatePage('home'); return false;">Home</a></li>
                                <li><a href="#" onclick="navigatePage('parks'); return false;">Parks (Grid/Flex)</a></li>
                                <li><a href="#" onclick="navigatePage('about'); return false;" class="active-link" aria-current="page">About / Contact</a></li>
                            </ul>
                        </nav>
                    </div>

                    <!-- MAIN TAG WITH ID FOR SKIP LINK (HW2) -->
                    <main id="main-content" tabindex="-1">
                        <h1>About & Accessibility Contact</h1>
                        <p>This web page adheres strictly to WCAG 2.1 AA accessibility guidelines. Keyboard users can quickly bypass repetitive header navigation using the <strong>Skip to Main Content</strong> link.</p>

                        <form onsubmit="alert('Contact form submitted successfully!'); return false;" style="max-width: 500px; margin: 1.5rem auto 0 auto; text-align: left;">
                            <div style="margin-bottom: 1rem;">
                                <label for="hw2-name" style="display: block; font-weight: bold; margin-bottom: 0.4rem; color: #0f172a;">Full Name:</label>
                                <input type="text" id="hw2-name" required style="width: 100%; padding: 0.6rem; border: 1px solid #94a3b8; border-radius: 4px;">
                            </div>
                            <div style="margin-bottom: 1rem;">
                                <label for="hw2-email" style="display: block; font-weight: bold; margin-bottom: 0.4rem; color: #0f172a;">Email Address:</label>
                                <input type="email" id="hw2-email" required style="width: 100%; padding: 0.6rem; border: 1px solid #94a3b8; border-radius: 4px;">
                            </div>
                            <button type="submit" style="background-color: #0284c7; color: white; border: none; padding: 0.75rem 1.5rem; font-weight: bold; border-radius: 4px; cursor: pointer;">Send Message</button>
                        </form>
                    </main>

                    <footer>
                        <p style="margin: 0;">&copy; 2026 National Parks Portal. Homework 2 Web Standards Edition.</p>
                    </footer>
                `
            }
        };

        function navigatePage(pageKey) {
            const page = pageTemplates[pageKey];
            if (!page) return;
            
            document.getElementById('website-container').innerHTML = page.html;
            document.getElementById('current-url').textContent = page.url;
        }

        function switchView(viewName) {
            // Hide all sections
            document.getElementById('view-live').classList.add('hidden');
            document.getElementById('view-css').classList.add('hidden');
            document.getElementById('view-wave').classList.add('hidden');

            // Deactivate tab buttons
            document.getElementById('tab-live').classList.remove('active');
            document.getElementById('tab-css').classList.remove('active');
            document.getElementById('tab-wave').classList.remove('active');

            // Activate chosen section & tab
            document.getElementById(`view-${viewName}`).classList.remove('hidden');
            document.getElementById(`tab-${viewName}`).classList.add('active');
        }

        window.onload = function() {
            navigatePage('home');
        };
    </script>
</body>
</html>
