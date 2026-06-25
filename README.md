<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ProFirstAid // Clinical Emergency & R.I.C.E. Guide</title>

<!-- Inter Font Family for modern, clean clinical look -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">

<style>
/* Modern Fluid Reset */
:root {
    --bg-main: #f8fafc;
    --bg-card: #ffffff;
    --text-main: #0f172a;
    --text-muted: #64748b;
    --primary: #0284c7;
    --primary-light: #e0f2fe;
    --primary-dark: #0369a1;
    --emergency: #ef4444;
    --emergency-light: #fee2e2;
    --emergency-dark: #b91c1c;
    --border: #e2e8f0;
    --radius-lg: 20px;
    --radius-md: 12px;
    --shadow-sm: 0 1px 3px rgba(0,0,0,0.05);
    --shadow-md: 0 10px 25px -5px rgba(2, 132, 199, 0.05), 0 8px 10px -6px rgba(0,0,0,0.03);
    --shadow-lg: 0 20px 25px -5px rgba(0, 0, 0, 0.05), 0 10px 10px -5px rgba(0,0,0,0.02);
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Inter', sans-serif;
    scroll-behavior: smooth;
}

body {
    background: var(--bg-main);
    color: var(--text-main);
    line-height: 1.5;
}

/* Fluid Layout Grid */
.app-wrapper {
    display: grid;
    grid-template-columns: 280px 1fr;
    min-height: 100vh;
}

/* Sidebar Navigation */
sidebar {
    background: #0f172a;
    color: #f8fafc;
    padding: 40px 24px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    position: sticky;
    top: 0;
    height: 100vh;
    border-right: 1px solid #1e293b;
    z-index: 100;
}

.brand {
    font-size: 1.4rem;
    font-weight: 800;
    letter-spacing: -0.5px;
    display: flex;
    align-items: center;
    gap: 8px;
    color: #fff;
}

.brand span {
    color: #38bdf8;
}

.nav-links {
    list-style: none;
    margin-top: 40px;
    display: flex;
    flex-direction: column;
    gap: 8px;
    flex-grow: 1;
}

.nav-links a {
    display: flex;
    align-items: center;
    gap: 12px;
    color: #94a3b8;
    text-decoration: none;
    padding: 12px 16px;
    border-radius: var(--radius-md);
    font-weight: 500;
    font-size: 0.95rem;
    transition: all 0.2s ease;
}

.nav-links a:hover, .nav-links li.active a {
    color: #fff;
    background: #1e293b;
}

.sidebar-emergency-card {
    background: #1e293b;
    border: 1px solid #334155;
    padding: 20px;
    border-radius: var(--radius-md);
    text-align: center;
}

.sidebar-emergency-card p {
    font-size: 0.85rem;
    color: #94a3b8;
    margin-bottom: 12px;
}

/* Main Interactive Area */
main {
    padding: 40px 60px;
    max-width: 1400px;
    width: 100%;
}

/* Global Section Header Dashboard Style */
.dashboard-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 40px;
    gap: 20px;
}

.welcome-text h1 {
    font-size: 2.2rem;
    font-weight: 800;
    letter-spacing: -0.8px;
}

.welcome-text p {
    color: var(--text-muted);
    margin-top: 4px;
}

/* Search Bar Feature */
.search-box {
    position: relative;
    width: 100%;
    max-width: 380px;
}

.search-box input {
    width: 100%;
    padding: 14px 20px 14px 45px;
    background: var(--bg-card);
    border: 1px solid var(--border);
    border-radius: var(--radius-md);
    font-size: 0.95rem;
    color: var(--text-main);
    box-shadow: var(--shadow-sm);
    outline: none;
    transition: all 0.2s ease;
}

.search-box input:focus {
    border-color: var(--primary);
    box-shadow: 0 0 0 4px var(--primary-light);
}

.search-box::before {
    content: "🔍";
    position: absolute;
    left: 16px;
    top: 50%;
    transform: translateY(-50%);
    font-size: 1rem;
    opacity: 0.5;
}

/* Modular Content Sections */
.section-panel {
    background: var(--bg-card);
    border: 1px solid var(--border);
    border-radius: var(--radius-lg);
    padding: 40px;
    margin-bottom: 40px;
    box-shadow: var(--shadow-md);
}

.section-panel h2 {
    font-size: 1.6rem;
    font-weight: 700;
    letter-spacing: -0.5px;
    margin-bottom: 30px;
    display: flex;
    align-items: center;
    gap: 12px;
}

/* Interactive Timeline Style for Steps */
.timeline-flow {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 24px;
}

.flow-node {
    background: var(--bg-main);
    border: 1px solid var(--border);
    border-radius: var(--radius-md);
    padding: 24px;
    position: relative;
    transition: all 0.2s ease;
}

.flow-node:hover {
    transform: translateY(-4px);
    box-shadow: var(--shadow-lg);
    border-color: var(--primary);
}

.node-badge {
    display: inline-block;
    padding: 4px 10px;
    background: var(--primary-light);
    color: var(--primary-dark);
    font-size: 0.75rem;
    font-weight: 700;
    border-radius: 20px;
    margin-bottom: 14px;
    text-transform: uppercase;
}

.flow-node h3 {
    font-size: 1.15rem;
    font-weight: 600;
    margin-bottom: 10px;
}

.flow-node p, .flow-node li {
    font-size: 0.9rem;
    color: var(--text-muted);
}

.flow-node ul {
    list-style: none;
    margin-top: 10px;
}

.flow-node li {
    margin-bottom: 6px;
    padding-left: 14px;
    position: relative;
}

.flow-node li::before {
    content: "→";
    position: absolute;
    left: 0;
    color: var(--primary);
}

/* R.I.C.E Graphic Blocks */
.rice-matrix {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 20px;
}

.rice-card {
    background: linear-gradient(180deg, var(--bg-card) 0%, #f0fdf4 100%);
    border: 1px solid #dcfce7;
    border-radius: var(--radius-md);
    padding: 30px 24px;
    text-align: center;
    transition: all 0.2s ease;
}

.rice-card:nth-child(2) { background: linear-gradient(180deg, var(--bg-card) 0%, #f0f9ff 100%); border-color: #e0f2fe; }
.rice-card:nth-child(3) { background: linear-gradient(180deg, var(--bg-card) 0%, #faf5ff 100%); border-color: #f3e8ff; }
.rice-card:nth-child(4) { background: linear-gradient(180deg, var(--bg-card) 0%, #fff7ed 100%); border-color: #ffedd5; }

.rice-card:hover {
    transform: scale(1.02);
    box-shadow: var(--shadow-lg);
}

.rice-icon {
    font-size: 2.2rem;
    margin-bottom: 12px;
}

.rice-card h3 {
    font-size: 1.3rem;
    font-weight: 700;
    margin-bottom: 8px;
}

.rice-card p {
    font-size: 0.9rem;
    color: var(--text-muted);
}

/* Common Injuries Grid with built-in filtration support */
.injury-catalog {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
    gap: 24px;
}

.catalog-item {
    background: var(--bg-main);
    border: 1px solid var(--border);
    padding: 24px;
    border-radius: var(--radius-md);
    transition: all 0.2s ease;
}

.catalog-item:hover {
    background: var(--bg-card);
    border-color: var(--primary);
    box-shadow: var(--shadow-md);
}

.catalog-item h3 {
    font-size: 1.15rem;
    font-weight: 600;
    margin-bottom: 12px;
    display: flex;
    align-items: center;
    gap: 8px;
}

.catalog-item ul {
    list-style: none;
}

.catalog-item li {
    font-size: 0.9rem;
    color: var(--text-muted);
    margin-bottom: 6px;
    padding-left: 16px;
    position: relative;
}

.catalog-item li::before {
    content: "✓";
    position: absolute;
    left: 0;
    color: #10b981;
    font-weight: bold;
}

/* Emergency Core Call Area styling */
.emergency-banner {
    background: linear-gradient(135deg, var(--emergency), var(--emergency-dark));
    color: white;
    border: none;
    text-align: center;
    padding: 50px 30px;
    border-radius: var(--radius-lg);
}

.emergency-banner h2 {
    color: white;
    justify-content: center;
}

.emergency-banner p {
    color: var(--emergency-light);
    margin-bottom: 24px;
    font-size: 1.1rem;
}

.btn-pulse {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    padding: 16px 40px;
    background: white;
    color: var(--emergency-dark);
    text-decoration: none;
    border-radius: 30px;
    font-weight: 700;
    font-size: 1.1rem;
    box-shadow: 0 10px 20px rgba(0,0,0,0.15);
    transition: all 0.2s ease;
    animation: pulse 2s infinite;
}

.btn-pulse:hover {
    transform: translateY(-2px);
    box-shadow: 0 15px 30px rgba(0,0,0,0.25);
    background: var(--emergency-light);
}

@keyframes pulse {
    0% { box-shadow: 0 0 0 0 rgba(255, 255, 255, 0.4); }
    70% { box-shadow: 0 0 0 15px rgba(255, 255, 255, 0); }
    100% { box-shadow: 0 0 0 0 rgba(255, 255, 255, 0); }
}

footer {
    text-align: center;
    padding: 40px 0;
    color: var(--text-muted);
    font-size: 0.9rem;
    border-top: 1px solid var(--border);
    margin-top: 20px;
}

/* Responsive Overrides */
@media (max-width: 1024px) {
    .app-wrapper { grid-template-columns: 1fr; }
    sidebar { display: none; }
    main { padding: 30px 20px; }
}

@media (max-width: 640px) {
    .dashboard-header { flex-direction: column; align-items: flex-start; }
    .search-box { max-width: 100%; }
    .section-panel { padding: 24px; }
}
</style>
</head>

<body>

<div class="app-wrapper">

    <!-- Fixed Left Control Panel -->
    <sidebar>
        <div>
            <div class="brand">🛡️ Pro<span>FirstAid</span></div>
            <ul class="nav-links">
                <li class="active"><a href="#protocol">📋 Action Protocol</a></li>
                <li><a href="#rice">🧊 R.I.C.E. Method</a></li>
                <li><a href="#injuries">🩹 Injury Catalog</a></li>
            </ul>
        </div>
        
        <div class="sidebar-emergency-card">
            <p>Crisis Situation?</p>
            <a href="tel:911" style="background: var(--emergency); color: white; display: block; text-decoration: none; padding: 10px; border-radius: 6px; font-weight: 600; font-size: 0.9rem;">Quick Dial 911</a>
        </div>
    </sidebar>

    <!-- Main Content Workspace -->
    <main>
        
        <div class="dashboard-header">
            <div class="welcome-text">
                <h1>Emergency Medical Guide</h1>
                <p>Instant clinical first-aid references for response teams and home safety.</p>
            </div>
            <div class="search-box">
                <input type="text" id="injurySearch" onkeyup="searchInjuries()" placeholder="Search injuries (e.g., Burns, Sprains)...">
            </div>
        </div>

        <!-- Section 1: Protocols -->
        <section id="protocol" class="section-panel">
            <h2>📋 Critical Injury Protocol</h2>
            <div class="timeline-flow">
                <div class="flow-node">
                    <span class="node-badge">Step 1</span>
                    <h3>Assess Situation</h3>
                    <p>Ensure the scene is completely safe before entering or providing help.</p>
                </div>
                <div class="flow-node">
                    <span class="node-badge">Step 2</span>
                    <h3>Call For Help</h3>
                    <p>If the baseline injury appears dangerous or severe, dial dispatch systems instantly.</p>
                </div>
                <div class="flow-node">
                    <span class="node-badge">Step 3</span>
                    <h3>Control Bleeding</h3>
                    <ul>
                        <li>Apply strong direct pressure using a clean cloth.</li>
                        <li>Layer additional padding if heavy saturation occurs.</li>
                    </ul>
                </div>
                <div class="flow-node">
                    <span class="node-badge">Step 4</span>
                    <h3>Treat Burns</h3>
                    <ul>
                        <li>Cool below ambient running water for 10+ minutes.</li>
                        <li>Apply non-stick sterile dressings.</li>
                    </ul>
                </div>
                <div class="flow-node">
                    <span class="node-badge">Step 5</span>
                    <h3>Stabilize Fractures</h3>
                    <p>Immobilize the structures using straight splints. Restrict active movement.</p>
                </div>
                <div class="flow-node">
                    <span class="node-badge">Step 6</span>
                    <h3>Monitor Vitals</h3>
                    <p>Track dynamic levels of consciousness, steady pulse rates, and respiratory tracking.</p>
                </div>
            </div>
        </section>

        <!-- Section 2: R.I.C.E. -->
        <section id="rice" class="section-panel">
            <h2>🧊 The R.I.C.E. Treatment System</h2>
            <div class="rice-matrix">
                <div class="rice-card">
                    <div class="rice-icon">🛌</div>
                    <h3>Rest</h3>
                    <p>Protect the localized path. Stop physical activity instantly.</p>
                </div>
                <div class="rice-card">
                    <div class="rice-icon">❄️</div>
                    <h3>Ice</h3>
                    <p>Apply cold packs wrapped in towels for 15-20 min increments.</p>
                </div>
                <div class="rice-card">
                    <div class="rice-icon">🩹</div>
                    <h3>Compression</h3>
                    <p>Wrap securely using elastic bandage sets to manage acute swelling.</p>
                </div>
                <div class="rice-card">
                    <div class="rice-icon">⬆️</div>
                    <h3>Elevation</h3>
                    <p>Keep the target zone safely elevated above the center cardiac line.</p>
                </div>
            </div>
        </section>

        <!-- Section 3: Live Filter Search Cards Catalog -->
        <section id="injuries" class="section-panel">
            <h2>🩹 Action Catalog for Common Injuries</h2>
            <div class="injury-catalog" id="catalogGrid">
                <div class="catalog-item">
                    <h3>🤕 Cuts and Scrapes</h3>
                    <ul>
                        <li>Clean thoroughly with water.</li>
                        <li>Apply thin antiseptic cream and cover safely.</li>
                    </ul>
                </div>
                <div class="catalog-item">
                    <h3>🔥 Thermal Burns</h3>
                    <ul>
                        <li>Run under cool water immediately.</li>
                        <li>Protect using a sterile, non-adhesive dressing layer.</li>
                    </ul>
                </div>
                <div class="catalog-item">
                    <h3>🤧 Severe Nosebleeds</h3>
                    <ul>
                        <li>Lean head slightly forward.</li>
                        <li>Firmly pinch soft nasal cavities for continuous minutes.</li>
                    </ul>
                </div>
                <div class="catalog-item">
                    <h3>🐝 Bites and Stings</h3>
                    <ul>
                        <li>Scrape stinger out safely.</li>
                        <li>Apply an localized cold compress to suppress reactions.</li>
                    </ul>
                </div>
                <div class="catalog-item">
                    <h3>🦴 Sprains & Strains</h3>
                    <ul>
                        <li>Implement full R.I.C.E protocol loops.</li>
                        <li>Limit active load bearing completely.</li>
                    </ul>
                </div>
                <div class="catalog-item">
                    <h3>😵 Sudden Fainting</h3>
                    <ul>
                        <li>Lay patient flat instantly.</li>
                        <li>Raise feet upward to support core circulation.</li>
                    </ul>
                </div>
                <div class="catalog-item">
                    <h3>👁️ Acute Eye Injury</h3>
                    <ul>
                        <li>Flush immediately with clean water.</li>
                        <li>Avoid physical rubbing actions.</li>
                    </ul>
                </div>
                <div class="catalog-item">
                    <h3>⚡ High Voltage Shock</h3>
                    <ul>
                        <li>Isolate active power grids before approaching.</li>
                        <li>Contact professional advanced critical services.</li>
                    </ul>
                </div>
                <div class="catalog-item">
                    <h3>🤢 Systemic Food Poisoning</h3>
                    <ul>
                        <li>Replenish lost electrolyte counts.</li>
                        <li>Ensure structural physical resting states.</li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- Section 4: Urgent Notice System -->
        <section class="section-panel emergency-banner">
            <h2>🚨 Need Urgent Medical Backup?</h2>
            <p>If you encounter trauma, respiratory failure, or serious uncontrolled bleeding, activate regional paramedics right now.</p>
            <a href="tel:911" class="btn-pulse">☎️ Call Medical Dispatch (911)</a>
        </section>

        <footer>
            <p>© 2026 ProFirstAid Protocol Systems. Designed for clarity under pressure.</p>
        </footer>

    </main>
</div>

<!-- Instant Search Functionality without bulky libraries -->
<script>
function searchInjuries() {
    let input = document.getElementById('injurySearch').value.toLowerCase();
    let cards = document.getElementsByClassName('catalog-item');
    
    for (let i = 0; i < cards.length; i++) {
        let title = cards[i].getElementsByTagName('h3')[0].innerText.toLowerCase();
        if (title.includes(input)) {
            cards[i].style.display = "";
        } else {
            cards[i].style.display = "none";
        }
    }
}
</script>

</body>
</html>
