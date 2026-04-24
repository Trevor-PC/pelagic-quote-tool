<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pelagic Automations — Get Your Quote</title>

    <!-- Tailwind CSS via CDN (no build step) -->
    <script src="https://cdn.tailwindcss.com"></script>

    <!-- Google Font: Inter -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">

    <style>
        body {
            font-family: 'Inter', sans-serif;
            background: #0a0a0f;
            color: #e5e7eb;
        }
        ::-webkit-scrollbar { width: 8px; }
        ::-webkit-scrollbar-track { background: #0a0a0f; }
        ::-webkit-scrollbar-thumb { background: #1f2937; border-radius: 4px; }

        /* Tier selection card */
        .tier-card {
            transition: all 0.2s ease;
            border: 2px solid #1f2937;
            background: #151522;
        }
        .tier-card:hover {
            border-color: #3b82f6;
            transform: translateY(-2px);
        }
        .tier-card.selected {
            border-color: #2563eb;
            background: linear-gradient(135deg, rgba(37, 99, 235, 0.15) 0%, rgba(37, 99, 235, 0.05) 100%);
            box-shadow: 0 0 0 1px #2563eb, 0 10px 40px -10px rgba(37, 99, 235, 0.4);
        }
        .tier-card.selected .tier-select-indicator {
            background: #2563eb;
            border-color: #2563eb;
        }
        .tier-card.selected .tier-select-indicator::after {
            content: '✓';
            color: white;
            font-weight: bold;
            font-size: 0.75rem;
        }

        /* Primary button */
        .btn-primary {
            background: linear-gradient(135deg, #2563eb 0%, #1d4ed8 100%);
            box-shadow: 0 4px 20px -5px rgba(37, 99, 235, 0.5);
            transition: all 0.2s ease;
        }
        .btn-primary:hover:not(:disabled) {
            transform: translateY(-1px);
            box-shadow: 0 8px 30px -5px rgba(37, 99, 235, 0.7);
        }
        .btn-primary:disabled {
            opacity: 0.5;
            cursor: not-allowed;
            background: #1f2937;
            box-shadow: none;
        }

        /* Fade in */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .fade-in { animation: fadeIn 0.4s ease forwards; }

        /* Spinner */
        .spinner {
            border: 3px solid #1f2937;
            border-top: 3px solid #2563eb;
            border-radius: 50%;
            width: 30px;
            height: 30px;
            animation: spin 1s linear infinite;
        }
        @keyframes spin { to { transform: rotate(360deg); } }

        /* Inputs */
        .form-input {
            background: #151522;
            border: 1px solid #2a2a3e;
            color: #e5e7eb;
            transition: border-color 0.2s;
        }
        .form-input:focus {
            outline: none;
            border-color: #2563eb;
            box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.2);
        }
        .form-input::placeholder { color: #4b5563; }
    </style>
</head>
<body>

    <!-- ================================
         HEADER
         ================================ -->
    <header class="border-b border-gray-800 sticky top-0 bg-[#0a0a0f]/90 backdrop-blur-lg z-50">
        <div class="max-w-6xl mx-auto px-4 py-4 flex items-center justify-between">
            <div class="flex items-center gap-3">
                <!-- Logo image. If assets/logo.png doesn't exist, text fallback shows instead. -->
                <img src="assets/logo.png" alt="Pelagic Automations" class="h-10 w-auto"
                     onerror="this.style.display='none'; document.getElementById('logo-text').style.display='block';">
                <div id="logo-text" class="text-xl font-bold tracking-tight" style="display:none;">
                    <span class="text-blue-500">Pelagic</span> Automations
                </div>
            </div>
        </div>
    </header>

    <!-- ================================
         MAIN CONTENT
         ================================ -->
    <main class="max-w-6xl mx-auto px-4 py-12 pb-40">

        <!-- HERO -->
        <section id="hero" class="text-center mb-16 fade-in">
            <div class="inline-block px-4 py-1 mb-4 rounded-full bg-blue-500/10 border border-blue-500/20 text-blue-400 text-sm font-medium">
                ⚡ Instant quote &middot; Transparent pricing
            </div>
            <h1 class="text-4xl md:text-5xl font-bold tracking-tight mb-4">
                Get an instant quote for your<br>
                <span class="bg-gradient-to-r from-blue-400 to-blue-600 bg-clip-text text-transparent">automation project</span>
            </h1>
            <p class="text-lg text-gray-400 max-w-2xl mx-auto">
                Choose the services and tiers you're interested in. See your estimate instantly. Takes about 2 minutes.
            </p>
        </section>

        <!-- LOADING STATE -->
        <div id="loading" class="flex items-center justify-center py-20">
            <div class="spinner"></div>
            <span class="ml-3 text-gray-400">Loading services...</span>
        </div>

        <!-- ERROR STATE -->
        <div id="error" class="hidden bg-red-950/50 border border-red-900 rounded-xl p-6 text-center">
            <p class="text-red-400 font-medium">Couldn't load services</p>
            <p class="text-gray-400 text-sm mt-2" id="error-message"></p>
            <button onclick="location.reload()" class="mt-4 px-4 py-2 bg-red-900/50 hover:bg-red-900 rounded-lg text-sm">Retry</button>
        </div>

        <!-- SERVICES (populated by JS) -->
        <div id="services-container" class="hidden space-y-10"></div>

        <!-- CONTACT FORM -->
        <section id="contact-section" class="hidden mt-16">
            <div class="max-w-2xl mx-auto">
                <h2 class="text-2xl font-bold mb-2">Your contact details</h2>
                <p class="text-gray-400 mb-8">We'll follow up within 1 business day with a detailed quote.</p>

                <form id="quote-form" class="space-y-5">
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div>
                            <label class="block text-sm font-medium mb-2">Full Name *</label>
                            <input type="text" name="full_name" required class="form-input w-full px-4 py-3 rounded-lg">
                        </div>
                        <div>
                            <label class="block text-sm font-medium mb-2">Email *</label>
                            <input type="email" name="email" required class="form-input w-full px-4 py-3 rounded-lg">
                        </div>
                    </div>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div>
                            <label class="block text-sm font-medium mb-2">Contact Number *</label>
                            <input type="tel" name="phone" required class="form-input w-full px-4 py-3 rounded-lg">
                        </div>
                        <div>
                            <label class="block text-sm font-medium mb-2">Company Name *</label>
                            <input type="text" name="company" required class="form-input w-full px-4 py-3 rounded-lg">
                        </div>
                    </div>

                    <div>
                        <label class="block text-sm font-medium mb-2">Website URL</label>
                        <input type="url" name="website" placeholder="https://" class="form-input w-full px-4 py-3 rounded-lg">
                    </div>

                    <div>
                        <label class="block text-sm font-medium mb-2">Tell us about your project</label>
                        <textarea name="project_description" rows="4" class="form-input w-full px-4 py-3 rounded-lg" placeholder="What are you looking to automate? What's your timeline?"></textarea>
                    </div>

                    <button type="submit" id="submit-btn" class="btn-primary w-full py-4 rounded-lg font-semibold text-white text-lg" disabled>
                        Select at least one service to continue
                    </button>

                    <p id="error-submit" class="hidden text-red-400 text-sm text-center"></p>
                </form>
            </div>
        </section>

        <!-- SUCCESS STATE -->
        <section id="success-section" class="hidden text-center py-20 fade-in">
            <div class="inline-flex items-center justify-center w-20 h-20 rounded-full bg-blue-500/10 border border-blue-500/30 mb-6">
                <svg class="w-10 h-10 text-blue-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
                </svg>
            </div>
            <h2 class="text-3xl font-bold mb-3">Got it — we'll be in touch</h2>
            <p class="text-gray-400 max-w-md mx-auto">
                Thank you for reaching out. We've received your quote request and will respond within 1 business day.
            </p>
        </section>
    </main>

    <!-- ================================
         STICKY RUNNING TOTAL
         ================================ -->
    <div id="total-bar" class="fixed bottom-0 left-0 right-0 bg-[#0a0a0f]/95 backdrop-blur-lg border-t border-gray-800 p-4 z-40 hidden">
        <div class="max-w-6xl mx-auto flex items-center justify-between flex-wrap gap-4">
            <div>
                <div class="text-sm text-gray-400">Your estimate</div>
                <div class="flex items-baseline gap-3 flex-wrap">
                    <span class="text-2xl font-bold text-white" id="total-onetime">R 0</span>
                    <span class="text-gray-400" id="total-monthly-wrapper" style="display:none;">
                        <span class="text-sm">+</span>
                        <span class="text-lg font-semibold" id="total-monthly">R 0</span>
                        <span class="text-sm">/month</span>
                    </span>
                </div>
            </div>
            <div class="text-sm text-gray-500">
                <span id="selection-count">No services selected</span>
            </div>
        </div>
    </div>

    <!-- ================================
         JAVASCRIPT
         ================================ -->
    <script>
        /* =============================================
           CONFIG — Edit these when needed
           ============================================= */
        const CSV_URL = 'https://docs.google.com/spreadsheets/d/e/2PACX-1vQMFgDp_4UlXq90T4trfyjS2VayG4X-m9Gzuf9p0suLFid7f2ZUnnu4Xya4Job-ri1rKC7b4YCbCgGy/pub?gid=0&single=true&output=csv';
        const WEBHOOK_URL = 'YOUR_N8N_WEBHOOK_URL_HERE'; // Will be set in Stage 6

        /* =============================================
           STATE
           ============================================= */
        let services = [];        // Grouped services
        let selections = {};      // { service_group_id: tier_id }

        /* =============================================
           CSV PARSER (handles quoted fields)
           ============================================= */
        function parseCSV(text) {
            const rows = [];
            let row = [];
            let field = '';
            let inQuotes = false;
            for (let i = 0; i < text.length; i++) {
                const c = text[i];
                const n = text[i + 1];
                if (c === '"') {
                    if (inQuotes && n === '"') { field += '"'; i++; }
                    else { inQuotes = !inQuotes; }
                } else if (c === ',' && !inQuotes) {
                    row.push(field); field = '';
                } else if ((c === '\n' || c === '\r') && !inQuotes) {
                    if (c === '\r' && n === '\n') i++;
                    row.push(field);
                    if (row.some(f => f.length > 0)) rows.push(row);
                    row = []; field = '';
                } else {
                    field += c;
                }
            }
            if (field.length > 0 || row.length > 0) {
                row.push(field);
                if (row.some(f => f.length > 0)) rows.push(row);
            }
            return rows;
        }

        function csvToObjects(csvText) {
            const rows = parseCSV(csvText);
            if (rows.length < 2) return [];
            const headers = rows[0].map(h => h.trim());
            return rows.slice(1).map(r => {
                const o = {};
                headers.forEach((h, i) => { o[h] = (r[i] || '').trim(); });
                return o;
            });
        }

        /* =============================================
           LOAD SERVICES FROM GOOGLE SHEET
           ============================================= */
        async function loadServices() {
            try {
                const response = await fetch(CSV_URL);
                if (!response.ok) throw new Error('HTTP ' + response.status);
                const csvText = await response.text();
                const rows = csvToObjects(csvText);

                const active = rows
                    .filter(r => r.active && r.active.toUpperCase() === 'TRUE')
                    .sort((a, b) => parseInt(a.sort_order || 0) - parseInt(b.sort_order || 0));

                const grouped = {};
                active.forEach(row => {
                    const gk = row.service_group;
                    if (!grouped[gk]) {
                        grouped[gk] = {
                            id: gk,
                            name: row.service_name,
                            category: row.category,
                            tiers: []
                        };
                    }
                    grouped[gk].tiers.push({
                        id: row.id,
                        tier: row.tier,
                        description: row.tier_description,
                        oneTime: parseFloat(row.one_time_price) || 0,
                        monthly: parseFloat(row.monthly_price) || 0
                    });
                });

                services = Object.values(grouped);
                if (services.length === 0) throw new Error('No active services found in the sheet.');

                renderServices();
                document.getElementById('loading').classList.add('hidden');
                document.getElementById('services-container').classList.remove('hidden');
                document.getElementById('contact-section').classList.remove('hidden');
                document.getElementById('total-bar').classList.remove('hidden');
                updateTotal();

            } catch (err) {
                console.error('Load error:', err);
                document.getElementById('loading').classList.add('hidden');
                document.getElementById('error').classList.remove('hidden');
                document.getElementById('error-message').textContent = err.message;
            }
        }

        /* =============================================
           RENDER
           ============================================= */
        function formatZAR(amount) {
            return 'R ' + amount.toLocaleString('en-ZA', { maximumFractionDigits: 0 });
        }

        function renderServices() {
            const container = document.getElementById('services-container');
            container.innerHTML = services.map((service, idx) => `
                <div class="fade-in" style="animation-delay: ${idx * 0.05}s">
                    <div class="flex items-baseline justify-between mb-4 flex-wrap gap-2">
                        <h3 class="text-xl font-bold">${escapeHTML(service.name)}</h3>
                        <span class="text-xs text-gray-500 uppercase tracking-wider">${escapeHTML(service.category)}</span>
                    </div>
                    <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                        ${service.tiers.map(tier => `
                            <div class="tier-card rounded-xl p-6 cursor-pointer" data-service="${service.id}" data-tier-id="${tier.id}">
                                <div class="flex items-start justify-between mb-3">
                                    <span class="text-sm font-bold uppercase tracking-wider text-blue-400">${escapeHTML(tier.tier)}</span>
                                    <div class="tier-select-indicator w-5 h-5 rounded-full border-2 border-gray-600 flex items-center justify-center"></div>
                                </div>
                                <div class="mb-4">
                                    <div class="text-2xl font-bold">${formatZAR(tier.oneTime)}</div>
                                    ${tier.monthly > 0
                                        ? `<div class="text-sm text-gray-400 mt-1">+ ${formatZAR(tier.monthly)} / month</div>`
                                        : `<div class="text-sm text-gray-500 mt-1">one-time</div>`}
                                </div>
                                <p class="text-sm text-gray-400 leading-relaxed">${escapeHTML(tier.description)}</p>
                            </div>
                        `).join('')}
                    </div>
                </div>
            `).join('');
            container.querySelectorAll('.tier-card').forEach(c => c.addEventListener('click', handleTierClick));
        }

        function escapeHTML(s) {
            return String(s).replace(/[&<>"']/g, m => ({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'})[m]);
        }

        /* =============================================
           TIER SELECTION
           ============================================= */
        function handleTierClick(e) {
            const card = e.currentTarget;
            const serviceId = card.dataset.service;
            const tierId = card.dataset.tierId;

            document.querySelectorAll(`[data-service="${serviceId}"]`).forEach(c => c.classList.remove('selected'));

            if (selections[serviceId] === tierId) {
                delete selections[serviceId];
            } else {
                selections[serviceId] = tierId;
                card.classList.add('selected');
            }
            updateTotal();
        }

        /* =============================================
           TOTALS
           ============================================= */
        function getSelectedDetails() {
            const out = [];
            Object.entries(selections).forEach(([sid, tid]) => {
                const service = services.find(s => s.id === sid);
                const tier = service.tiers.find(t => t.id === tid);
                out.push({
                    service_id: sid,
                    service_name: service.name,
                    tier: tier.tier,
                    tier_id: tier.id,
                    tier_description: tier.description,
                    one_time: tier.oneTime,
                    monthly: tier.monthly
                });
            });
            return out;
        }

        function updateTotal() {
            const selected = getSelectedDetails();
            const totalOneTime = selected.reduce((s, x) => s + x.one_time, 0);
            const totalMonthly = selected.reduce((s, x) => s + x.monthly, 0);

            document.getElementById('total-onetime').textContent = formatZAR(totalOneTime);
            document.getElementById('total-monthly').textContent = formatZAR(totalMonthly);
            document.getElementById('total-monthly-wrapper').style.display = totalMonthly > 0 ? '' : 'none';

            const n = selected.length;
            document.getElementById('selection-count').textContent =
                n === 0 ? 'No services selected' : n === 1 ? '1 service selected' : `${n} services selected`;

            const btn = document.getElementById('submit-btn');
            if (n === 0) {
                btn.disabled = true;
                btn.textContent = 'Select at least one service to continue';
            } else {
                btn.disabled = false;
                btn.textContent = 'Get my quote →';
            }
        }

        /* =============================================
           FORM SUBMISSION
           ============================================= */
        document.getElementById('quote-form').addEventListener('submit', async (e) => {
            e.preventDefault();
            const btn = document.getElementById('submit-btn');
            const errEl = document.getElementById('error-submit');
            errEl.classList.add('hidden');
            btn.disabled = true;
            btn.textContent = 'Submitting...';

            const fd = new FormData(e.target);
            const selected = getSelectedDetails();
            const totalOneTime = selected.reduce((s, x) => s + x.one_time, 0);
            const totalMonthly = selected.reduce((s, x) => s + x.monthly, 0);

            const payload = {
                contact: {
                    full_name: fd.get('full_name'),
                    email: fd.get('email'),
                    phone: fd.get('phone'),
                    company: fd.get('company'),
                    website: fd.get('website') || '',
                    project_description: fd.get('project_description') || ''
                },
                selected_services: selected,
                totals: { one_time: totalOneTime, monthly: totalMonthly, currency: 'ZAR' },
                submitted_at: new Date().toISOString(),
                source: 'pelagic-quote-tool-v1'
            };

            try {
                if (WEBHOOK_URL.startsWith('YOUR_')) {
                    // Webhook not configured yet — just log payload so you can see it in DevTools console
                    console.log('[Pelagic] Webhook not configured. Payload:', payload);
                    await new Promise(r => setTimeout(r, 700));
                } else {
                    const res = await fetch(WEBHOOK_URL, {
                        method: 'POST',
                        headers: { 'Content-Type': 'application/json' },
                        body: JSON.stringify(payload)
                    });
                    if (!res.ok) throw new Error('Server returned ' + res.status);
                }

                // Show success
                document.getElementById('hero').classList.add('hidden');
                document.getElementById('services-container').classList.add('hidden');
                document.getElementById('contact-section').classList.add('hidden');
                document.getElementById('total-bar').classList.add('hidden');
                document.getElementById('success-section').classList.remove('hidden');
                window.scrollTo({ top: 0, behavior: 'smooth' });

            } catch (err) {
                console.error(err);
                errEl.textContent = 'Submission failed: ' + err.message + '. Please try again or email us directly.';
                errEl.classList.remove('hidden');
                btn.disabled = false;
                btn.textContent = 'Try again';
            }
        });

        /* =============================================
           INIT
           ============================================= */
        loadServices();
    </script>
</body>
</html>
