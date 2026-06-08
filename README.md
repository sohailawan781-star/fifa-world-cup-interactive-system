<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>FIFA World Cup 2026 — Official Scoresheet</title>
<style>
  /* Self-contained system fonts — no internet required */
  @font-face {
    font-family: 'Bebas Neue';
    src: local('Impact'), local('Arial Black'), local('Haettenschweiler');
  }
</style>
<style>
  :root {
    --gold: #C9A84C;
    --gold-light: #F0CC6A;
    --navy: #0A1628;
    --navy-mid: #112040;
    --navy-card: #0F1E38;
    --green: #00A86B;
    --red: #E63946;
    --white: #F5F0E8;
    --muted: #8899BB;
    --border: rgba(201,168,76,0.25);
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--navy);
    color: var(--white);
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Arial, sans-serif;
    min-height: 100vh;
  }

  /* HEADER */
  header {
    background: linear-gradient(135deg, #0A1628 0%, #112040 50%, #0A1628 100%);
    border-bottom: 2px solid var(--gold);
    padding: 24px 20px 20px;
    text-align: center;
    position: relative;
    overflow: hidden;
  }
  header::before {
    content: '';
    position: absolute;
    inset: 0;
    background: repeating-linear-gradient(
      45deg,
      transparent,
      transparent 30px,
      rgba(201,168,76,0.03) 30px,
      rgba(201,168,76,0.03) 31px
    );
  }
  .header-flag-strip {
    display: flex;
    justify-content: center;
    gap: 6px;
    margin-bottom: 14px;
    flex-wrap: wrap;
  }
  .flag-dot {
    width: 8px; height: 8px;
    border-radius: 50%;
    opacity: 0.7;
  }
  header h1 {
    font-family: 'Impact', 'Arial Black', 'Arial Narrow', sans-serif;
    font-size: clamp(28px, 6vw, 56px);
    letter-spacing: 4px;
    color: var(--gold-light);
    text-shadow: 0 0 40px rgba(201,168,76,0.4);
    position: relative;
  }
  header .sub {
    font-family: 'Arial Narrow', 'Helvetica Neue', Arial, sans-serif;
    font-size: clamp(11px, 2.5vw, 15px);
    letter-spacing: 6px;
    color: var(--muted);
    margin-top: 4px;
    text-transform: uppercase;
    position: relative;
  }
  .host-badge {
    display: inline-flex;
    gap: 10px;
    margin-top: 12px;
    background: rgba(201,168,76,0.1);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 6px 16px;
    font-family: 'Arial Narrow', 'Helvetica Neue', Arial, sans-serif;
    font-size: 13px;
    letter-spacing: 2px;
    color: var(--gold);
    position: relative;
  }

  /* TABS */
  .tabs-wrapper {
    background: var(--navy-mid);
    border-bottom: 1px solid var(--border);
    padding: 0 16px;
    overflow-x: auto;
    -webkit-overflow-scrolling: touch;
    white-space: nowrap;
  }
  .tabs {
    display: inline-flex;
    gap: 0;
    min-width: 100%;
  }
  .tab-btn {
    background: none;
    border: none;
    color: var(--muted);
    font-family: 'Arial Narrow', 'Helvetica Neue', Arial, sans-serif;
    font-size: 14px;
    font-weight: 600;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    padding: 14px 16px;
    cursor: pointer;
    border-bottom: 3px solid transparent;
    transition: all 0.2s;
    white-space: nowrap;
  }
  .tab-btn:hover { color: var(--white); }
  .tab-btn.active {
    color: var(--gold-light);
    border-bottom-color: var(--gold);
  }

  /* PANELS */
  .panel { display: none; padding: 20px 16px; max-width: 1100px; margin: 0 auto; }
  .panel.active { display: block; }

  /* GROUP SECTION */
  .group-section {
    margin-bottom: 32px;
  }
  .group-header {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 12px;
  }
  .group-label {
    font-family: 'Impact', 'Arial Black', 'Arial Narrow', sans-serif; letter-spacing: 2px;
    font-size: 22px;
    letter-spacing: 3px;
    color: var(--gold-light);
    background: rgba(201,168,76,0.1);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 4px 14px;
  }
  .group-teams {
    font-family: 'Arial Narrow', 'Helvetica Neue', Arial, sans-serif;
    font-size: 13px;
    color: var(--muted);
    letter-spacing: 1px;
  }

  /* MATCH CARD */
  .match-card {
    background: var(--navy-card);
    border: 1px solid var(--border);
    border-radius: 8px;
    margin-bottom: 10px;
    overflow: hidden;
    transition: border-color 0.2s;
  }
  .match-card:hover { border-color: rgba(201,168,76,0.5); }

  .match-header {
    display: grid;
    grid-template-columns: 1fr auto 1fr;
    align-items: center;
    padding: 14px 16px 12px;
    gap: 10px;
    cursor: pointer;
  }
  .team-home { text-align: right; }
  .team-away { text-align: left; }
  .team-name {
    font-family: 'Arial Narrow', 'Helvetica Neue', Arial, sans-serif;
    font-size: clamp(13px, 3vw, 17px);
    font-weight: 700;
    letter-spacing: 0.5px;
    color: var(--white);
    line-height: 1.2;
  }
  .team-flag {
    font-size: 20px;
    display: block;
    margin-bottom: 2px;
  }

  .score-center {
    display: flex;
    align-items: center;
    gap: 6px;
    flex-direction: column;
    min-width: 100px;
  }
  .score-inputs {
    display: flex;
    align-items: center;
    gap: 6px;
  }
  .score-input {
    width: 36px;
    height: 36px;
    background: var(--navy);
    border: 1px solid var(--border);
    border-radius: 4px;
    color: var(--gold-light);
    font-family: 'Impact', 'Arial Black', 'Arial Narrow', sans-serif; letter-spacing: 2px;
    font-size: 24px;
    text-align: center;
    outline: none;
    transition: border-color 0.2s;
  }
  .score-input:focus { border-color: var(--gold); }
  .score-sep {
    font-family: 'Impact', 'Arial Black', 'Arial Narrow', sans-serif; letter-spacing: 2px;
    font-size: 22px;
    color: var(--muted);
  }
  .match-meta {
    font-family: 'Arial Narrow', 'Helvetica Neue', Arial, sans-serif;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 0.5px;
    text-align: center;
    line-height: 1.4;
  }
  .match-date {
    font-size: 10px;
    color: var(--gold);
    letter-spacing: 1px;
    font-family: 'Arial Narrow', 'Helvetica Neue', Arial, sans-serif;
  }
  .expand-icon {
    font-size: 11px;
    color: var(--muted);
    margin-top: 2px;
  }

  /* DETAILS PANEL */
  .match-details {
    display: none;
    padding: 0 16px 16px;
    border-top: 1px solid var(--border);
    background: rgba(0,0,0,0.2);
  }
  .match-details.open { display: block; }

  .details-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
    padding-top: 14px;
  }
  @media (max-width: 600px) {
    .details-grid { grid-template-columns: 1fr; }
  }

  .detail-section h4 {
    font-family: 'Arial Narrow', 'Helvetica Neue', Arial, sans-serif;
    font-size: 11px;
    letter-spacing: 2px;
    color: var(--gold);
    text-transform: uppercase;
    margin-bottom: 8px;
    border-bottom: 1px solid var(--border);
    padding-bottom: 4px;
  }

  .event-row {
    display: flex;
    gap: 6px;
    margin-bottom: 6px;
    align-items: center;
  }
  .event-type {
    font-size: 14px;
    flex-shrink: 0;
  }
  .event-input {
    flex: 1;
    background: var(--navy);
    border: 1px solid rgba(136,153,187,0.2);
    border-radius: 4px;
    color: var(--white);
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Arial, sans-serif;
    font-size: 12px;
    padding: 5px 8px;
    outline: none;
    transition: border-color 0.2s;
  }
  .event-input:focus { border-color: var(--gold); }
  .event-input::placeholder { color: rgba(136,153,187,0.5); }
  .min-input {
    width: 46px;
    text-align: center;
    flex-shrink: 0;
  }
  .add-event-btn {
    background: none;
    border: 1px dashed rgba(201,168,76,0.3);
    border-radius: 4px;
    color: var(--muted);
    font-family: 'Arial Narrow', 'Helvetica Neue', Arial, sans-serif;
    font-size: 11px;
    letter-spacing: 1px;
    padding: 5px 10px;
    cursor: pointer;
    width: 100%;
    margin-top: 4px;
    transition: all 0.2s;
  }
  .add-event-btn:hover {
    border-color: var(--gold);
    color: var(--gold);
  }

  /* PENALTY / EXTRA FIELDS */
  .penalty-row {
    display: flex;
    gap: 8px;
    align-items: center;
    margin-top: 8px;
  }
  .penalty-label {
    font-family: 'Arial Narrow', 'Helvetica Neue', Arial, sans-serif;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 1px;
    min-width: 60px;
  }
  .pen-score-input {
    width: 36px;
    height: 30px;
    background: var(--navy);
    border: 1px solid rgba(230,57,70,0.4);
    border-radius: 4px;
    color: var(--red);
    font-family: 'Impact', 'Arial Black', 'Arial Narrow', sans-serif; letter-spacing: 2px;
    font-size: 18px;
    text-align: center;
    outline: none;
  }
  .pen-score-input:focus { border-color: var(--red); }

  /* POINTS BADGE */
  .points-row {
    display: flex;
    gap: 8px;
    align-items: center;
    margin-top: 10px;
    flex-wrap: wrap;
  }
  .pts-box {
    display: flex;
    align-items: center;
    gap: 6px;
    background: rgba(201,168,76,0.06);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 6px 10px;
    flex: 1;
    min-width: 120px;
  }
  .pts-box label {
    font-family: 'Arial Narrow', 'Helvetica Neue', Arial, sans-serif;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 1px;
    flex: 1;
  }
  .pts-select {
    background: var(--navy);
    border: 1px solid var(--border);
    border-radius: 3px;
    color: var(--gold-light);
    font-family: 'Arial Narrow', 'Helvetica Neue', Arial, sans-serif;
    font-size: 14px;
    font-weight: 700;
    padding: 2px 6px;
    outline: none;
    cursor: pointer;
  }
  .pts-select:focus { border-color: var(--gold); }

  .notes-input {
    width: 100%;
    background: var(--navy);
    border: 1px solid rgba(136,153,187,0.2);
    border-radius: 4px;
    color: var(--white);
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Arial, sans-serif;
    font-size: 12px;
    padding: 7px 10px;
    outline: none;
    resize: vertical;
    min-height: 50px;
    margin-top: 8px;
    transition: border-color 0.2s;
  }
  .notes-input:focus { border-color: var(--gold); }
  .notes-input::placeholder { color: rgba(136,153,187,0.4); }

  /* STANDINGS TABLE */
  .standings-table {
    width: 100%;
    border-collapse: collapse;
    font-family: 'Arial Narrow', 'Helvetica Neue', Arial, sans-serif;
    font-size: 14px;
    margin-top: 8px;
  }
  .standings-table th {
    font-size: 10px;
    letter-spacing: 2px;
    color: var(--gold);
    text-align: center;
    padding: 6px 8px;
    border-bottom: 1px solid var(--border);
    text-transform: uppercase;
  }
  .standings-table th:first-child { text-align: left; }
  .standings-table td {
    padding: 8px;
    text-align: center;
    border-bottom: 1px solid rgba(201,168,76,0.08);
    color: var(--white);
  }
  .standings-table td:first-child { text-align: left; font-weight: 600; }
  .standings-table tr:last-child td { border-bottom: none; }
  .rank-num {
    display: inline-block;
    width: 20px;
    height: 20px;
    border-radius: 50%;
    text-align: center;
    line-height: 20px;
    font-size: 11px;
    font-weight: 700;
    margin-right: 6px;
    background: rgba(201,168,76,0.12);
    color: var(--gold);
  }
  .rank-num.qualify { background: rgba(0,168,107,0.2); color: var(--green); }
  .rank-num.out { background: rgba(230,57,70,0.15); color: var(--red); }

  /* KNOCKOUT BRACKET */
  .knockout-info {
    background: var(--navy-card);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 20px;
    text-align: center;
    color: var(--muted);
    font-family: 'Arial Narrow', 'Helvetica Neue', Arial, sans-serif;
    font-size: 14px;
    letter-spacing: 1px;
  }
  .ko-stage {
    margin-bottom: 24px;
  }
  .ko-stage-title {
    font-family: 'Impact', 'Arial Black', 'Arial Narrow', sans-serif; letter-spacing: 2px;
    font-size: 20px;
    letter-spacing: 3px;
    color: var(--gold-light);
    margin-bottom: 12px;
    text-align: center;
  }
  .ko-match {
    background: var(--navy-card);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 12px 14px;
    margin-bottom: 8px;
  }
  .ko-match-header {
    display: grid;
    grid-template-columns: 1fr auto 1fr;
    align-items: center;
    gap: 8px;
    margin-bottom: 6px;
  }
  .ko-team { text-align: center; }
  .ko-team-input {
    width: 100%;
    background: rgba(201,168,76,0.05);
    border: 1px solid var(--border);
    border-radius: 4px;
    color: var(--white);
    font-family: 'Arial Narrow', 'Helvetica Neue', Arial, sans-serif;
    font-size: 13px;
    font-weight: 700;
    padding: 6px 8px;
    text-align: center;
    outline: none;
    letter-spacing: 0.5px;
  }
  .ko-team-input:focus { border-color: var(--gold); }
  .ko-team-input::placeholder { color: rgba(136,153,187,0.4); }
  .ko-score-row {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 6px;
  }
  .ko-meta {
    font-family: 'Arial Narrow', 'Helvetica Neue', Arial, sans-serif;
    font-size: 11px;
    color: var(--muted);
    text-align: center;
    margin-bottom: 6px;
    letter-spacing: 0.5px;
  }

  /* PRINT — only applies when printing */

  /* SAVE BUTTON */
  .save-bar {
    background: var(--navy-mid);
    border-top: 1px solid var(--border);
    padding: 12px 20px;
    text-align: center;
    position: sticky;
    bottom: 0;
    z-index: 10;
    display: flex;
    gap: 10px;
    justify-content: center;
    flex-wrap: wrap;
  }
  .action-btn {
    background: linear-gradient(135deg, var(--gold), #A07830);
    border: none;
    border-radius: 4px;
    color: var(--navy);
    font-family: 'Arial Narrow', 'Helvetica Neue', Arial, sans-serif;
    font-size: 14px;
    font-weight: 700;
    letter-spacing: 2px;
    padding: 10px 24px;
    cursor: pointer;
    text-transform: uppercase;
    transition: opacity 0.2s;
  }
  .action-btn:hover { opacity: 0.85; }
  .action-btn.secondary {
    background: transparent;
    border: 1px solid var(--border);
    color: var(--muted);
  }
  .action-btn.secondary:hover { border-color: var(--gold); color: var(--gold); }

  .saved-toast {
    display: none;
    font-family: 'Arial Narrow', 'Helvetica Neue', Arial, sans-serif;
    font-size: 13px;
    color: var(--green);
    letter-spacing: 1px;
    align-items: center;
    gap: 6px;
  }

  /* PRINT MODAL */
  .modal-overlay {
    display: none;
    position: fixed;
    inset: 0;
    background: rgba(0,0,0,0.75);
    z-index: 100;
    align-items: center;
    justify-content: center;
    padding: 20px;
  }
  .modal-overlay.open { display: flex; }
  .modal-box {
    background: var(--navy-mid);
    border: 1px solid var(--gold);
    border-radius: 10px;
    width: 100%;
    max-width: 520px;
    max-height: 85vh;
    overflow-y: auto;
    padding: 24px;
  }
  .modal-title {
    font-family: 'Impact', 'Arial Black', 'Arial Narrow', sans-serif; letter-spacing: 2px;
    font-size: 24px;
    letter-spacing: 3px;
    color: var(--gold-light);
    margin-bottom: 4px;
  }
  .modal-sub {
    font-family: 'Arial Narrow', 'Helvetica Neue', Arial, sans-serif;
    font-size: 12px;
    color: var(--muted);
    letter-spacing: 1px;
    margin-bottom: 18px;
  }
  .print-section-title {
    font-family: 'Arial Narrow', 'Helvetica Neue', Arial, sans-serif;
    font-size: 11px;
    letter-spacing: 2px;
    color: var(--gold);
    text-transform: uppercase;
    border-bottom: 1px solid var(--border);
    padding-bottom: 4px;
    margin: 14px 0 8px;
  }
  .print-options-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 8px;
  }
  .print-option {
    display: flex;
    align-items: center;
    gap: 8px;
    background: rgba(201,168,76,0.05);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 8px 10px;
    cursor: pointer;
    transition: all 0.15s;
    font-family: 'Arial Narrow', 'Helvetica Neue', Arial, sans-serif;
    font-size: 13px;
    color: var(--white);
    letter-spacing: 0.3px;
    user-select: none;
  }
  .print-option:hover { border-color: var(--gold); background: rgba(201,168,76,0.1); }
  .print-option input[type=checkbox] { accent-color: var(--gold); width: 15px; height: 15px; flex-shrink: 0; cursor: pointer; }
  .print-option.full-row { grid-column: 1 / -1; }
  .modal-actions {
    display: flex;
    gap: 10px;
    margin-top: 20px;
    flex-wrap: wrap;
  }
  .print-details-toggle {
    display: flex;
    align-items: center;
    gap: 8px;
    margin-top: 10px;
    font-family: 'Arial Narrow', 'Helvetica Neue', Arial, sans-serif;
    font-size: 12px;
    color: var(--muted);
    letter-spacing: 1px;
    cursor: pointer;
  }
  .print-details-toggle input { accent-color: var(--gold); }

  @media print {
    .save-bar, .tabs-wrapper, header, .modal-overlay { display: none !important; }
    body { background: white !important; color: black !important; }
    .panel { display: block !important; padding: 10px !important; }
    .match-card { border: 1px solid #ccc !important; break-inside: avoid; margin-bottom: 8px; background: white !important; }
    .match-header { background: white !important; }
    .team-name, .match-meta, .match-date { color: black !important; }
    .score-input { border: 1px solid #999 !important; background: white !important; color: black !important; font-size: 18px !important; }
    .score-sep { color: #333 !important; }
    .group-label { color: black !important; background: #f0f0f0 !important; border: 1px solid #ccc !important; }
    .group-teams { color: #444 !important; }
    .match-details { border-top: 1px solid #ddd !important; background: #fafafa !important; }
    .match-details.open { display: block !important; }
    .event-input, .notes-input, .pen-score-input, .pts-select { border: 1px solid #bbb !important; background: white !important; color: black !important; }
    .detail-section h4 { color: #555 !important; border-bottom: 1px solid #ddd !important; }
    .add-event-btn { display: none !important; }
    .expand-icon { display: none !important; }
    .ko-team-input { border: 1px solid #bbb !important; background: white !important; color: black !important; }
    .standings-table th { color: #555 !important; }
    .standings-table td { color: black !important; }
    .ko-stage-title { color: black !important; }
    details { display: block !important; }
    details summary { display: none !important; }

    .print-hide { display: none !important; }
    .print-show { display: block !important; }
  }

</style>
</head>
<body>

<header>
  <div class="header-flag-strip">
    <div class="flag-dot" style="background:#CE1126"></div>
    <div class="flag-dot" style="background:#FFFFFF"></div>
    <div class="flag-dot" style="background:#003087"></div>
    <div class="flag-dot" style="background:#009B3A"></div>
    <div class="flag-dot" style="background:#FFD700"></div>
    <div class="flag-dot" style="background:#C8102E"></div>
    <div class="flag-dot" style="background:#0032A0"></div>
    <div class="flag-dot" style="background:#FFFFFF"></div>
    <div class="flag-dot" style="background:#D52B1E"></div>
    <div class="flag-dot" style="background:#00843D"></div>
    <div class="flag-dot" style="background:#EF3340"></div>
    <div class="flag-dot" style="background:#002395"></div>
  </div>
  <h1>⚽ FIFA WORLD CUP 2026</h1>
  <div class="sub">Official Match Scoresheet · USA · Canada · Mexico</div>
  <div class="host-badge">🗓 June 11 – July 19, 2026 &nbsp;|&nbsp; 48 Teams &nbsp;|&nbsp; 104 Matches &nbsp;|&nbsp; 16 Cities</div>
</header>

<div class="tabs-wrapper">
  <div class="tabs">
    <button class="tab-btn active" onclick="showTab('groups')">Group Stage</button>
    <button class="tab-btn" onclick="showTab('r32')">Round of 32</button>
    <button class="tab-btn" onclick="showTab('r16')">Round of 16</button>
    <button class="tab-btn" onclick="showTab('qf')">Quarterfinals</button>
    <button class="tab-btn" onclick="showTab('sf')">Semifinals</button>
    <button class="tab-btn" onclick="showTab('final')">Final</button>
  </div>
</div>

<div id="groups" class="panel active"></div>
<div id="r32" class="panel"></div>
<div id="r16" class="panel"></div>
<div id="qf" class="panel"></div>
<div id="sf" class="panel"></div>
<div id="final" class="panel"></div>

<!-- PRINT MODAL -->
<div class="modal-overlay" id="printModal">
  <div class="modal-box">
    <div class="modal-title">🖨 Print Options</div>
    <div class="modal-sub">Choose exactly what to print</div>

    <div class="print-section-title">📋 Group Stage</div>
    <div class="print-options-grid">
      <label class="print-option full-row">
        <input type="checkbox" id="po-all-groups" onchange="toggleAllGroups(this)"> All Groups (A–L)
      </label>
      <label class="print-option"><input type="checkbox" class="po-group" value="A"> Group A</label>
      <label class="print-option"><input type="checkbox" class="po-group" value="B"> Group B</label>
      <label class="print-option"><input type="checkbox" class="po-group" value="C"> Group C</label>
      <label class="print-option"><input type="checkbox" class="po-group" value="D"> Group D</label>
      <label class="print-option"><input type="checkbox" class="po-group" value="E"> Group E</label>
      <label class="print-option"><input type="checkbox" class="po-group" value="F"> Group F</label>
      <label class="print-option"><input type="checkbox" class="po-group" value="G"> Group G</label>
      <label class="print-option"><input type="checkbox" class="po-group" value="H"> Group H</label>
      <label class="print-option"><input type="checkbox" class="po-group" value="I"> Group I</label>
      <label class="print-option"><input type="checkbox" class="po-group" value="J"> Group J</label>
      <label class="print-option"><input type="checkbox" class="po-group" value="K"> Group K</label>
      <label class="print-option"><input type="checkbox" class="po-group" value="L"> Group L</label>
    </div>

    <div class="print-section-title">⚡ Knockout Rounds</div>
    <div class="print-options-grid">
      <label class="print-option full-row">
        <input type="checkbox" id="po-all-ko" onchange="toggleAllKO(this)"> All Knockout Rounds
      </label>
      <label class="print-option"><input type="checkbox" class="po-ko" value="r32"> Round of 32</label>
      <label class="print-option"><input type="checkbox" class="po-ko" value="r16"> Round of 16</label>
      <label class="print-option"><input type="checkbox" class="po-ko" value="qf"> Quarterfinals</label>
      <label class="print-option"><input type="checkbox" class="po-ko" value="sf"> Semifinals</label>
      <label class="print-option full-row"><input type="checkbox" class="po-ko" value="final"> 🏆 Final & 3rd Place</label>
    </div>

    <div class="print-section-title">⚽ Single Match</div>
    <div style="font-family:'Barlow Condensed';font-size:12px;color:var(--muted);margin-bottom:8px;letter-spacing:0.5px">
      Print just one specific match card
    </div>
    <div style="display:flex;gap:8px;flex-wrap:wrap;align-items:center">
      <select id="po-match-group" onchange="populateMatchList()" style="background:var(--navy);border:1px solid var(--border);border-radius:4px;color:var(--white);font-family:'Barlow Condensed';font-size:13px;padding:7px 10px;outline:none;flex:1;min-width:120px">
        <option value="">— Select Group / Stage —</option>
        <option value="A">Group A</option>
        <option value="B">Group B</option>
        <option value="C">Group C</option>
        <option value="D">Group D</option>
        <option value="E">Group E</option>
        <option value="F">Group F</option>
        <option value="G">Group G</option>
        <option value="H">Group H</option>
        <option value="I">Group I</option>
        <option value="J">Group J</option>
        <option value="K">Group K</option>
        <option value="L">Group L</option>
        <option value="ko">Knockout Match</option>
      </select>
      <select id="po-match-pick" style="background:var(--navy);border:1px solid var(--border);border-radius:4px;color:var(--white);font-family:'Barlow Condensed';font-size:13px;padding:7px 10px;outline:none;flex:2;min-width:180px">
        <option value="">— Select Match —</option>
      </select>
    </div>
    <button class="add-event-btn" onclick="printSingleMatch()" style="margin-top:8px;width:auto;padding:7px 18px">🖨 Print This Match Only</button>

    <div class="print-section-title" style="margin-top:16px">⚙️ Print Settings</div>
    <label class="print-details-toggle">
      <input type="checkbox" id="po-details" checked>
      Include detail fields (scorers, cards, notes, penalties)
    </label>
    <label class="print-details-toggle" style="margin-top:6px">
      <input type="checkbox" id="po-standings" checked>
      Include group standings tables
    </label>

    <div class="modal-actions">
      <button class="action-btn" onclick="executePrint()">🖨 Print Selected Sections</button>
      <button class="action-btn secondary" onclick="closePrintModal()">✕ Cancel</button>
    </div>
  </div>
</div>

<div class="save-bar">
  <button class="action-btn secondary" onclick="openPrintModal()">🖨 Print / Save PDF</button>
  <button class="action-btn" onclick="saveData()">💾 Save Progress</button>
  <div class="saved-toast" id="savedToast">✓ Saved locally!</div>
</div>

<script>
// ============================================================
// DATA
// ============================================================
const groups = [
  { id:'A', teams:['🇲🇽 Mexico','🇰🇷 South Korea','🇿🇦 South Africa','🇨🇿 Czechia'], matches:[
    {date:'Jun 11',venue:'Mexico City Stadium',home:'Mexico',away:'South Africa'},
    {date:'Jun 11',venue:'Estadio Guadalajara',home:'South Korea',away:'Czechia'},
    {date:'Jun 18',venue:'Atlanta Stadium',home:'Czechia',away:'South Africa'},
    {date:'Jun 18',venue:'Estadio Guadalajara',home:'Mexico',away:'South Korea'},
    {date:'Jun 24',venue:'Mexico City Stadium',home:'Czechia',away:'Mexico'},
    {date:'Jun 24',venue:'Estadio Monterrey',home:'South Africa',away:'South Korea'},
  ]},
  { id:'B', teams:['🇨🇦 Canada','🇨🇭 Switzerland','🇶🇦 Qatar','🇧🇦 Bosnia-Herz.'], matches:[
    {date:'Jun 12',venue:'Toronto Stadium',home:'Canada',away:'Bosnia-Herz.'},
    {date:'Jun 13',venue:'SF Bay Area Stadium',home:'Qatar',away:'Switzerland'},
    {date:'Jun 18',venue:'Los Angeles Stadium',home:'Switzerland',away:'Bosnia-Herz.'},
    {date:'Jun 18',venue:'BC Place, Vancouver',home:'Canada',away:'Qatar'},
    {date:'Jun 24',venue:'BC Place, Vancouver',home:'Switzerland',away:'Canada'},
    {date:'Jun 24',venue:'Seattle Stadium',home:'Qatar',away:'Bosnia-Herz.'},
  ]},
  { id:'C', teams:['🇧🇷 Brazil','🇲🇦 Morocco','🏴󠁧󠁢󠁳󠁣󠁴󠁿 Scotland','🇭🇹 Haiti'], matches:[
    {date:'Jun 13',venue:'New York/NJ Stadium',home:'Brazil',away:'Morocco'},
    {date:'Jun 13',venue:'Boston Stadium',home:'Haiti',away:'Scotland'},
    {date:'Jun 19',venue:'Boston Stadium',home:'Scotland',away:'Morocco'},
    {date:'Jun 19',venue:'Philadelphia Stadium',home:'Brazil',away:'Haiti'},
    {date:'Jun 24',venue:'Miami Stadium',home:'Scotland',away:'Brazil'},
    {date:'Jun 24',venue:'Atlanta Stadium',home:'Morocco',away:'Haiti'},
  ]},
  { id:'D', teams:['🇺🇸 USA','🇦🇺 Australia','🇵🇾 Paraguay','🇹🇷 Türkiye'], matches:[
    {date:'Jun 12',venue:'Los Angeles Stadium',home:'USA',away:'Paraguay'},
    {date:'Jun 13',venue:'BC Place, Vancouver',home:'Australia',away:'Türkiye'},
    {date:'Jun 19',venue:'Seattle Stadium',home:'USA',away:'Australia'},
    {date:'Jun 19',venue:'SF Bay Area Stadium',home:'Türkiye',away:'Paraguay'},
    {date:'Jun 25',venue:'Los Angeles Stadium',home:'Türkiye',away:'USA'},
    {date:'Jun 25',venue:'SF Bay Area Stadium',home:'Paraguay',away:'Australia'},
  ]},
  { id:'E', teams:['🇩🇪 Germany','🇪🇨 Ecuador','🇨🇮 Ivory Coast','🇨🇼 Curaçao'], matches:[
    {date:'Jun 14',venue:'Houston Stadium',home:'Germany',away:'Curaçao'},
    {date:'Jun 14',venue:'Philadelphia Stadium',home:'Ivory Coast',away:'Ecuador'},
    {date:'Jun 20',venue:'Houston Stadium',home:'Netherlands',away:'Curaçao'},
    {date:'Jun 20',venue:'Toronto Stadium',home:'Germany',away:'Ivory Coast'},
    {date:'Jun 25',venue:'New York/NJ Stadium',home:'Ecuador',away:'Germany'},
    {date:'Jun 25',venue:'Philadelphia Stadium',home:'Curaçao',away:'Ivory Coast'},
  ]},
  { id:'F', teams:['🇳🇱 Netherlands','🇯🇵 Japan','🇹🇳 Tunisia','🇺🇦 Ukraine'], matches:[
    {date:'Jun 14',venue:'Dallas Stadium',home:'Netherlands',away:'Japan'},
    {date:'Jun 14',venue:'Estadio Monterrey',home:'Ukraine',away:'Tunisia'},
    {date:'Jun 20',venue:'Estadio Monterrey',home:'Tunisia',away:'Japan'},
    {date:'Jun 20',venue:'Houston Stadium',home:'Netherlands',away:'Ukraine'},
    {date:'Jun 25',venue:'Dallas Stadium',home:'Japan',away:'Ukraine'},
    {date:'Jun 25',venue:'Kansas City Stadium',home:'Tunisia',away:'Netherlands'},
  ]},
  { id:'G', teams:['🇧🇪 Belgium','🇮🇷 Iran','🇪🇬 Egypt','🇳🇿 New Zealand'], matches:[
    {date:'Jun 15',venue:'BC Place, Vancouver',home:'Belgium',away:'Egypt'},
    {date:'Jun 15',venue:'Los Angeles Stadium',home:'Iran',away:'New Zealand'},
    {date:'Jun 21',venue:'Los Angeles Stadium',home:'Belgium',away:'Iran'},
    {date:'Jun 21',venue:'BC Place, Vancouver',home:'New Zealand',away:'Egypt'},
    {date:'Jun 26',venue:'Seattle Stadium',home:'Egypt',away:'Iran'},
    {date:'Jun 26',venue:'BC Place, Vancouver',home:'New Zealand',away:'Belgium'},
  ]},
  { id:'H', teams:['🇪🇸 Spain','🇺🇾 Uruguay','🇸🇦 Saudi Arabia','🇨🇻 Cape Verde'], matches:[
    {date:'Jun 15',venue:'Atlanta Stadium',home:'Spain',away:'Cape Verde'},
    {date:'Jun 15',venue:'Miami Stadium',home:'Saudi Arabia',away:'Uruguay'},
    {date:'Jun 21',venue:'Atlanta Stadium',home:'Spain',away:'Saudi Arabia'},
    {date:'Jun 21',venue:'Miami Stadium',home:'Uruguay',away:'Cape Verde'},
    {date:'Jun 26',venue:'Houston Stadium',home:'Cape Verde',away:'Saudi Arabia'},
    {date:'Jun 26',venue:'Estadio Guadalajara',home:'Uruguay',away:'Spain'},
  ]},
  { id:'I', teams:['🇫🇷 France','🇸🇳 Senegal','🇳🇴 Norway','🇮🇶 Iraq'], matches:[
    {date:'Jun 16',venue:'New York/NJ Stadium',home:'France',away:'Senegal'},
    {date:'Jun 16',venue:'Boston Stadium',home:'Iraq',away:'Norway'},
    {date:'Jun 22',venue:'Philadelphia Stadium',home:'France',away:'Iraq'},
    {date:'Jun 22',venue:'New York/NJ Stadium',home:'Norway',away:'Senegal'},
    {date:'Jun 26',venue:'Boston Stadium',home:'Norway',away:'France'},
    {date:'Jun 26',venue:'Toronto Stadium',home:'Senegal',away:'Iraq'},
  ]},
  { id:'J', teams:['🇦🇷 Argentina','🇦🇹 Austria','🇩🇿 Algeria','🇯🇴 Jordan'], matches:[
    {date:'Jun 16',venue:'Kansas City Stadium',home:'Argentina',away:'Algeria'},
    {date:'Jun 16',venue:'SF Bay Area Stadium',home:'Austria',away:'Jordan'},
    {date:'Jun 22',venue:'Dallas Stadium',home:'Argentina',away:'Austria'},
    {date:'Jun 22',venue:'SF Bay Area Stadium',home:'Jordan',away:'Algeria'},
    {date:'Jun 27',venue:'Kansas City Stadium',home:'Algeria',away:'Austria'},
    {date:'Jun 27',venue:'Dallas Stadium',home:'Jordan',away:'Argentina'},
  ]},
  { id:'K', teams:['🇵🇹 Portugal','🇨🇴 Colombia','🇺🇿 Uzbekistan','🇨🇩 DR Congo'], matches:[
    {date:'Jun 17',venue:'Houston Stadium',home:'Portugal',away:'DR Congo'},
    {date:'Jun 17',venue:'Mexico City Stadium',home:'Uzbekistan',away:'Colombia'},
    {date:'Jun 23',venue:'Houston Stadium',home:'Portugal',away:'Uzbekistan'},
    {date:'Jun 23',venue:'Estadio Guadalajara',home:'Colombia',away:'DR Congo'},
    {date:'Jun 27',venue:'Miami Stadium',home:'Colombia',away:'Portugal'},
    {date:'Jun 27',venue:'Atlanta Stadium',home:'DR Congo',away:'Uzbekistan'},
  ]},
  { id:'L', teams:['🏴󠁧󠁢󠁥󠁮󠁧󠁿 England','🇭🇷 Croatia','🇵🇦 Panama','🇬🇭 Ghana'], matches:[
    {date:'Jun 17',venue:'Dallas Stadium',home:'England',away:'Croatia'},
    {date:'Jun 17',venue:'Toronto Stadium',home:'Ghana',away:'Panama'},
    {date:'Jun 23',venue:'Boston Stadium',home:'England',away:'Ghana'},
    {date:'Jun 23',venue:'Toronto Stadium',home:'Panama',away:'Croatia'},
    {date:'Jun 27',venue:'New York/NJ Stadium',home:'Panama',away:'England'},
    {date:'Jun 27',venue:'Philadelphia Stadium',home:'Croatia',away:'Ghana'},
  ]},
];

const knockoutStages = {
  r32: {
    label: 'Round of 32',
    dates: 'June 28 – July 3',
    matches: [
      {id:'r32-1', date:'Jun 28', venue:'Los Angeles Stadium', label:'Match 73'},
      {id:'r32-2', date:'Jun 29', venue:'Houston Stadium', label:'Match 76'},
      {id:'r32-3', date:'Jun 29', venue:'Boston Stadium', label:'Match 74'},
      {id:'r32-4', date:'Jun 29', venue:'Estadio Monterrey', label:'Match 75'},
      {id:'r32-5', date:'Jun 30', venue:'Dallas Stadium', label:'Match 78'},
      {id:'r32-6', date:'Jun 30', venue:'New York/NJ Stadium', label:'Match 77'},
      {id:'r32-7', date:'Jun 30', venue:'Mexico City Stadium', label:'Match 79'},
      {id:'r32-8', date:'Jul 1', venue:'Atlanta Stadium', label:'Match 80'},
      {id:'r32-9', date:'Jul 1', venue:'Seattle Stadium', label:'Match 82'},
      {id:'r32-10', date:'Jul 1', venue:'SF Bay Area Stadium', label:'Match 81'},
      {id:'r32-11', date:'Jul 2', venue:'Los Angeles Stadium', label:'Match 84'},
      {id:'r32-12', date:'Jul 2', venue:'Toronto Stadium', label:'Match 83'},
      {id:'r32-13', date:'Jul 2', venue:'BC Place, Vancouver', label:'Match 85'},
      {id:'r32-14', date:'Jul 3', venue:'Dallas Stadium', label:'Match 88'},
      {id:'r32-15', date:'Jul 3', venue:'Miami Stadium', label:'Match 86'},
      {id:'r32-16', date:'Jul 3', venue:'Kansas City Stadium', label:'Match 87'},
    ]
  },
  r16: {
    label: 'Round of 16',
    dates: 'July 4 – 7',
    matches: [
      {id:'r16-1', date:'Jul 4', venue:'Houston Stadium', label:'Match 90'},
      {id:'r16-2', date:'Jul 4', venue:'Philadelphia Stadium', label:'Match 89'},
      {id:'r16-3', date:'Jul 5', venue:'New York/NJ Stadium', label:'Match 91'},
      {id:'r16-4', date:'Jul 5', venue:'Kansas City Stadium', label:'Match 92'},
      {id:'r16-5', date:'Jul 6', venue:'Los Angeles Stadium', label:'Match 93'},
      {id:'r16-6', date:'Jul 6', venue:'Atlanta Stadium', label:'Match 94'},
      {id:'r16-7', date:'Jul 7', venue:'Seattle Stadium', label:'Match 95'},
      {id:'r16-8', date:'Jul 7', venue:'Dallas Stadium', label:'Match 96'},
    ]
  },
  qf: {
    label: 'Quarterfinals',
    dates: 'July 9 – 11',
    matches: [
      {id:'qf-1', date:'Jul 9', venue:'Miami Stadium', label:'QF 1'},
      {id:'qf-2', date:'Jul 10', venue:'New York/NJ Stadium', label:'QF 2'},
      {id:'qf-3', date:'Jul 10', venue:'Los Angeles Stadium', label:'QF 3'},
      {id:'qf-4', date:'Jul 11', venue:'Dallas Stadium', label:'QF 4'},
    ]
  },
  sf: {
    label: 'Semifinals',
    dates: 'July 14 – 15',
    matches: [
      {id:'sf-1', date:'Jul 14', venue:'Atlanta Stadium', label:'SF 1'},
      {id:'sf-2', date:'Jul 15', venue:'Dallas Stadium', label:'SF 2'},
    ]
  },
  final: {
    label: 'Final & 3rd Place',
    dates: 'July 18 – 19',
    matches: [
      {id:'3rd', date:'Jul 18', venue:'Miami Stadium', label:'3rd Place'},
      {id:'final', date:'Jul 19', venue:'New York/NJ Stadium · MetLife', label:'🏆 THE FINAL'},
    ]
  }
};

// ============================================================
// RENDER GROUP STAGE
// ============================================================
function renderGroups() {
  const container = document.getElementById('groups');
  let html = '';
  groups.forEach(g => {
    const matchesHtml = g.matches.map((m, i) => {
      const mid = `g${g.id}-m${i}`;
      return `
      <div class="match-card" id="card-${mid}">
        <div class="match-header" onclick="toggleDetails('${mid}')">
          <div class="team-home">
            <div class="team-name">${m.home}</div>
          </div>
          <div class="score-center">
            <div class="match-date">${m.date}</div>
            <div class="score-inputs">
              <input class="score-input" id="sh-${mid}" type="number" min="0" max="30" placeholder="0" oninput="updatePts('${g.id}')">
              <span class="score-sep">–</span>
              <input class="score-input" id="sa-${mid}" type="number" min="0" max="30" placeholder="0" oninput="updatePts('${g.id}')">
            </div>
            <div class="match-meta">${m.venue}</div>
            <div class="expand-icon" id="icon-${mid}">▼ Details</div>
          </div>
          <div class="team-away">
            <div class="team-name">${m.away}</div>
          </div>
        </div>
        <div class="match-details" id="det-${mid}">
          <div class="details-grid">
            <div class="detail-section">
              <h4>⚽ Goals — ${m.home}</h4>
              <div id="goals-home-${mid}">
                ${goalRow(mid,'home',0)}
              </div>
              <button class="add-event-btn" onclick="addGoal('${mid}','home')">+ Add Goal</button>
            </div>
            <div class="detail-section">
              <h4>⚽ Goals — ${m.away}</h4>
              <div id="goals-away-${mid}">
                ${goalRow(mid,'away',0)}
              </div>
              <button class="add-event-btn" onclick="addGoal('${mid}','away')">+ Add Goal</button>
            </div>
            <div class="detail-section">
              <h4>🟨 Cards & Events — ${m.home}</h4>
              <div id="cards-home-${mid}">
                ${cardRow(mid,'home',0)}
              </div>
              <button class="add-event-btn" onclick="addCard('${mid}','home')">+ Add Card/Event</button>
            </div>
            <div class="detail-section">
              <h4>🟨 Cards & Events — ${m.away}</h4>
              <div id="cards-away-${mid}">
                ${cardRow(mid,'away',0)}
              </div>
              <button class="add-event-btn" onclick="addCard('${mid}','away')">+ Add Card/Event</button>
            </div>
          </div>

          <div class="detail-section" style="margin-top:12px">
            <h4>🎯 Penalty Shootout (if applicable)</h4>
            <div class="penalty-row">
              <span class="penalty-label">${m.home}</span>
              <input class="pen-score-input" id="pen-h-${mid}" type="number" min="0" max="10" placeholder="–">
              <span style="color:var(--muted);font-family:'Barlow Condensed';font-size:13px">vs</span>
              <input class="pen-score-input" id="pen-a-${mid}" type="number" min="0" max="10" placeholder="–">
              <span class="penalty-label" style="margin-left:4px">${m.away}</span>
            </div>
          </div>

          <div class="detail-section" style="margin-top:12px">
            <h4>📊 Points Awarded</h4>
            <div class="points-row">
              <div class="pts-box">
                <label>${m.home} Points</label>
                <select class="pts-select" id="pts-h-${mid}">
                  <option value="">–</option>
                  <option value="3">3 (Win)</option>
                  <option value="1">1 (Draw)</option>
                  <option value="0">0 (Loss)</option>
                </select>
              </div>
              <div class="pts-box">
                <label>${m.away} Points</label>
                <select class="pts-select" id="pts-a-${mid}">
                  <option value="">–</option>
                  <option value="3">3 (Win)</option>
                  <option value="1">1 (Draw)</option>
                  <option value="0">0 (Loss)</option>
                </select>
              </div>
            </div>
          </div>

          <div class="detail-section" style="margin-top:12px">
            <h4>📝 Notes</h4>
            <textarea class="notes-input" id="notes-${mid}" placeholder="VAR decisions, key moments, injuries, weather…"></textarea>
          </div>
        </div>
      </div>`;
    }).join('');

    // Standings table
    const teamNames = g.teams.map(t => t.replace(/^[^\s]+ /,''));
    const standingsRows = teamNames.map((t,i) => {
      const rank = i < 2 ? 'qualify' : 'out';
      return `<tr>
        <td><span class="rank-num ${rank}">${i+1}</span>${g.teams[i]}</td>
        <td id="std-p-${g.id}-${i}">0</td>
        <td id="std-gf-${g.id}-${i}">0</td>
        <td id="std-ga-${g.id}-${i}">0</td>
        <td id="std-gd-${g.id}-${i}">0</td>
        <td id="std-pts-${g.id}-${i}" style="color:var(--gold-light);font-weight:700">0</td>
      </tr>`;
    }).join('');

    html += `
    <div class="group-section" id="grp-section-${g.id}">
      <div class="group-header">
        <div class="group-label">GROUP ${g.id}</div>
        <div class="group-teams">${g.teams.join(' · ')}</div>
      </div>
      ${matchesHtml}
      <details style="margin-top:8px">
        <summary style="font-family:'Barlow Condensed';font-size:12px;letter-spacing:2px;color:var(--muted);cursor:pointer;padding:6px 0;text-transform:uppercase">▶ Group ${g.id} Standings</summary>
        <div style="background:var(--navy-card);border:1px solid var(--border);border-radius:6px;padding:10px;margin-top:6px;overflow-x:auto">
          <table class="standings-table">
            <thead><tr>
              <th style="text-align:left">Team</th>
              <th>P</th><th>GF</th><th>GA</th><th>GD</th><th>Pts</th>
            </tr></thead>
            <tbody id="std-${g.id}">${standingsRows}</tbody>
          </table>
        </div>
      </details>
    </div>`;
  });
  container.innerHTML = html;
}

function goalRow(mid, side, idx) {
  return `<div class="event-row">
    <span class="event-type">⚽</span>
    <input class="event-input" id="g-pl-${mid}-${side}-${idx}" placeholder="Player name" type="text">
    <input class="event-input min-input" id="g-mn-${mid}-${side}-${idx}" placeholder="Min" type="text" style="width:46px">
    <select class="event-input" id="g-tp-${mid}-${side}-${idx}" style="width:70px">
      <option value="goal">Goal</option>
      <option value="pen">Pen ⚽</option>
      <option value="og">OG</option>
    </select>
  </div>`;
}

function cardRow(mid, side, idx) {
  return `<div class="event-row">
    <select class="event-input" id="c-tp-${mid}-${side}-${idx}" style="width:50px;flex-shrink:0">
      <option value="Y">🟨</option>
      <option value="R">🟥</option>
      <option value="YR">🟨🟥</option>
      <option value="sub">🔄</option>
    </select>
    <input class="event-input" id="c-pl-${mid}-${side}-${idx}" placeholder="Player name" type="text">
    <input class="event-input min-input" id="c-mn-${mid}-${side}-${idx}" placeholder="Min" type="text">
  </div>`;
}

let goalCounts = {};
let cardCounts = {};

function addGoal(mid, side) {
  const key = `${mid}-${side}`;
  goalCounts[key] = (goalCounts[key] || 1) + 1;
  const idx = goalCounts[key] - 1;
  const el = document.getElementById(`goals-${side}-${mid}`);
  el.insertAdjacentHTML('beforeend', goalRow(mid, side, idx));
}

function addCard(mid, side) {
  const key = `${mid}-${side}`;
  cardCounts[key] = (cardCounts[key] || 1) + 1;
  const idx = cardCounts[key] - 1;
  const el = document.getElementById(`cards-${side}-${mid}`);
  el.insertAdjacentHTML('beforeend', cardRow(mid, side, idx));
}

function updateKoLabels(mid) {
  const homeVal = (document.getElementById(mid + '-home')?.value.trim()) || 'Team A';
  const awayVal = (document.getElementById(mid + '-away')?.value.trim()) || 'Team B';

  const set = (id, text) => { const el = document.getElementById(id); if (el) el.textContent = text; };

  set('lbl-goals-home-' + mid, '⚽ Goals — ' + homeVal);
  set('lbl-goals-away-' + mid, '⚽ Goals — ' + awayVal);
  set('lbl-cards-home-' + mid, '🟨 Cards & Events — ' + homeVal);
  set('lbl-cards-away-' + mid, '🟨 Cards & Events — ' + awayVal);
  set('lbl-pen-home-' + mid, homeVal);
  set('lbl-pen-away-' + mid, awayVal);
  set('lbl-et-home-' + mid, homeVal);
  set('lbl-et-away-' + mid, awayVal);
}

function toggleDetails(mid) {
  const det = document.getElementById(`det-${mid}`);
  const icon = document.getElementById(`icon-${mid}`);
  det.classList.toggle('open');
  icon.textContent = det.classList.contains('open') ? '▲ Close' : '▼ Details';
}

// ============================================================
// LIVE STANDINGS ENGINE — auto-calculates on every score input
// ============================================================
function updatePts(groupId) {
  const group = groups.find(g => g.id === groupId);
  if (!group) return;

  // Build a stats map for each team
  const stats = {};
  group.teams.forEach(t => {
    const name = t.replace(/^\S+\s/, ''); // strip emoji
    stats[name] = { team: t, p: 0, w: 0, d: 0, l: 0, gf: 0, ga: 0, gd: 0, pts: 0 };
  });

  group.matches.forEach((m, i) => {
    const mid = `g${groupId}-m${i}`;
    const shEl = document.getElementById(`sh-${mid}`);
    const saEl = document.getElementById(`sa-${mid}`);
    if (!shEl || !saEl) return;

    const shVal = shEl.value.trim();
    const saVal = saEl.value.trim();
    if (shVal === '' || saVal === '') return; // skip unplayed

    const sh = parseInt(shVal, 10);
    const sa = parseInt(saVal, 10);
    if (isNaN(sh) || isNaN(sa)) return;

    const home = m.home;
    const away = m.away;
    if (!stats[home] || !stats[away]) return;

    stats[home].p++;
    stats[away].p++;
    stats[home].gf += sh;
    stats[home].ga += sa;
    stats[away].gf += sa;
    stats[away].ga += sh;
    stats[home].gd = stats[home].gf - stats[home].ga;
    stats[away].gd = stats[away].gf - stats[away].ga;

    if (sh > sa) {
      stats[home].w++; stats[home].pts += 3;
      stats[away].l++;
    } else if (sh < sa) {
      stats[away].w++; stats[away].pts += 3;
      stats[home].l++;
    } else {
      stats[home].d++; stats[home].pts += 1;
      stats[away].d++; stats[away].pts += 1;
    }

    // Auto-set points selectors
    const ptsH = document.getElementById(`pts-h-${mid}`);
    const ptsA = document.getElementById(`pts-a-${mid}`);
    if (ptsH && ptsA) {
      if (sh > sa)       { ptsH.value = '3'; ptsA.value = '0'; }
      else if (sh < sa)  { ptsH.value = '0'; ptsA.value = '3'; }
      else               { ptsH.value = '1'; ptsA.value = '1'; }
    }
  });

  // Sort: pts → gd → gf → team name
  const sorted = Object.values(stats).sort((a, b) => {
    if (b.pts !== a.pts) return b.pts - a.pts;
    if (b.gd  !== a.gd)  return b.gd  - a.gd;
    if (b.gf  !== a.gf)  return b.gf  - a.gf;
    return a.team.localeCompare(b.team);
  });

  // Re-render standings tbody
  const tbody = document.getElementById(`std-${groupId}`);
  if (!tbody) return;
  tbody.innerHTML = sorted.map((s, i) => {
    const rankClass = i < 2 ? 'qualify' : 'out';
    const gdStr = s.gd > 0 ? `+${s.gd}` : `${s.gd}`;
    const ptsColor = i < 2 ? 'var(--green)' : (i >= 2 && s.p > 0 ? 'var(--red)' : 'var(--gold-light)');
    return `<tr>
      <td><span class="rank-num ${rankClass}">${i+1}</span>${s.team}</td>
      <td>${s.p}</td>
      <td>${s.gf}</td>
      <td>${s.ga}</td>
      <td>${gdStr}</td>
      <td style="color:${ptsColor};font-weight:700;font-size:16px">${s.pts}</td>
    </tr>`;
  }).join('');

  // Auto-open the standings details so user sees the update
  const detailsEl = tbody.closest('details');
  if (detailsEl) detailsEl.open = true;
}

// ============================================================
// RENDER KNOCKOUT STAGE
// ============================================================
function renderKnockout(stageKey, containerId) {
  const stage = knockoutStages[stageKey];
  const container = document.getElementById(containerId);
  let html = `<div class="ko-stage">
    <div class="ko-stage-title">${stage.label} · ${stage.dates}</div>`;

  stage.matches.forEach(m => {
    const mid = m.id;
    html += `
    <div class="match-card" id="card-${mid}">
      <div class="match-header" onclick="toggleDetails('${mid}')">
        <div class="team-home">
          <input class="ko-team-input" id="${mid}-home" placeholder="Team A" type="text" onclick="event.stopPropagation()" oninput="updateKoLabels('${mid}')">
        </div>
        <div class="score-center">
          <div class="match-date">${m.date}</div>
          <div class="score-inputs">
            <input class="score-input" id="${mid}-sh" type="number" min="0" max="20" placeholder="0" onclick="event.stopPropagation()">
            <span class="score-sep">–</span>
            <input class="score-input" id="${mid}-sa" type="number" min="0" max="20" placeholder="0" onclick="event.stopPropagation()">
          </div>
          <div class="match-meta">${m.label} · ${m.venue}</div>
          <div class="expand-icon" id="icon-${mid}">▼ Details</div>
        </div>
        <div class="team-away">
          <input class="ko-team-input" id="${mid}-away" placeholder="Team B" type="text" onclick="event.stopPropagation()" oninput="updateKoLabels('${mid}')">
        </div>
      </div>

      <div class="match-details" id="det-${mid}">
        <div class="details-grid">
          <div class="detail-section">
            <h4 id="lbl-goals-home-${mid}">⚽ Goals — Team A</h4>
            <div id="goals-home-${mid}">${goalRow(mid,'home',0)}</div>
            <button class="add-event-btn" onclick="addGoal('${mid}','home')">+ Add Goal</button>
          </div>
          <div class="detail-section">
            <h4 id="lbl-goals-away-${mid}">⚽ Goals — Team B</h4>
            <div id="goals-away-${mid}">${goalRow(mid,'away',0)}</div>
            <button class="add-event-btn" onclick="addGoal('${mid}','away')">+ Add Goal</button>
          </div>
          <div class="detail-section">
            <h4 id="lbl-cards-home-${mid}">🟨 Cards & Events — Team A</h4>
            <div id="cards-home-${mid}">${cardRow(mid,'home',0)}</div>
            <button class="add-event-btn" onclick="addCard('${mid}','home')">+ Add Card/Event</button>
          </div>
          <div class="detail-section">
            <h4 id="lbl-cards-away-${mid}">🟨 Cards & Events — Team B</h4>
            <div id="cards-away-${mid}">${cardRow(mid,'away',0)}</div>
            <button class="add-event-btn" onclick="addCard('${mid}','away')">+ Add Card/Event</button>
          </div>
        </div>

        <div class="detail-section" style="margin-top:12px">
          <h4>🎯 Penalty Shootout (if applicable)</h4>
          <div class="penalty-row">
            <span class="penalty-label" id="lbl-pen-home-${mid}">Team A</span>
            <input class="pen-score-input" id="${mid}-ph" type="number" min="0" max="10" placeholder="–">
            <span style="color:var(--muted);font-family:'Barlow Condensed';font-size:13px">vs</span>
            <input class="pen-score-input" id="${mid}-pa" type="number" min="0" max="10" placeholder="–">
            <span class="penalty-label" id="lbl-pen-away-${mid}" style="margin-left:4px">Team B</span>
          </div>
        </div>

        <div class="detail-section" style="margin-top:12px">
          <h4>⏱ Extra Time Score (if applicable)</h4>
          <div class="penalty-row">
            <span class="penalty-label" id="lbl-et-home-${mid}">Team A</span>
            <input class="pen-score-input" id="${mid}-eth" type="number" min="0" max="20" placeholder="–" style="border-color:rgba(201,168,76,0.4);color:var(--gold-light)">
            <span style="color:var(--muted);font-family:'Barlow Condensed';font-size:13px">vs</span>
            <input class="pen-score-input" id="${mid}-eta" type="number" min="0" max="20" placeholder="–" style="border-color:rgba(201,168,76,0.4);color:var(--gold-light)">
            <span class="penalty-label" id="lbl-et-away-${mid}" style="margin-left:4px">Team B</span>
          </div>
        </div>

        <div class="detail-section" style="margin-top:12px">
          <h4>🏆 Match Winner</h4>
          <div class="points-row">
            <div class="pts-box" style="flex:2">
              <label>Winner advances to next round</label>
              <input class="event-input" id="${mid}-winner" placeholder="Winning team name" type="text" style="flex:1.5">
            </div>
          </div>
        </div>

        <div class="detail-section" style="margin-top:12px">
          <h4>📝 Notes</h4>
          <textarea class="notes-input" id="${mid}-notes" placeholder="VAR decisions, key moments, injuries, red cards, controversies…"></textarea>
        </div>
      </div>
    </div>`;
  });

  html += `</div>`;
  container.innerHTML = html;
}

// ============================================================
// SAVE / LOAD
// ============================================================
function populateMatchList() {
  const gid = document.getElementById('po-match-group').value;
  const pick = document.getElementById('po-match-pick');
  pick.innerHTML = '<option value="">— Select Match —</option>';
  if (!gid) return;

  if (gid === 'ko') {
    // All knockout stages
    const koStages = ['r32','r16','qf','sf','final'];
    const koLabels = {'r32':'Round of 32','r16':'Round of 16','qf':'Quarterfinals','sf':'Semifinals','final':'Final & 3rd Place'};
    koStages.forEach(sk => {
      const stage = knockoutStages[sk];
      stage.matches.forEach(m => {
        const opt = document.createElement('option');
        opt.value = 'ko:' + m.id;
        opt.textContent = koLabels[sk] + ' · ' + m.label + ' (' + m.date + ')';
        pick.appendChild(opt);
      });
    });
  } else {
    const group = groups.find(g => g.id === gid);
    if (!group) return;
    group.matches.forEach((m, i) => {
      const opt = document.createElement('option');
      opt.value = 'g:' + gid + ':' + i;
      opt.textContent = m.home + ' vs ' + m.away + ' · ' + m.date;
      pick.appendChild(opt);
    });
  }
}

function printSingleMatch() {
  const pickVal = document.getElementById('po-match-pick').value;
  if (!pickVal) { alert('Please select a match first.'); return; }

  const withDetails = document.getElementById('po-details').checked;
  let targetId = '';

  if (pickVal.startsWith('g:')) {
    const parts = pickVal.split(':');
    targetId = 'g' + parts[1] + '-m' + parts[2];
    // Make groups panel active
    document.querySelectorAll('.panel').forEach(el => { el.dataset.wasActive = el.classList.contains('active'); el.classList.remove('active'); });
    document.getElementById('groups').classList.add('active');
    // Hide all group sections
    document.querySelectorAll('.group-section').forEach(el => el.style.display = 'none');
    // Show only the parent group section
    const gid = parts[1];
    const grpEl = document.getElementById('grp-section-' + gid);
    if (grpEl) grpEl.style.display = 'block';
    // Hide all match cards in that group except the one we want
    if (grpEl) {
      grpEl.querySelectorAll('.match-card').forEach(el => el.style.display = 'none');
    }
    const matchCard = document.getElementById('card-' + targetId);
    if (matchCard) matchCard.style.display = 'block';
  } else {
    // knockout
    const koId = pickVal.split(':')[1];
    targetId = koId;
    document.querySelectorAll('.panel').forEach(el => { el.dataset.wasActive = el.classList.contains('active'); el.classList.remove('active'); });
    // Find which stage this match belongs to and show only that panel
    for (const [sk, stage] of Object.entries(knockoutStages)) {
      const found = stage.matches.find(m => m.id === koId);
      if (found) {
        const panel = document.getElementById(sk);
        if (panel) {
          panel.classList.add('active');
          // Hide all match cards except target
          panel.querySelectorAll('.match-card').forEach(el => el.style.display = 'none');
          const matchCard = document.getElementById('card-' + koId);
          if (matchCard) matchCard.style.display = 'block';
        }
        break;
      }
    }
  }

  // Handle details
  const matchCard = document.getElementById('card-' + targetId);
  if (matchCard) {
    const det = matchCard.querySelector('.match-details');
    if (det) {
      if (withDetails) det.classList.add('open');
      else det.classList.remove('open');
    }
  }

  // Hide standings for single match print
  document.querySelectorAll('details').forEach(el => el.open = false);

  closePrintModal();
  setTimeout(() => {
    window.print();
    setTimeout(restoreAfterPrint, 1000);
  }, 200);
}

function openPrintModal() { document.getElementById('printModal').classList.add('open'); }
function closePrintModal() { document.getElementById('printModal').classList.remove('open'); }

function toggleAllGroups(cb) {
  document.querySelectorAll('.po-group').forEach(c => c.checked = cb.checked);
}
function toggleAllKO(cb) {
  document.querySelectorAll('.po-ko').forEach(c => c.checked = cb.checked);
}

function executePrint() {
  const selectedGroups = [...document.querySelectorAll('.po-group:checked')].map(c => c.value);
  const selectedKO     = [...document.querySelectorAll('.po-ko:checked')].map(c => c.value);
  const withDetails    = document.getElementById('po-details').checked;
  const withStandings  = document.getElementById('po-standings').checked;

  if (selectedGroups.length === 0 && selectedKO.length === 0) {
    alert('Please select at least one section to print.');
    return;
  }

  // Hide everything first
  document.querySelectorAll('.group-section').forEach(el => el.style.display = 'none');
  document.querySelectorAll('.panel').forEach(el => { el.dataset.wasActive = el.classList.contains('active'); el.classList.remove('active'); });

  // Show selected groups
  selectedGroups.forEach(gid => {
    const el = document.getElementById('grp-section-' + gid);
    if (el) el.style.display = 'block';
  });

  // Show group panel if any groups selected
  if (selectedGroups.length > 0) {
    document.getElementById('groups').classList.add('active');
  }

  // Show selected KO panels
  selectedKO.forEach(kid => {
    const el = document.getElementById(kid);
    if (el) el.classList.add('active');
  });

  // Handle details visibility
  if (withDetails) {
    document.querySelectorAll('.match-details').forEach(el => el.classList.add('open'));
  } else {
    document.querySelectorAll('.match-details').forEach(el => el.classList.remove('open'));
  }

  // Handle standings
  document.querySelectorAll('details').forEach(el => { el.open = withStandings; });

  // Close modal and print
  closePrintModal();
  setTimeout(() => {
    window.print();
    // Restore everything after print dialog closes
    setTimeout(restoreAfterPrint, 1000);
  }, 200);
}

function restoreAfterPrint() {
  // Restore all group sections
  document.querySelectorAll('.group-section').forEach(el => el.style.display = '');
  // Restore all match cards
  document.querySelectorAll('.match-card').forEach(el => el.style.display = '');
  // Restore active panels
  document.querySelectorAll('.panel').forEach(el => {
    if (el.dataset.wasActive === 'true') el.classList.add('active');
    else el.classList.remove('active');
    delete el.dataset.wasActive;
  });
  // Collapse details again
  document.querySelectorAll('.match-details').forEach(el => el.classList.remove('open'));
  document.querySelectorAll('.expand-icon').forEach(el => el.textContent = '▼ Details');
  // Reset match picker
  document.getElementById('po-match-group').value = '';
  document.getElementById('po-match-pick').innerHTML = '<option value="">— Select Match —</option>';
}

function downloadFile() {
  // Grab the full current HTML of the page (live state)
  const html = '<!DOCTYPE html>' + document.documentElement.outerHTML;
  const blob = new Blob([html], { type: 'text/html' });
  const url = URL.createObjectURL(blob);
  const a = document.createElement('a');
  a.href = url;
  a.download = 'FIFA-World-Cup-2026-Scoresheet.html';
  document.body.appendChild(a);
  a.click();
  document.body.removeChild(a);
  URL.revokeObjectURL(url);
}

function saveData() {
  const inputs = document.querySelectorAll('input, select, textarea');
  const data = {};
  inputs.forEach(el => { if(el.id) data[el.id] = el.value; });
  try {
    localStorage.setItem('wc2026_scoresheet', JSON.stringify(data));
    const toast = document.getElementById('savedToast');
    toast.style.display = 'flex';
    setTimeout(() => toast.style.display = 'none', 2500);
  } catch(e) {}
}

function loadData() {
  try {
    const raw = localStorage.getItem('wc2026_scoresheet');
    if (!raw) return;
    const data = JSON.parse(raw);
    Object.keys(data).forEach(id => {
      const el = document.getElementById(id);
      if (el) el.value = data[id];
    });
  } catch(e) {}
}

// ============================================================
// TABS
// ============================================================
function showTab(id) {
  document.querySelectorAll('.panel').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  event.target.classList.add('active');
}

// ============================================================
// INIT
// ============================================================
renderGroups();
renderKnockout('r32', 'r32');
renderKnockout('r16', 'r16');
renderKnockout('qf', 'qf');
renderKnockout('sf', 'sf');
renderKnockout('final', 'final');
loadData();
</script>
</body>
</html>
