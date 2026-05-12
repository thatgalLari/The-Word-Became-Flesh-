<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>The Word Became Flesh — Prayer & Testimony Journal</title>
<link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;600;900&family=EB+Garamond:ital,wght@0,400;0,500;1,400;1,500&display=swap" rel="stylesheet">
<style>
:root {
  --cream: #f5f0e8;
  --cream-dark: #ece5d8;
  --tan: #e8e0d0;
  --tan-deep: #ddd4c0;
  --dark: #1a2030;
  --dark-mid: #2e3e52;
  --gold: #c9a84c;
  --gold-light: #e8d5a3;
  --gold-dim: rgba(201,168,76,0.25);
  --brown: #6b5a42;
  --brown-light: #9a8870;
  --text: #2c2416;
  --text-light: #6b5a42;
  --border: #d4c9b5;
  --answered: #3a6b45;
  --answered-bg: #eaf2ec;
}

* { margin:0; padding:0; box-sizing:border-box; }

body {
  background: var(--cream);
  font-family: 'EB Garamond', serif;
  color: var(--text);
  min-height: 100vh;
}

/* ─── GRAIN ─── */
body::after {
  content:''; position:fixed; inset:0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.85' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.035'/%3E%3C/svg%3E");
  pointer-events:none; z-index:999; opacity:.4;
}

/* ─── NAV ─── */
nav {
  display:flex; align-items:center; justify-content:space-between;
  padding:16px 40px; border-bottom:1px solid var(--border);
  background:var(--cream); position:sticky; top:0; z-index:50;
}
.nav-brand { font-family:'Cinzel',serif; font-size:13px; letter-spacing:4px; color:var(--dark); text-transform:uppercase; text-decoration:none; }
.nav-right { display:flex; gap:12px; align-items:center; }
.btn-nav {
  font-family:'Cinzel',serif; font-size:9px; letter-spacing:2px; text-transform:uppercase;
  padding:7px 16px; border-radius:2px; cursor:pointer; border:none; transition:all .2s;
}
.btn-nav.outline { background:transparent; border:1px solid var(--border); color:var(--brown); }
.btn-nav.outline:hover { border-color:var(--gold); color:var(--dark); }
.btn-nav.primary { background:var(--dark); color:var(--cream); }
.btn-nav.primary:hover { background:var(--dark-mid); }

/* ─── PAGES ─── */
.page { display:none; }
.page.active { display:block; }

/* ════════════════════════════════
   DASHBOARD
════════════════════════════════ */
.dashboard { max-width:900px; margin:0 auto; padding:60px 24px; }

.dash-hero { text-align:center; margin-bottom:56px; }
.dash-label { font-family:'Cinzel',serif; font-size:10px; letter-spacing:5px; color:var(--gold); text-transform:uppercase; margin-bottom:14px; display:block; }
.dash-title { font-family:'Cinzel',serif; font-size:clamp(32px,6vw,58px); font-weight:900; color:var(--dark); letter-spacing:4px; text-transform:uppercase; line-height:1.05; }
.dash-divider { display:flex; align-items:center; gap:14px; margin:20px auto; max-width:400px; }
.dash-divider::before,.dash-divider::after { content:''; flex:1; height:1px; background:linear-gradient(90deg,transparent,var(--gold)); }
.dash-divider::after { background:linear-gradient(90deg,var(--gold),transparent); }
.dash-sub { font-size:17px; font-style:italic; color:var(--brown); line-height:1.7; max-width:520px; margin:0 auto; }

.stats-row { display:grid; grid-template-columns:repeat(3,1fr); gap:14px; margin-bottom:40px; }
.stat-card { background:var(--tan); border-radius:4px; padding:22px 20px; text-align:center; }
.stat-num { font-family:'Cinzel',serif; font-size:32px; font-weight:900; color:var(--dark); line-height:1; }
.stat-label { font-size:11px; letter-spacing:2px; text-transform:uppercase; color:var(--brown); margin-top:6px; font-family:'Cinzel',serif; }

.entries-header { display:flex; justify-content:space-between; align-items:center; margin-bottom:20px; }
.entries-title { font-family:'Cinzel',serif; font-size:14px; letter-spacing:3px; text-transform:uppercase; color:var(--dark); }
.btn-new { font-family:'Cinzel',serif; font-size:10px; letter-spacing:2px; text-transform:uppercase; background:var(--dark); color:var(--cream); border:none; padding:10px 22px; border-radius:2px; cursor:pointer; transition:background .2s; }
.btn-new:hover { background:var(--dark-mid); }

.entry-list { display:flex; flex-direction:column; gap:10px; }

.entry-card {
  background:var(--tan); border-radius:4px; padding:20px 24px;
  display:grid; grid-template-columns:1fr auto;
  align-items:center; gap:16px; cursor:pointer;
  border:1px solid transparent; transition:all .2s;
}
.entry-card:hover { border-color:var(--gold); background:var(--cream-dark); }
.entry-card.answered { border-left:3px solid var(--answered); }

.entry-name { font-family:'Cinzel',serif; font-size:15px; font-weight:600; color:var(--dark); margin-bottom:4px; }
.entry-meta { font-size:13px; color:var(--brown-light); font-style:italic; }
.entry-type { font-family:'Cinzel',serif; font-size:9px; letter-spacing:2px; text-transform:uppercase; color:var(--brown); margin-top:6px; }

.badge { font-family:'Cinzel',serif; font-size:8px; letter-spacing:2px; text-transform:uppercase; padding:4px 10px; border-radius:20px; }
.badge.active-b { background:var(--gold-dim); color:var(--brown); border:1px solid var(--gold); }
.badge.answered-b { background:var(--answered-bg); color:var(--answered); border:1px solid var(--answered); }

.empty-state { text-align:center; padding:60px 24px; color:var(--brown-light); }
.empty-state p { font-size:17px; font-style:italic; margin-bottom:20px; }

/* ════════════════════════════════
   ENTRY VIEW (3 sections)
════════════════════════════════ */
.entry-view { max-width:860px; margin:0 auto; padding:40px 24px 80px; }

.entry-nav { display:flex; justify-content:space-between; align-items:center; margin-bottom:32px; }
.back-btn { font-family:'Cinzel',serif; font-size:9px; letter-spacing:2px; text-transform:uppercase; color:var(--brown); background:none; border:none; cursor:pointer; padding:0; }
.back-btn:hover { color:var(--dark); }
.entry-actions { display:flex; gap:10px; }

/* section tabs */
.section-tabs { display:flex; gap:0; margin-bottom:32px; border:1px solid var(--border); border-radius:3px; overflow:hidden; }
.tab-btn {
  flex:1; font-family:'Cinzel',serif; font-size:9px; letter-spacing:2px; text-transform:uppercase;
  padding:12px 8px; background:var(--tan); color:var(--brown); border:none; cursor:pointer;
  border-right:1px solid var(--border); transition:all .2s; text-align:center;
}
.tab-btn:last-child { border-right:none; }
.tab-btn.active { background:var(--dark); color:var(--cream); }
.tab-btn.done::after { content:' ✓'; color:var(--gold); }

.section-panel { display:none; }
.section-panel.active { display:block; }

/* section header */
.section-badge { font-family:'Cinzel',serif; font-size:9px; letter-spacing:4px; text-transform:uppercase; color:var(--gold); margin-bottom:10px; display:block; }
.section-heading { font-family:'Cinzel',serif; font-size:clamp(22px,4vw,34px); font-weight:900; color:var(--dark); letter-spacing:3px; text-transform:uppercase; margin-bottom:6px; }
.section-verse { font-size:14px; font-style:italic; color:var(--brown); border-left:2px solid var(--gold); padding-left:14px; margin:16px 0 28px; line-height:1.6; }

/* form fields */
.field-group { margin-bottom:24px; }
.field-label { font-family:'Cinzel',serif; font-size:9px; letter-spacing:3px; text-transform:uppercase; color:var(--dark); margin-bottom:8px; display:block; }
.field-hint { font-size:12px; font-style:italic; color:var(--brown-light); margin-bottom:8px; display:block; }

.field-input, .field-textarea, .field-select {
  font-family:'EB Garamond',serif; font-size:15px; color:var(--text);
  width:100%; padding:12px 16px; background:var(--tan); border:1px solid var(--border);
  border-radius:3px; outline:none; transition:border-color .2s;
}
.field-input:focus, .field-textarea:focus, .field-select:focus { border-color:var(--gold); background:#fff; }
.field-textarea { resize:vertical; min-height:100px; line-height:1.7; }
.field-select { cursor:pointer; }

.field-input::placeholder, .field-textarea::placeholder { color:#b8ad9c; font-style:italic; }

/* prayer type pills */
.type-pills { display:flex; gap:10px; flex-wrap:wrap; }
.type-pill {
  font-family:'Cinzel',serif; font-size:9px; letter-spacing:2px; text-transform:uppercase;
  padding:8px 16px; border:1px solid var(--border); border-radius:20px; cursor:pointer;
  background:var(--tan); color:var(--brown); transition:all .2s; user-select:none;
}
.type-pill.selected { background:var(--dark); color:var(--cream); border-color:var(--dark); }

/* divider */
.form-divider { height:1px; background:var(--border); margin:28px 0; }

/* ── AI DECLARATIONS ── */
.ai-box { background:var(--dark); border-radius:4px; overflow:hidden; margin-bottom:24px; }
.ai-header { padding:16px 20px; display:flex; align-items:center; justify-content:space-between; border-bottom:1px solid rgba(255,255,255,0.08); }
.ai-title { font-family:'Cinzel',serif; font-size:10px; letter-spacing:3px; text-transform:uppercase; color:var(--gold); }
.ai-sub { font-size:12px; font-style:italic; color:#8a8070; margin-top:2px; }
.ai-body { padding:20px; }

.ai-search-row { display:flex; gap:0; }
.ai-input {
  flex:1; font-family:'EB Garamond',serif; font-size:15px; color:var(--cream);
  background:rgba(255,255,255,0.07); border:1px solid rgba(255,255,255,0.12);
  border-right:none; border-radius:3px 0 0 3px; padding:11px 16px; outline:none;
}
.ai-input::placeholder { color:#6a6058; font-style:italic; }
.ai-input:focus { background:rgba(255,255,255,0.12); }
.ai-go {
  font-family:'Cinzel',serif; font-size:9px; letter-spacing:2px; text-transform:uppercase;
  background:var(--gold); color:var(--dark); border:none; padding:11px 20px;
  border-radius:0 3px 3px 0; cursor:pointer; transition:background .2s; white-space:nowrap;
}
.ai-go:hover { background:var(--gold-light); }
.ai-go:disabled { background:#5a5040; color:#8a7a68; cursor:not-allowed; }

.ai-examples { margin-top:10px; font-size:12px; color:#6a6058; font-style:italic; }
.ai-examples span { cursor:pointer; color:#9a8870; text-decoration:underline; text-underline-offset:2px; margin:0 4px; }
.ai-examples span:hover { color:var(--gold); }

.ai-loading { text-align:center; padding:28px; display:none; }
.ai-loading.on { display:block; }
.ai-loading-icon { font-size:24px; color:var(--gold); animation:spin 2s linear infinite; display:inline-block; margin-bottom:8px; }
@keyframes spin { from{transform:rotate(0deg)} to{transform:rotate(360deg)} }
.ai-loading p { font-size:14px; font-style:italic; color:#8a8070; }

.ai-result { display:none; }
.ai-result.on { display:block; }

.ai-section-out { margin-bottom:16px; border-left:2px solid rgba(201,168,76,0.3); padding-left:14px; }
.ai-section-label { font-family:'Cinzel',serif; font-size:8px; letter-spacing:3px; text-transform:uppercase; color:var(--gold); margin-bottom:4px; }
.ai-section-text { font-size:14px; color:#c8bfb0; line-height:1.7; }

.ai-copy-btn {
  font-family:'Cinzel',serif; font-size:9px; letter-spacing:2px; text-transform:uppercase;
  background:transparent; border:1px solid rgba(201,168,76,0.4); color:var(--gold);
  padding:8px 16px; border-radius:2px; cursor:pointer; margin-top:12px; transition:all .2s;
}
.ai-copy-btn:hover { background:var(--gold); color:var(--dark); }

/* ── PRESS IN PRAYER entries ── */
.pip-entries { display:flex; flex-direction:column; gap:16px; margin-bottom:20px; }
.pip-entry { background:var(--tan); border-radius:4px; padding:20px; border:1px solid var(--border); }
.pip-entry-header { display:flex; justify-content:space-between; align-items:center; margin-bottom:16px; }
.pip-entry-num { font-family:'Cinzel',serif; font-size:9px; letter-spacing:3px; text-transform:uppercase; color:var(--gold); }
.pip-remove { background:none; border:none; color:var(--brown-light); cursor:pointer; font-size:18px; line-height:1; }
.pip-remove:hover { color:#c0392b; }

.btn-add-pip {
  font-family:'Cinzel',serif; font-size:9px; letter-spacing:2px; text-transform:uppercase;
  background:transparent; border:1px dashed var(--border); color:var(--brown); padding:12px;
  border-radius:3px; cursor:pointer; width:100%; transition:all .2s;
}
.btn-add-pip:hover { border-color:var(--gold); color:var(--dark); background:var(--tan); }

/* ── TETELESTAI ── */
.tetelestai-box {
  background:var(--dark); border-radius:4px; padding:28px; text-align:center;
  margin-bottom:28px; border:1px solid rgba(201,168,76,0.3);
}
.tetelestai-word { font-family:'Cinzel',serif; font-size:clamp(28px,5vw,44px); font-weight:900; color:var(--gold); letter-spacing:6px; text-transform:uppercase; }
.tetelestai-meaning { font-size:14px; font-style:italic; color:#8a8070; margin-top:6px; }
.tetelestai-check { font-size:12px; color:#b0a898; margin-top:14px; display:flex; align-items:center; justify-content:center; gap:8px; cursor:pointer; }
.tetelestai-check input { accent-color:var(--gold); width:16px; height:16px; cursor:pointer; }

/* section nav buttons */
.section-footer { display:flex; justify-content:space-between; align-items:center; margin-top:32px; padding-top:24px; border-top:1px solid var(--border); }
.btn-section {
  font-family:'Cinzel',serif; font-size:9px; letter-spacing:2px; text-transform:uppercase;
  padding:10px 24px; border-radius:2px; cursor:pointer; border:none; transition:all .2s;
}
.btn-section.prev { background:transparent; border:1px solid var(--border); color:var(--brown); }
.btn-section.prev:hover { border-color:var(--dark); color:var(--dark); }
.btn-section.next { background:var(--dark); color:var(--cream); }
.btn-section.next:hover { background:var(--dark-mid); }
.btn-section.save-final { background:var(--gold); color:var(--dark); font-weight:700; }
.btn-section.save-final:hover { background:var(--gold-light); }

/* ── print ── */
@media print {
  nav, .section-tabs, .section-footer, .ai-box, .entry-nav, .entry-actions, .btn-add-pip, .pip-remove { display:none !important; }
  .section-panel { display:block !important; }
  body { background:white; }
}

@media (max-width:600px) {
  nav { padding:14px 16px; }
  .stats-row { grid-template-columns:1fr 1fr; }
  .tab-btn { font-size:8px; padding:10px 4px; }
}
</style>
</head>
<body>

<!-- ─── NAV ─── -->
<nav>
  <span class="nav-brand">The Word Became Flesh</span>
  <div class="nav-right">
    <button class="btn-nav outline" onclick="showPage('dashboard')">My Journal</button>
    <button class="btn-nav primary" onclick="startNewEntry()">+ New Entry</button>
  </div>
</nav>

<!-- ════════════════════════════════
     DASHBOARD
════════════════════════════════ -->
<div id="page-dashboard" class="page active">
  <div class="dashboard">

    <div class="dash-hero">
      <span class="dash-label">Prayer &amp; Testimony Journal</span>
      <h1 class="dash-title">The Word<br>Became Flesh</h1>
      <div class="dash-divider"><span style="color:var(--gold);font-size:16px;">✦</span></div>
      <p class="dash-sub">Pray the Scriptures · Wait in Faith · See the Word Fulfilled</p>
    </div>

    <div class="stats-row">
      <div class="stat-card">
        <div class="stat-num" id="stat-total">0</div>
        <div class="stat-label">Total Prayers</div>
      </div>
      <div class="stat-card">
        <div class="stat-num" id="stat-active">0</div>
        <div class="stat-label">Standing in Faith</div>
      </div>
      <div class="stat-card">
        <div class="stat-num" id="stat-answered" style="color:var(--answered)">0</div>
        <div class="stat-label">Testimonies</div>
      </div>
    </div>

    <div class="entries-header">
      <span class="entries-title">Prayer Entries</span>
      <button class="btn-new" onclick="startNewEntry()">+ New Prayer Entry</button>
    </div>

    <div class="entry-list" id="entry-list">
      <div class="empty-state">
        <p>"Let us then approach God's throne of grace with confidence…" — Hebrews 4:16</p>
        <button class="btn-new" onclick="startNewEntry()">Begin Your First Prayer Entry</button>
      </div>
    </div>

  </div>
</div>

<!-- ════════════════════════════════
     ENTRY VIEW
════════════════════════════════ -->
<div id="page-entry" class="page">
  <div class="entry-view">

    <div class="entry-nav">
      <button class="back-btn" onclick="confirmBack()">← Back to Journal</button>
      <div class="entry-actions">
        <button class="btn-nav outline" onclick="window.print()">Print</button>
        <button class="btn-nav primary" onclick="saveEntry()">Save Entry</button>
      </div>
    </div>

    <!-- TABS -->
    <div class="section-tabs">
      <button class="tab-btn active" id="tab-1" onclick="switchTab(1)">I · Prayer Entry</button>
      <button class="tab-btn" id="tab-2" onclick="switchTab(2)">II · Press In Prayer</button>
      <button class="tab-btn" id="tab-3" onclick="switchTab(3)">III · Word Became Flesh</button>
    </div>

    <!-- ══ SECTION 1: PRAYER ENTRY ══ -->
    <div class="section-panel active" id="panel-1">
      <span class="section-badge">Section One</span>
      <h2 class="section-heading">Prayer Entry</h2>
      <div class="section-verse">"Let us then approach God's throne of grace with confidence, so that we may receive mercy and find grace to help us in our time of need." — Hebrews 4:16</div>

      <div class="field-group">
        <label class="field-label">Name</label>
        <span class="field-hint">Write the name of the person you are praying for (including yourself if applicable)</span>
        <input class="field-input" id="f-name" type="text" placeholder="Name…" />
      </div>

      <div class="field-group">
        <label class="field-label">Type of Prayer</label>
        <div class="type-pills">
          <div class="type-pill" onclick="selectType(this,'Supplication / Petition')">Supplication / Petition</div>
          <div class="type-pill" onclick="selectType(this,'Intercession')">Intercession</div>
          <div class="type-pill" onclick="selectType(this,'Lamentation')">Lamentation</div>
        </div>
        <input type="hidden" id="f-type" />
      </div>

      <div class="field-group">
        <label class="field-label">Situation</label>
        <span class="field-hint">Describe the specific circumstance that has led you to prayer</span>
        <textarea class="field-textarea" id="f-situation" placeholder="Describe your situation…" style="min-height:120px;"></textarea>
      </div>

      <div class="form-divider"></div>

      <div class="field-group">
        <label class="field-label">Standing Scriptures</label>
        <span class="field-hint">Write out the full scriptures you are standing on. These reveal God's will and become the foundation of your faith for this situation.</span>
        <textarea class="field-textarea" id="f-scriptures" placeholder="e.g. Isaiah 53:5 — But he was pierced for our transgressions…" style="min-height:130px;"></textarea>
      </div>

      <div class="form-divider"></div>

      <!-- AI DECLARATIONS -->
      <div class="field-group">
        <label class="field-label">Declarations</label>
        <span class="field-hint">Guided by the scriptures you have written, declare God's truth over the situation. Use the AI generator below to help you pray a specific scripture, then write your declarations above.</span>

        <textarea class="field-textarea" id="f-declarations" placeholder="I declare that the Lord is my healer…&#10;I declare that by His wounds I am healed…" style="min-height:130px; margin-bottom:16px;"></textarea>

        <!-- AI BOX -->
        <div class="ai-box">
          <div class="ai-header">
            <div>
              <div class="ai-title">✦ Praying Scripture — AI Generator</div>
              <div class="ai-sub">Type a scripture reference to generate a 7-section prayer framework</div>
            </div>
          </div>
          <div class="ai-body">
            <div class="ai-sear# The-Word-Became-Flesh-
A prayer journal. 
