<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="NCAR Gsoil Heat Flux Sandbox Heatmap — interactive visualization of ground soil heat flux sensors (W/m²) across a 15×24in sandbox. Mar 2026 data.">
<title>Gsoil Sandbox Heatmap — NCAR</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Barlow:wght@300;400;600&display=swap');

  :root {
    --bg: #0a0e14;
    --panel: #111720;
    --border: #2a3d52;
    --accent: #00d4ff;
    --accent2: #ff6b35;
    --text: #deeaf6;
    --muted: #7a9ab8;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Barlow', sans-serif;
    font-weight: 300;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 20px;
  }

  h1 {
    font-family: 'Share Tech Mono', monospace;
    font-size: 1.1rem;
    color: var(--accent);
    letter-spacing: 0.15em;
    text-transform: uppercase;
    margin-bottom: 2px;
  }

  /* ── Site Header ── */
  .site-header {
    width: 100%;
    max-width: 1000px;
    display: flex;
    align-items: center;
    gap: 24px;
    padding: 14px 0 18px 0;
    border-bottom: 1px solid var(--border);
    margin-bottom: 22px;
    flex-wrap: wrap;
  }

  .header-logos {
    display: flex;
    align-items: center;
    gap: 16px;
    flex-shrink: 0;
  }

  .logo-isfs {
    height: 52px;
    width: auto;
    /* Invert black logo to white for dark background */
    filter: invert(1) brightness(1.8);
    opacity: 0.85;
  }

  .logo-ncar {
    height: 44px;
    width: auto;
    /* Keep full color but slightly brighten on dark bg */
    filter: brightness(1.1);
  }

  .header-divider {
    width: 1px;
    height: 44px;
    background: var(--border);
  }

  .header-text {
    display: flex;
    flex-direction: column;
    gap: 2px;
  }

  .subtitle {
    font-size: 0.75rem;
    color: var(--muted);
    letter-spacing: 0.1em;
    margin-bottom: 20px;
  }

  .main-layout {
    display: flex;
    gap: 20px;
    align-items: stretch;
    width: 100%;
    max-width: 1000px;
  }

  .left-panel {
    display: flex;
    flex-direction: column;
    gap: 12px;
    flex: 0 0 auto;
  }

  .sandbox-wrap {
    background: var(--panel);
    border: 1px solid var(--border);
    padding: 10px;
    position: relative;
  }

  canvas#heatmap, canvas#heatmap2 {
    display: block;
  }

  canvas#overlay, canvas#overlay2 {
    position: absolute;
    top: 10px;
    left: 10px;
    pointer-events: none;
  }

  .controls {
    background: var(--panel);
    border: 1px solid var(--border);
    padding: 12px 16px;
  }

  .ctrl-row {
    display: flex;
    gap: 8px;
    align-items: center;
    margin-bottom: 8px;
    flex-wrap: wrap;
  }

  .ctrl-row:last-child { margin-bottom: 0; }

  .btn {
    background: transparent;
    border: 1px solid var(--border);
    color: var(--text);
    padding: 5px 12px;
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.7rem;
    cursor: pointer;
    letter-spacing: 0.05em;
    transition: all 0.15s;
  }

  .btn:hover, .btn.active {
    border-color: var(--accent);
    color: var(--accent);
    background: rgba(0, 212, 255, 0.06);
  }

  .btn.spike.active {
    border-color: var(--accent2);
    color: var(--accent2);
    background: rgba(255, 107, 53, 0.06);
  }

  label {
    font-size: 0.72rem;
    color: var(--muted);
    letter-spacing: 0.08em;
    text-transform: uppercase;
  }

  input[type=range] {
    -webkit-appearance: none;
    width: 200px;
    height: 2px;
    background: var(--border);
    outline: none;
    cursor: pointer;
  }
  input[type=range]::-webkit-slider-thumb {
    -webkit-appearance: none;
    width: 12px; height: 12px;
    background: var(--accent);
    border-radius: 50%;
  }

  #time-display {
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.68rem;
    color: var(--accent);
    min-width: 140px;
  }

  .right-panel {
    flex: 1;
    display: flex;
    flex-direction: column;
    gap: 12px;
  }

  .sensor-table {
    background: var(--panel);
    border: 1px solid var(--border);
    padding: 12px;
    overflow-y: auto;
    flex: 1;
    min-height: 0;
  }

  .sensor-table h3 {
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.7rem;
    color: var(--muted);
    letter-spacing: 0.1em;
    text-transform: uppercase;
    margin-bottom: 10px;
  }

  table {
    width: 100%;
    border-collapse: collapse;
    font-size: 0.72rem;
  }

  th {
    text-align: left;
    color: var(--muted);
    font-weight: 400;
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.65rem;
    letter-spacing: 0.08em;
    padding: 3px 8px;
    border-bottom: 1px solid var(--border);
  }

  td {
    padding: 3px 8px;
    border-bottom: 1px solid rgba(30,45,61,0.5);
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.68rem;
  }

  .sensor-name { color: var(--accent); }
  .val-cell { text-align: right; }

  .bar-cell {
    width: 80px;
  }

  .bar-bg {
    background: var(--border);
    height: 6px;
    border-radius: 2px;
    overflow: hidden;
  }

  .bar-fill {
    height: 100%;
    border-radius: 2px;
    transition: width 0.3s;
  }

  .legend {
    background: var(--panel);
    border: 1px solid var(--border);
    padding: 10px 14px;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .legend label {
    font-size: 0.65rem;
  }

  #legend-canvas { border-radius: 2px; }

  .tooltip {
    position: fixed;
    background: rgba(10,14,20,0.95);
    border: 1px solid var(--accent);
    padding: 6px 10px;
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.68rem;
    color: var(--text);
    pointer-events: none;
    display: none;
    z-index: 100;
    white-space: nowrap;
  }

  .mote-group {
    display: flex;
    gap: 6px;
    flex-wrap: wrap;
  }

  .mote-btn {
    background: transparent;
    border: 1px solid var(--border);
    color: var(--muted);
    padding: 3px 8px;
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.65rem;
    cursor: pointer;
    transition: all 0.15s;
    border-radius: 2px;
  }
  .mote-btn:hover { border-color: var(--accent); color: var(--accent); }
  .mote-btn.active { border-color: var(--accent); color: var(--accent); background: rgba(0,212,255,0.08); }

  /* ── Tabs ── */
  .tab-nav {
    display: flex;
    gap: 0;
    width: 100%;
    max-width: 1000px;
    border-bottom: 1px solid var(--border);
    margin-bottom: 20px;
  }
  .tab-btn {
    background: transparent;
    border: 1px solid var(--border);
    border-bottom: none;
    color: var(--muted);
    padding: 8px 22px;
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.72rem;
    letter-spacing: 0.1em;
    cursor: pointer;
    transition: all 0.15s;
    margin-bottom: -1px;
  }
  .tab-btn:hover { color: var(--accent); border-color: var(--accent); }
  .tab-btn.active { color: var(--accent); border-color: var(--accent); background: rgba(0,212,255,0.06); border-bottom: 1px solid var(--bg); }
  .tab-panel { display: none; width: 100%; }
  .tab-panel.active { display: flex; flex-direction: column; align-items: center; }
  .charts-section {
    width: 100%;
    max-width: 1000px;
    margin-top: 24px;
    display: flex;
    flex-direction: column;
    gap: 20px;
  }

  .chart-block {
    background: var(--panel);
    border: 1px solid var(--border);
    padding: 14px 16px;
  }

  .chart-header {
    display: flex;
    align-items: baseline;
    gap: 12px;
    margin-bottom: 10px;
    flex-wrap: wrap;
  }

  .chart-title {
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.68rem;
    color: var(--accent);
    letter-spacing: 0.1em;
    text-transform: uppercase;
  }

  .chart-sub {
    font-size: 0.65rem;
    color: var(--muted);
    letter-spacing: 0.05em;
  }

  .chart-wrap {
    position: relative;
  }

  .chart-tip {
    position: absolute;
    background: rgba(10,14,20,0.95);
    border: 1px solid var(--accent);
    padding: 5px 9px;
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.65rem;
    color: var(--text);
    pointer-events: none;
    display: none;
    white-space: nowrap;
    z-index: 50;
  }

  .chart-filter-row {
    display: flex;
    align-items: center;
    gap: 6px;
    margin-bottom: 8px;
    flex-wrap: wrap;
  }

  .chart-filter-label {
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.62rem;
    color: var(--muted);
    letter-spacing: 0.08em;
  }

  .chart-fbtn {
    background: transparent;
    border: 1px solid var(--border);
    color: var(--muted);
    padding: 3px 8px;
    font-family: 'Share Tech Mono', monospace;
    font-size: 0.62rem;
    cursor: pointer;
    letter-spacing: 0.05em;
    transition: all 0.15s;
  }

  .chart-fbtn:hover { border-color: var(--accent); color: var(--accent); }
  .chart-fbtn.active { border-color: var(--accent); color: var(--accent); background: rgba(0,212,255,0.08); }
</style>
</head>
<body>

<header class="site-header">
  <div class="header-logos">
    <img src="ISFS_logo.png" alt="ISFS" class="logo-isfs" />
    <div class="header-divider"></div>
    <img src="NCAR_logo.png" alt="NSF NCAR" class="logo-ncar" />
  </div>
  <div class="header-text">
    <h1>Gsoil Sandbox Heatmap</h1>
    <p class="subtitle">NCAR · Earth Observing Laboratory · Ground Soil Heat Flux · W/m² · 15×24 in sandbox</p>
  </div>
</header>

<!-- Tab Navigation -->
<div class="tab-nav">
  <button class="tab-btn active" onclick="switchTab(1,this)">CALIBRATION RUN 1 — 28 SENSORS · MAR 6</button>
  <button class="tab-btn" onclick="switchTab(2,this)">CALIBRATION RUN 2 — 16 SENSORS · MAR 12</button>
</div>

<!-- TAB 1 -->
<div class="tab-panel active" id="tab-1">

<div class="main-layout">
  <div class="left-panel">
    <div class="sandbox-wrap" id="sandbox-wrap">
      <canvas id="heatmap"></canvas>
      <canvas id="overlay"></canvas>
    </div>
    <div class="legend">
      <label>LOW</label>
      <canvas id="legend-canvas" width="140" height="10"></canvas>
      <label>HIGH</label>
      <span id="legend-range" style="font-family:'Share Tech Mono',monospace;font-size:0.6rem;color:var(--muted);margin-left:6px;"></span>
    </div>
    <div class="controls">
      <div class="ctrl-row">
        <label>VIEW:</label>
        <button class="btn active" id="btn-spike" onclick="setMode('spike')">MAR 6 PEAK</button>
        <button class="btn" id="btn-baseline" onclick="setMode('baseline')">BASELINE</button>
        <button class="btn" id="btn-timeline" onclick="setMode('timeline')">TIMELINE</button>
      </div>
      <div class="ctrl-row" id="timeline-ctrl" style="display:none;">
        <label>MAR 6:</label>
        <input type="range" id="time-slider" min="0" max="41" value="0" oninput="onSlider(this.value)">
        <span id="time-display">16:00:00</span>
      </div>
      <div class="ctrl-row">
        <label>MOTE:</label>
        <div class="mote-group">
          <button class="mote-btn active" onclick="toggleMote('all',this)">ALL</button>
          <button class="mote-btn" onclick="toggleMote(2,this)">M2</button>
          <button class="mote-btn" onclick="toggleMote(3,this)">M3</button>
          <button class="mote-btn" onclick="toggleMote(4,this)">M4</button>
          <button class="mote-btn" onclick="toggleMote(5,this)">M5</button>
          <button class="mote-btn" onclick="toggleMote(6,this)">M6</button>
          <button class="mote-btn" onclick="toggleMote(7,this)">M7</button>
        </div>
      </div>
    </div>
  </div>
  <div class="right-panel">
    <div class="sensor-table">
      <h3 id="table-title">Mar 6 Peak Values (W/m²)</h3>
      <table id="sensor-table">
        <thead><tr><th>SENSOR</th><th>MOTE</th><th style="text-align:right">VALUE</th><th>MAGNITUDE</th></tr></thead>
        <tbody id="table-body"></tbody>
      </table>
    </div>
  </div>
</div>

<div class="charts-section">
  <div class="chart-block">
    <div class="chart-header">
      <span class="chart-title">TIME SERIES — ALL SENSORS · Mar 6 16:00–23:00</span>
      <span class="chart-sub">W/m² · 10-min avg</span>
    </div>
    <div class="chart-filter-row">
      <span class="chart-filter-label">FILTER:</span>
      <button class="chart-fbtn active" onclick="setTsFilter('all',this)">ALL</button>
      <button class="chart-fbtn" onclick="setTsFilter('2',this)">M2</button>
      <button class="chart-fbtn" onclick="setTsFilter('3',this)">M3</button>
      <button class="chart-fbtn" onclick="setTsFilter('4',this)">M4</button>
      <button class="chart-fbtn" onclick="setTsFilter('5',this)">M5</button>
      <button class="chart-fbtn" onclick="setTsFilter('6',this)">M6</button>
      <button class="chart-fbtn" onclick="setTsFilter('7',this)">M7</button>
    </div>
    <div class="chart-wrap"><canvas id="chart-ts"></canvas></div>
  </div>
  <div class="chart-block">
    <div class="chart-header">
      <span class="chart-title">MOTE COMPARISON — Average W/m² per Mote Over Time</span>
      <span class="chart-sub">Each line = mean of all sensors on that mote</span>
    </div>
    <div class="chart-wrap"><canvas id="chart-mote"></canvas></div>
  </div>
  <div class="chart-block">
    <div class="chart-header">
      <span class="chart-title">COOL-DOWN CURVE — Decay from Peak</span>
      <span class="chart-sub">Values normalised to each sensor's peak (1.0) · shows relative cool-down rate</span>
    </div>
    <div class="chart-wrap"><canvas id="chart-cool"></canvas></div>
  </div>
</div>

</div><!-- end tab-1 -->

<!-- TAB 2 -->
<div class="tab-panel" id="tab-2">

<div class="main-layout">
  <div class="left-panel">
    <div class="sandbox-wrap" id="sandbox-wrap-2">
      <canvas id="heatmap2"></canvas>
      <canvas id="overlay2"></canvas>
    </div>
    <div class="legend">
      <label>LOW</label>
      <canvas id="legend-canvas-2" width="140" height="10"></canvas>
      <label>HIGH</label>
      <span id="legend-range-2" style="font-family:'Share Tech Mono',monospace;font-size:0.6rem;color:var(--muted);margin-left:6px;"></span>
    </div>
    <div class="controls">
      <div class="ctrl-row">
        <label>VIEW:</label>
        <button class="btn active" id="btn2-spike" onclick="setMode2('spike')">MAR 12 PEAK</button>
        <button class="btn" id="btn2-baseline" onclick="setMode2('baseline')">BASELINE</button>
        <button class="btn" id="btn2-timeline" onclick="setMode2('timeline')">TIMELINE</button>
      </div>
      <div class="ctrl-row" id="timeline-ctrl-2" style="display:none;">
        <label>UTC:</label>
        <input type="range" id="time-slider-2" min="0" max="62" value="0" oninput="onSlider2(this.value)">
        <span id="time-display-2">00:00</span>
      </div>
      <div class="ctrl-row">
        <label>MOTE:</label>
        <div class="mote-group">
          <button class="mote-btn active" onclick="toggleMote2('all',this)">ALL</button>
          <button class="mote-btn" onclick="toggleMote2(2,this)">M2</button>
          <button class="mote-btn" onclick="toggleMote2(3,this)">M3</button>
          <button class="mote-btn" onclick="toggleMote2(6,this)">M6</button>
          <button class="mote-btn" onclick="toggleMote2(7,this)">M7</button>
        </div>
      </div>
    </div>
  </div>
  <div class="right-panel">
    <div class="sensor-table">
      <h3 id="table-title-2">Mar 12 Peak Values (W/m²)</h3>
      <table>
        <thead><tr><th>SENSOR</th><th>MOTE</th><th style="text-align:right">VALUE</th><th>MAGNITUDE</th></tr></thead>
        <tbody id="table-body-2"></tbody>
      </table>
    </div>
  </div>
</div>

<div class="charts-section">
  <div class="chart-block">
    <div class="chart-header">
      <span class="chart-title">TIME SERIES — 16 SENSORS · Mar 12 16:30 – Mar 13 03:00 UTC</span>
      <span class="chart-sub">W/m² · 10-min avg</span>
    </div>
    <div class="chart-filter-row">
      <span class="chart-filter-label">FILTER:</span>
      <button class="chart-fbtn active" onclick="setTsFilter2('all',this)">ALL</button>
      <button class="chart-fbtn" onclick="setTsFilter2('2',this)">M2</button>
      <button class="chart-fbtn" onclick="setTsFilter2('3',this)">M3</button>
      <button class="chart-fbtn" onclick="setTsFilter2('6',this)">M6</button>
      <button class="chart-fbtn" onclick="setTsFilter2('7',this)">M7</button>
    </div>
    <div class="chart-wrap"><canvas id="chart-ts-2"></canvas></div>
  </div>
  <div class="chart-block">
    <div class="chart-header">
      <span class="chart-title">MOTE COMPARISON — Average W/m² per Mote Over Time</span>
      <span class="chart-sub">Each line = mean of all sensors on that mote</span>
    </div>
    <div class="chart-wrap"><canvas id="chart-mote-2"></canvas></div>
  </div>
  <div class="chart-block">
    <div class="chart-header">
      <span class="chart-title">COOL-DOWN CURVE — Decay from Peak</span>
      <span class="chart-sub">Values normalised to each sensor's peak (1.0)</span>
    </div>
    <div class="chart-wrap"><canvas id="chart-cool-2"></canvas></div>
  </div>
</div>

</div><!-- end tab-2 -->

<script>
const COORDS = {"a_2":[5,-10],"b_2":[3,-9],"c_2":[3,-5.5],"d_2":[5.5,-4],"e_2":[7.5,-5],"a_3":[4.5,-17],"b_3":[5,-14],"c_3":[3.5,-20.5],"d_3":[3.5,-15.5],"e_3":[4.5,-13],"a_4":[7.5,-13.5],"b_4":[5,-20],"c_4":[5.5,-18.5],"d_4":[7,-17],"e_4":[7.5,-11.5],"a_5":[12.5,-16],"b_5":[11,-20],"c_5":[9.5,-17.7],"d_5":[10,-13],"e_5":[13.5,-18.5],"a_6":[12.5,-10.5],"b_6":[6,-5.5],"c_6":[12,-6.5],"d_6":[10.5,-8.5],"e_6":[8,-3.5],"a_7":[12,-14],"b_7":[10,-5],"c_7":[8,-8]};
const SPIKE_MAX = {"a_2":77.258,"b_2":80.388,"c_2":69.219,"d_2":54.851,"e_2":81.259,"a_3":55.178,"b_3":83.888,"c_3":13.354,"d_3":75.169,"e_3":96.519,"a_4":85.381,"b_4":26.986,"c_4":26.291,"d_4":54.521,"e_4":92.35,"a_5":55.408,"b_5":40.711,"c_5":63.701,"d_5":72.439,"e_5":37.274,"a_6":68.605,"b_6":78.381,"c_6":56.047,"d_6":78.597,"e_6":48.769,"a_7":60.735,"b_7":50.76,"c_7":61.361};
const BASELINE = {"a_2":0.594,"b_2":0.782,"c_2":0.57,"d_2":0.82,"e_2":0.896,"a_3":0.653,"b_3":0.868,"c_3":0.502,"d_3":0.847,"e_3":0.877,"a_4":0.854,"b_4":0.874,"c_4":0.797,"d_4":0.77,"e_4":0.653,"a_5":0.745,"b_5":1.0,"c_5":0.887,"d_5":0.784,"e_5":0.576,"a_6":0.822,"b_6":0.854,"c_6":0.751,"d_6":0.889,"e_6":0.773,"a_7":0.724,"b_7":0.713,"c_7":0.641};

// Timeseries: 03-06 16:00 to 23:00, 10-min increments (42 steps)
const TS_TIMES = ["2026-03-06 16:00:00","2026-03-06 16:10:00","2026-03-06 16:20:00","2026-03-06 16:30:00","2026-03-06 16:40:00","2026-03-06 16:50:00","2026-03-06 17:00:00","2026-03-06 17:10:00","2026-03-06 17:20:00","2026-03-06 17:30:00","2026-03-06 17:40:00","2026-03-06 17:50:00","2026-03-06 18:00:00","2026-03-06 18:10:00","2026-03-06 18:20:00","2026-03-06 18:30:00","2026-03-06 18:40:00","2026-03-06 18:50:00","2026-03-06 19:00:00","2026-03-06 19:10:00","2026-03-06 19:20:00","2026-03-06 19:30:00","2026-03-06 19:40:00","2026-03-06 19:50:00","2026-03-06 20:00:00","2026-03-06 20:10:00","2026-03-06 20:20:00","2026-03-06 20:30:00","2026-03-06 20:40:00","2026-03-06 20:50:00","2026-03-06 21:00:00","2026-03-06 21:10:00","2026-03-06 21:20:00","2026-03-06 21:30:00","2026-03-06 21:40:00","2026-03-06 21:50:00","2026-03-06 22:00:00","2026-03-06 22:10:00","2026-03-06 22:20:00","2026-03-06 22:30:00","2026-03-06 22:40:00","2026-03-06 22:50:00"];
const TS_VALS = {"a_2":[0.934,0.949,0.961,0.967,0.972,0.984,2.673,12.307,26.28,39.33,50.411,58.679,64.82,69.124,72.096,74.136,75.483,76.347,76.868,77.133,77.234,77.243,77.114,76.865,71.615,57.44,42.385,29.846,20.153,12.919,7.568,3.645,0.805,-1.242,-2.745,-3.825,-4.568,-5.032,-5.268,-5.347,-5.319,-5.251],"b_2":[1.217,1.239,1.259,1.27,1.277,1.289,2.369,10.496,24.145,37.694,49.406,58.122,64.428,68.999,72.336,74.791,76.547,77.811,78.711,79.342,79.778,80.094,80.269,80.347,76.986,64.878,50.299,37.436,27.147,19.294,13.375,8.946,5.67,3.247,1.414,0.042,-0.96,-1.655,-2.089,-2.34,-2.459,-2.524],"c_2":[0.832,0.857,0.877,0.885,0.892,0.903,2.531,11.873,24.906,36.665,46.957,53.806,58.769,62.246,64.697,66.377,67.453,68.214,68.671,68.967,69.114,69.192,69.172,68.954,65.035,53.225,40.327,29.532,21.225,15.09,10.563,7.22,4.77,2.953,1.556,0.509,-0.265,-0.792,-1.12,-1.322,-1.43,-1.515],"d_2":[1.272,1.301,1.321,1.332,1.335,1.341,1.946,6.175,13.568,21.417,28.48,35.404,41.285,45.658,48.788,50.976,52.434,53.466,54.144,54.534,54.732,54.817,54.84,54.764,53.154,47.114,38.929,31.001,24.176,18.642,14.279,10.891,8.297,6.276,4.655,3.382,2.402,1.683,1.168,0.788,0.526,0.313],"e_2":[1.378,1.4,1.421,1.436,1.44,1.448,2.175,8.728,21.276,34.785,46.869,56.816,64.57,70.172,74.115,76.862,78.673,79.861,80.597,81.006,81.197,81.254,81.201,81.06,78.564,68.458,54.745,41.758,30.927,22.426,15.885,10.897,7.165,4.384,2.261,0.67,-0.496,-1.324,-1.871,-2.217,-2.411,-2.515],"a_3":[0.943,0.954,0.963,0.965,0.968,0.974,1.358,5.033,12.407,20.644,28.029,33.872,38.394,41.983,44.834,47.121,48.97,50.428,51.582,52.525,53.321,54.013,54.567,55.049,54.102,48.443,40.176,32.068,25.15,19.545,15.098,11.637,8.978,6.923,5.309,4.037,3.05,2.295,1.738,1.333,1.036,0.795],"b_3":[1.354,1.363,1.37,1.372,1.372,1.378,2.043,7.992,19.611,32.46,43.96,53.772,61.618,67.55,71.965,75.269,77.749,79.568,80.897,81.855,82.566,83.123,83.506,83.818,81.298,70.697,56.589,43.318,32.244,23.442,16.586,11.335,7.379,4.408,2.149,0.443,-0.818,-1.723,-2.328,-2.707,-2.93,-3.072],"c_3":[0.842,0.858,0.876,0.881,0.89,0.9,1.041,1.945,3.57,5.422,7.191,8.767,9.993,10.935,11.663,12.198,12.563,12.759,12.848,12.938,13.051,13.17,13.181,13.218,12.727,11.244,9.211,7.124,5.287,3.718,2.437,1.465,0.729,0.137,-0.349,-0.738,-1.028,-1.223,-1.317,-1.352,-1.353,-1.364],"d_3":[1.201,1.216,1.228,1.232,1.236,1.244,1.767,6.857,17.056,28.311,38.323,46.4,52.627,57.463,61.253,64.278,66.717,68.644,70.188,71.457,72.536,73.476,74.248,74.969,73.532,65.234,53.608,42.547,33.278,25.862,20.032,15.525,12.083,9.435,7.357,5.723,4.453,3.482,2.769,2.249,1.866,1.553],"e_3":[1.331,1.345,1.358,1.363,1.368,1.38,2.644,11.861,27.328,42.825,56.132,66.863,75.046,81.034,85.383,88.578,90.918,92.598,93.815,94.694,95.351,95.862,96.18,96.427,91.712,76.178,58.296,42.845,30.627,21.314,14.298,9.076,5.232,2.401,0.282,-1.292,-2.425,-3.201,-3.677,-3.937,-4.049,-4.098],"a_4":[1.369,1.377,1.384,1.385,1.386,1.393,2.542,10.626,24.018,37.578,49.188,58.625,66.086,71.782,75.994,79.076,81.301,82.849,83.885,84.548,84.961,85.235,85.34,85.286,81.703,69.505,54.622,41.154,30.106,21.4,14.65,9.492,5.61,2.709,0.517,-1.122,-2.316,-3.155,-3.696,-4.01,-4.172,-4.266],"b_4":[1.32,1.334,1.347,1.353,1.358,1.365,1.436,2.251,4.343,7.224,10.286,13.218,15.759,17.879,19.639,21.096,22.301,23.261,24.031,24.688,25.273,25.818,26.261,26.758,26.764,25.623,23.189,20.195,17.246,14.588,12.274,10.345,8.78,7.496,6.407,5.491,4.74,4.137,3.67,3.312,3.025,2.761],"c_4":[1.235,1.243,1.249,1.252,1.251,1.256,1.323,2.081,4.061,6.807,9.729,12.539,15.074,17.221,19.004,20.482,21.716,22.716,23.54,24.21,24.779,25.3,25.729,26.117,26.199,25.238,23.011,20.201,17.389,14.814,12.553,10.653,9.09,7.798,6.705,5.788,5.032,4.424,3.948,3.569,3.255,2.974],"d_4":[1.193,1.201,1.207,1.207,1.205,1.207,1.476,4.466,11.093,18.977,26.372,32.619,37.677,41.695,44.835,47.284,49.198,50.655,51.754,52.577,53.198,53.707,54.098,54.441,53.688,48.835,41.139,33.196,26.172,20.332,15.605,11.862,8.952,6.696,4.927,3.545,2.478,1.669,1.077,0.654,0.353,0.119],"e_4":[1.098,1.112,1.124,1.126,1.133,1.151,4.539,19.165,36.915,52.02,63.872,73.068,79.9,84.681,87.918,90.049,91.349,92.055,92.327,92.27,92.034,91.7,91.193,90.441,82.272,63.931,46.12,31.779,20.793,12.573,6.465,1.964,-1.317,-3.684,-5.411,-6.638,-7.46,-7.947,-8.165,-8.194,-8.106,-7.984],"a_5":[1.159,1.171,1.18,1.181,1.184,1.192,1.72,6.331,14.903,23.919,31.797,37.878,42.459,45.973,48.622,50.623,52.149,53.23,53.961,54.455,54.793,55.059,55.229,55.377,54.199,48.252,39.637,31.28,24.202,18.502,14.013,10.54,7.882,5.852,4.289,3.074,2.139,1.438,0.938,0.595,0.357,0.164],"b_5":[1.474,1.49,1.499,1.5,1.505,1.515,1.754,3.978,8.58,13.898,19.014,23.568,27.232,30.12,32.408,34.262,35.784,36.951,37.879,38.596,39.188,39.706,40.123,40.575,40.363,37.673,33.024,28.063,23.559,19.66,16.404,13.758,11.622,9.892,8.468,7.276,6.294,5.519,4.925,4.462,4.08,3.712],"c_5":[1.339,1.349,1.356,1.358,1.358,1.362,1.642,4.954,12.636,21.962,30.778,38.321,44.423,49.186,52.837,55.644,57.818,59.455,60.669,61.574,62.256,62.811,63.24,63.595,62.944,57.904,49.329,40.188,31.995,25.151,19.6,15.194,11.757,9.086,6.99,5.343,4.059,3.071,2.334,1.792,1.394,1.075],"d_5":[1.217,1.226,1.234,1.24,1.242,1.248,1.937,7.717,18.511,30.185,40.55,49.332,56.356,61.549,65.262,67.893,69.722,70.936,71.696,72.126,72.337,72.428,72.403,72.308,70.306,62.008,50.412,39.147,29.542,21.807,15.716,10.993,7.393,4.681,2.621,1.065,-0.092,-0.936,-1.517,-1.887,-2.115,-2.28],"e_5":[0.857,0.869,0.877,0.88,0.885,0.894,1.345,4.772,10.572,16.384,21.454,25.429,28.476,30.801,32.559,33.912,34.987,35.714,36.186,36.506,36.755,36.969,37.107,37.239,36.337,32.102,26.339,20.939,16.416,12.745,9.833,7.582,5.839,4.49,3.44,2.599,1.929,1.422,1.07,0.83,0.66,0.5],"a_6":[1.186,1.2,1.211,1.215,1.217,1.223,2.28,9.514,20.853,31.883,41.228,48.698,54.467,58.7,61.767,63.994,65.575,66.671,67.416,67.885,68.194,68.417,68.54,68.579,66.554,58.404,47.753,37.868,29.66,23.149,18.097,14.139,11.086,8.746,6.925,5.497,4.385,3.538,2.915,2.467,2.132,1.834],"b_6":[1.313,1.34,1.364,1.379,1.385,1.394,2.33,9.174,20.82,32.883,43.223,52.881,61.005,66.937,71.095,73.961,75.824,77.049,77.798,78.192,78.351,78.37,78.276,78.026,75.462,65.869,53.192,41.188,31.087,23.065,16.858,12.022,8.351,5.574,3.418,1.775,0.547,-0.343,-0.952,-1.366,-1.634,-1.809],"c_6":[1.052,1.068,1.08,1.086,1.088,1.093,1.961,7.84,17.108,26.177,33.757,39.676,44.258,47.688,50.214,52.064,53.357,54.291,54.955,55.379,55.671,55.877,56.003,56.023,54.558,48.439,40.155,32.292,25.692,20.456,16.4,13.217,10.765,8.879,7.388,6.207,5.273,4.545,3.991,3.567,3.229,2.937],"d_6":[1.326,1.343,1.359,1.37,1.374,1.384,2.412,9.673,21.801,34.324,45.222,54.601,62.159,67.741,71.702,74.456,76.282,77.448,78.143,78.471,78.583,78.576,78.457,78.223,75.919,67.098,55.054,43.374,33.374,25.307,18.984,14.0,10.171,7.266,5.033,3.327,2.041,1.088,0.411,-0.052,-0.369,-0.608],"e_6":[1.193,1.215,1.231,1.239,1.242,1.247,1.8,5.596,12.079,19.009,25.34,31.358,36.494,40.39,43.241,45.267,46.634,47.575,48.184,48.531,48.71,48.761,48.704,48.579,47.185,42.165,35.303,28.536,22.594,17.678,13.755,10.629,8.206,6.3,4.753,3.525,2.568,1.856,1.337,0.949,0.665,0.439],"a_7":[1.051,1.062,1.071,1.075,1.078,1.084,1.801,7.531,17.421,27.372,35.885,42.426,47.295,50.967,53.709,55.76,57.29,58.382,59.141,59.655,60.013,60.293,60.475,60.678,59.097,51.985,42.319,33.243,25.702,19.646,14.904,11.24,8.438,6.312,4.667,3.386,2.405,1.667,1.136,0.77,0.508,0.29],"b_7":[1.009,1.024,1.038,1.048,1.05,1.055,1.464,4.99,11.656,18.929,25.576,31.525,36.608,40.53,43.44,45.584,47.121,48.252,49.078,49.655,50.068,50.375,50.596,50.732,49.912,45.505,38.777,31.903,25.848,20.815,16.767,13.551,11.034,9.076,7.504,6.247,5.251,4.465,3.858,3.383,3.003,2.697],"c_7":[0.995,1.01,1.024,1.033,1.036,1.044,1.995,8.238,18.138,27.883,36.31,43.379,49.048,53.253,56.249,58.331,59.687,60.564,61.074,61.303,61.355,61.301,61.148,60.901,58.561,50.57,40.512,31.172,23.376,17.137,12.262,8.486,5.617,3.461,1.8,0.544,-0.382,-1.046,-1.491,-1.779,-1.957,-2.068]};
</script>

<!-- ── TAB 2 DATA ── -->
<script>
// Tab 2: 16 sensors, Mar 12 00:00-03:00 UTC
const COORDS2 = {"112":[4,-7],"142":[6,-7],"118":[9,-7],"153":[11,-7],"119":[4,-9],"115":[6,-9],"114":[9,-9],"120":[11,-9],"151":[4,-12],"123":[6,-12],"122":[9,-12],"154":[11,-12],"117":[4,-14],"152":[6,-14],"121":[9,-14],"150":[11,-14]};
const SPIKE_MAX2 = {"112":17.413,"114":34.59,"115":27.922,"117":20.132,"118":26.529,"119":21.891,"120":33.875,"121":31.304,"122":37.441,"123":37.888,"142":25.751,"150":33.439,"151":24.269,"152":29.806,"153":25.553,"154":38.081};
const BASELINE2 = {"112":1.297,"114":1.459,"115":1.369,"117":1.242,"118":1.445,"119":1.27,"120":1.458,"121":1.297,"122":1.395,"123":1.525,"142":1.522,"150":1.459,"151":1.251,"152":1.366,"153":1.52,"154":1.39};
const TS_TIMES2 = ["03/12 16:30","03/12 16:40","03/12 16:50","03/12 17:00","03/12 17:10","03/12 17:20","03/12 17:30","03/12 17:40","03/12 17:50","03/12 18:00","03/12 18:10","03/12 18:20","03/12 18:30","03/12 18:40","03/12 18:50","03/12 19:00","03/12 19:10","03/12 19:20","03/12 19:30","03/12 19:40","03/12 19:50","03/12 20:00","03/12 20:10","03/12 20:20","03/12 20:30","03/12 20:40","03/12 20:50","03/12 21:00","03/12 21:10","03/12 21:20","03/12 21:30","03/12 21:40","03/12 21:50","03/12 22:00","03/12 22:10","03/12 22:20","03/12 22:30","03/12 22:40","03/12 22:50","03/12 23:00","03/12 23:10","03/12 23:20","03/12 23:30","03/12 23:40","03/12 23:50","03/13 00:00","03/13 00:10","03/13 00:20","03/13 00:30","03/13 00:40","03/13 00:50","03/13 01:00","03/13 01:10","03/13 01:20","03/13 01:30","03/13 01:40","03/13 01:50","03/13 02:00","03/13 02:10","03/13 02:20","03/13 02:30","03/13 02:40","03/13 02:50"];
const TS_VALS2 = {"112":[1.133,1.352,3.144,6.135,8.997,11.379,13.129,14.282,15.141,15.876,16.479,16.932,17.224,17.367,17.41,17.395,17.368,17.322,17.255,17.241,17.235,17.172,17.082,17.029,16.982,16.939,16.892,16.838,16.728,16.47,16.292,16.171,16.087,16.005,15.894,15.762,15.669,15.951,14.777,11.992,8.964,6.271,4.025,2.253,0.877,-0.167,-0.948,-1.49,-1.866,-2.132,-2.314,-2.437,-2.511,-2.541,-2.535,-2.519,-2.499,-2.456,-2.388,-2.316,-2.248,-2.186,-2.127],"114":[1.162,2.236,8.277,15.732,21.722,26.108,29.109,31.044,32.352,33.29,33.903,34.282,34.532,34.569,34.485,34.352,34.289,34.223,34.164,34.14,34.102,34.021,33.916,33.833,33.737,33.619,33.533,33.408,33.215,32.934,32.421,31.91,31.495,31.136,30.832,30.528,30.274,29.811,25.803,18.854,12.617,7.77,4.153,1.509,-0.429,-1.812,-2.774,-3.435,-3.904,-4.222,-4.422,-4.537,-4.571,-4.534,-4.455,-4.347,-4.219,-4.074,-3.917,-3.746,-3.574,-3.409,-3.243],"115":[1.099,1.75,5.999,11.703,16.433,20.094,22.644,24.283,25.46,26.401,27.099,27.567,27.829,27.916,27.885,27.803,27.782,27.747,27.684,27.652,27.589,27.498,27.417,27.343,27.26,27.157,27.06,26.939,26.741,26.452,26.201,26.034,25.946,25.858,25.697,25.548,25.478,25.378,22.66,17.325,12.237,8.097,4.898,2.496,0.693,-0.623,-1.582,-2.255,-2.734,-3.07,-3.292,-3.429,-3.494,-3.508,-3.486,-3.435,-3.371,-3.286,-3.175,-3.052,-2.934,-2.827,-2.716],"117":[1.129,1.435,3.967,7.783,11.198,13.906,15.911,17.261,18.187,18.885,19.408,19.771,19.972,20.041,20.027,19.994,19.986,20.047,20.105,20.115,20.094,20.059,20.02,19.962,19.89,19.818,19.754,19.702,19.62,19.473,19.514,19.712,19.896,20.04,20.094,20.125,20.118,20.04,18.441,14.768,10.932,7.77,5.279,3.33,1.833,0.726,-0.113,-0.765,-1.271,-1.64,-1.896,-2.075,-2.189,-2.256,-2.291,-2.283,-2.234,-2.161,-2.077,-1.996,-1.917,-1.833,-1.746],"118":[1.178,1.94,6.34,11.945,16.534,19.918,22.207,23.655,24.655,25.416,25.95,26.285,26.487,26.506,26.423,26.304,26.235,26.171,26.095,26.041,25.973,25.886,25.784,25.693,25.61,25.512,25.431,25.313,25.129,24.843,24.382,23.897,23.474,23.09,22.752,22.468,22.269,21.964,19.143,14.024,9.304,5.528,2.664,0.546,-1.027,-2.165,-2.954,-3.47,-3.812,-4.037,-4.178,-4.255,-4.267,-4.216,-4.134,-4.033,-3.925,-3.803,-3.67,-3.52,-3.37,-3.227,-3.083],"119":[1.061,1.423,4.127,8.188,11.875,14.856,17.009,18.427,19.457,20.295,20.972,21.454,21.723,21.854,21.888,21.876,21.863,21.827,21.77,21.764,21.744,21.666,21.572,21.508,21.459,21.417,21.352,21.277,21.153,20.947,20.857,20.847,20.907,20.984,20.979,20.918,20.906,21.052,19.429,15.603,11.654,8.266,5.481,3.31,1.663,0.422,-0.503,-1.174,-1.668,-2.023,-2.263,-2.417,-2.505,-2.543,-2.546,-2.528,-2.501,-2.452,-2.375,-2.292,-2.21,-2.138,-2.064],"120":[1.214,3.062,10.61,18.273,23.945,27.847,30.325,31.814,32.769,33.338,33.627,33.793,33.86,33.742,33.526,33.303,33.164,33.043,32.921,32.836,32.714,32.499,32.315,32.247,32.153,32.001,31.894,31.732,31.448,31.054,30.307,29.613,29.055,28.643,28.338,27.951,27.584,26.873,21.573,14.131,8.189,3.798,0.624,-1.581,-3.139,-4.192,-4.855,-5.263,-5.521,-5.671,-5.739,-5.738,-5.669,-5.523,-5.35,-5.16,-4.951,-4.742,-4.54,-4.328,-4.112,-3.905,-3.695],"121":[1.054,1.851,6.873,13.508,19.08,23.241,26.184,28.139,29.416,30.251,30.753,31.041,31.239,31.295,31.248,31.152,31.132,31.209,31.264,31.267,31.253,31.211,31.14,31.06,30.989,30.902,30.837,30.772,30.612,30.415,30.246,30.148,30.059,29.993,29.836,29.536,29.193,28.761,25.012,18.302,12.336,7.801,4.464,2.055,0.297,-0.97,-1.857,-2.508,-2.988,-3.321,-3.529,-3.645,-3.696,-3.69,-3.642,-3.561,-3.452,-3.319,-3.177,-3.035,-2.895,-2.753,-2.614],"122":[1.122,2.103,8.189,16.179,22.823,27.752,31.229,33.566,35.116,36.147,36.771,37.139,37.372,37.435,37.409,37.321,37.304,37.32,37.311,37.292,37.267,37.204,37.087,37.006,36.945,36.867,36.814,36.744,36.575,36.309,35.969,35.669,35.412,35.219,35.021,34.739,34.427,34.011,29.763,22.051,15.093,9.74,5.747,2.855,0.764,-0.737,-1.796,-2.567,-3.137,-3.531,-3.777,-3.92,-3.986,-3.982,-3.935,-3.851,-3.728,-3.583,-3.428,-3.269,-3.106,-2.945,-2.79],"123":[1.247,2.22,8.412,16.425,23.025,27.949,31.386,33.632,35.166,36.287,37.031,37.519,37.802,37.876,37.82,37.739,37.745,37.764,37.756,37.718,37.658,37.596,37.528,37.428,37.312,37.18,37.086,36.971,36.753,36.421,36.224,36.19,36.195,36.214,36.135,35.965,35.8,35.51,31.306,23.508,16.4,10.878,6.707,3.637,1.406,-0.21,-1.374,-2.243,-2.888,-3.342,-3.645,-3.828,-3.911,-3.939,-3.931,-3.879,-3.775,-3.651,-3.507,-3.353,-3.2,-3.051,-2.9],"142":[1.241,1.859,5.677,10.818,15.138,18.476,20.749,22.203,23.278,24.177,24.884,25.368,25.645,25.743,25.726,25.651,25.622,25.581,25.518,25.495,25.455,25.369,25.272,25.191,25.124,25.04,24.953,24.839,24.633,24.327,24.042,23.781,23.568,23.352,23.086,22.844,22.724,22.616,20.199,15.361,10.781,6.97,4.002,1.777,0.087,-1.172,-2.082,-2.684,-3.088,-3.371,-3.562,-3.679,-3.735,-3.738,-3.702,-3.652,-3.599,-3.525,-3.425,-3.313,-3.201,-3.097,-2.993],"150":[1.261,3.144,10.553,17.996,23.483,27.349,29.893,31.446,32.347,32.822,33.104,33.314,33.425,33.327,33.12,32.843,32.741,32.701,32.601,32.548,32.451,32.249,32.103,31.982,31.913,31.742,31.598,31.421,31.193,31.019,30.578,30.165,29.892,29.688,29.417,28.955,28.547,27.736,21.695,13.73,7.744,3.515,0.547,-1.539,-3.006,-3.998,-4.629,-5.066,-5.353,-5.534,-5.616,-5.614,-5.547,-5.39,-5.206,-5.008,-4.783,-4.561,-4.356,-4.15,-3.951,-3.753,-3.566],"151":[1.059,1.51,4.779,9.509,13.629,16.867,19.21,20.766,21.867,22.716,23.351,23.804,24.039,24.135,24.149,24.135,24.127,24.15,24.164,24.172,24.146,24.09,24.031,23.954,23.878,23.81,23.744,23.678,23.544,23.36,23.427,23.63,23.842,24.024,24.106,24.142,24.188,24.185,22.139,17.568,13.0,9.237,6.266,3.975,2.254,0.987,0.036,-0.692,-1.244,-1.648,-1.932,-2.119,-2.232,-2.296,-2.322,-2.312,-2.274,-2.215,-2.137,-2.055,-1.972,-1.889,-1.804],"152":[1.147,1.632,5.501,11.295,16.368,20.317,23.21,25.22,26.632,27.655,28.355,28.842,29.174,29.334,29.364,29.369,29.421,29.533,29.647,29.696,29.712,29.728,29.735,29.712,29.658,29.596,29.573,29.526,29.409,29.206,29.265,29.496,29.675,29.789,29.779,29.674,29.514,29.287,26.659,20.954,15.376,10.912,7.509,4.931,2.996,1.565,0.503,-0.313,-0.944,-1.409,-1.744,-1.97,-2.115,-2.21,-2.271,-2.289,-2.26,-2.202,-2.127,-2.048,-1.966,-1.88,-1.79],"153":[1.276,2.195,6.897,12.489,16.811,19.93,21.95,23.218,24.081,24.699,25.104,25.373,25.532,25.502,25.36,25.233,25.162,25.101,25.02,24.972,24.9,24.767,24.652,24.605,24.556,24.458,24.38,24.265,24.054,23.772,23.222,22.619,22.096,21.661,21.331,21.023,20.785,20.512,17.216,11.995,7.568,4.131,1.569,-0.296,-1.665,-2.637,-3.265,-3.645,-3.885,-4.052,-4.155,-4.2,-4.179,-4.092,-3.982,-3.865,-3.735,-3.595,-3.452,-3.298,-3.139,-2.981,-2.824],"154":[1.196,3.728,12.709,21.205,27.381,31.63,34.387,36.042,37.007,37.516,37.785,37.965,38.066,37.967,37.756,37.478,37.362,37.245,37.119,37.04,36.915,36.674,36.497,36.407,36.352,36.194,36.07,35.907,35.673,35.398,34.737,34.142,33.736,33.469,33.181,32.721,32.267,31.338,24.431,15.569,8.867,4.154,0.849,-1.447,-3.025,-4.083,-4.768,-5.228,-5.525,-5.695,-5.759,-5.752,-5.677,-5.515,-5.324,-5.115,-4.882,-4.652,-4.434,-4.216,-3.995,-3.787,-3.594]};
// GS IDs for tab 2
const SENSOR_IDS2 = {"112":"GS112","114":"GS114","115":"GS115","117":"GS117","118":"GS118","119":"GS119","120":"GS120","121":"GS121","122":"GS122","123":"GS123","142":"GS142","150":"GS150","151":"GS151","152":"GS152","153":"GS153","154":"GS154"};
const SANDBOX_W2 = 15, SANDBOX_H2 = 24;

// Mote lookup by GS number
function getMote2(k) {
  const n = parseInt(k);
  if (n>=112&&n<=118) return 2;
  if (n>=119&&n<=123) return 3;
  if (n>=142&&n<=153) return 6;
  if (n>=154&&n<=159) return 7;
  return 2;
}
</script>

<script>
const SENSOR_KEYS = Object.keys(COORDS);
const SANDBOX_W = 15, SANDBOX_H = 24;
const PAD = 18;
let DPR = window.devicePixelRatio || 1;

function calcScale() {
  const byHeight = Math.floor((window.innerHeight * 0.80 - PAD*2) / SANDBOX_H);
  const byWidth  = Math.floor((window.innerWidth  * 0.45 - PAD*2) / SANDBOX_W);
  return Math.max(22, Math.min(byHeight, byWidth));
}

let SCALE = calcScale();
let CW = Math.round(SANDBOX_W * SCALE) + PAD*2;
let CH = Math.round(SANDBOX_H * SCALE) + PAD*2;

const heatCanvas   = document.getElementById('heatmap');
const overlayCanvas = document.getElementById('overlay');

function resizeCanvases() {
  SCALE = calcScale();
  DPR = window.devicePixelRatio || 1;
  CW = Math.round(SANDBOX_W * SCALE) + PAD*2;
  CH = Math.round(SANDBOX_H * SCALE) + PAD*2;
  heatCanvas.width = overlayCanvas.width = CW * DPR;
  heatCanvas.height = overlayCanvas.height = CH * DPR;
  heatCanvas.style.width = overlayCanvas.style.width = CW + 'px';
  heatCanvas.style.height = overlayCanvas.style.height = CH + 'px';
  heatCanvas.getContext('2d').setTransform(DPR, 0, 0, DPR, 0, 0);
  overlayCanvas.getContext('2d').setTransform(DPR, 0, 0, DPR, 0, 0);
}

resizeCanvases();

const hCtx = heatCanvas.getContext('2d');
const oCtx = overlayCanvas.getContext('2d');

const MOTE_COLORS  = {2:'#00d4ff',3:'#7affb0',4:'#ffd600',5:'#ff6b35',6:'#c97bff',7:'#ff4d8f'};
const MOTE_COLORS2 = {2:'#00d4ff',3:'#7affb0',6:'#c97bff',7:'#ff4d8f'};

const SENSOR_IDS = {
  'a_2':'GS112','b_2':'GS114','c_2':'GS115','d_2':'GS117','e_2':'GS118',
  'a_3':'GS119','b_3':'GS120','c_3':'GS121','d_3':'GS122','e_3':'GS123',
  'a_4':'GS124','b_4':'GS127','c_4':'GS128','d_4':'GS131','e_4':'GS133',
  'a_5':'GS135','b_5':'GS137','c_5':'HF138','d_5':'GS140','e_5':'GS141',
  'a_6':'GS142','b_6':'GS150','c_6':'GS151','d_6':'GS152','e_6':'GS153',
  'a_7':'GS154','b_7':'GS157','c_7':'GS159'
};

function intensityColor(norm) {
  norm = Math.max(0, Math.min(1, norm));
  let r, g, b;
  if (norm < 0.25) { const t=norm/0.25; r=0; g=Math.round(20+t*180); b=Math.round(80+t*175); }
  else if (norm < 0.5) { const t=(norm-0.25)/0.25; r=Math.round(t*20); g=Math.round(200+t*55); b=Math.round(255-t*255); }
  else if (norm < 0.75) { const t=(norm-0.5)/0.25; r=Math.round(20+t*235); g=Math.round(255-t*50); b=0; }
  else { const t=(norm-0.75)/0.25; r=255; g=Math.round(205-t*205); b=0; }
  return `rgb(${r},${g},${b})`;
}

function contrastText(norm) { return (norm > 0.25 && norm < 0.85) ? '#0a0e14' : '#ffffff'; }

let currentMode = 'spike';
let activeMote = 'all';
let sliderIdx = 0;

function toCanvasX(x) { return PAD + x * SCALE; }
function toCanvasY(y) { return PAD + (-y) * SCALE; }

function valueToColor(norm, alpha=0.85) {
  norm = Math.max(0, Math.min(1, norm));
  let r, g, b;
  if (norm < 0.25) { const t=norm/0.25; r=0; g=Math.round(20+t*180); b=Math.round(80+t*175); }
  else if (norm < 0.5) { const t=(norm-0.25)/0.25; r=Math.round(t*20); g=Math.round(200+t*55); b=Math.round(255-t*255); }
  else if (norm < 0.75) { const t=(norm-0.5)/0.25; r=Math.round(20+t*235); g=Math.round(255-t*50); b=0; }
  else { const t=(norm-0.75)/0.25; r=255; g=Math.round(205-t*205); b=0; }
  return `rgba(${r},${g},${b},${alpha})`;
}

const SCALE_MIN = -10;
const SCALE_MAX = 100;

function drawHeatmap(values) {
  hCtx.clearRect(0,0,CW,CH);
  hCtx.fillStyle='#0d1520'; hCtx.fillRect(0,0,CW,CH);
  const STEP=2, sigma2=(SCALE*3.5)**2;
  const sensors = SENSOR_KEYS.filter(k=>activeMote==='all'||k.endsWith('_'+activeMote))
    .map(k=>({cx:PAD+COORDS[k][0]*SCALE,cy:PAD+(-COORDS[k][1])*SCALE,v:values[k]!=null?values[k]:0}));
  // Boundary anchors — 30% of the lowest sensor value in this frame
  const sensorValsArr = sensors.map(s=>s.v).filter(v=>v>0);
  const BOUNDARY_VAL = sensorValsArr.length ? Math.min(...sensorValsArr) * 0.40 : 1.0;
  const BSTEP=1.5;
  const boundary=[];
  for(let x=0;x<=SANDBOX_W;x+=BSTEP){boundary.push({cx:PAD+x*SCALE,cy:PAD,v:BOUNDARY_VAL});boundary.push({cx:PAD+x*SCALE,cy:PAD+SANDBOX_H*SCALE,v:BOUNDARY_VAL});}
  for(let y=BSTEP;y<SANDBOX_H;y+=BSTEP){boundary.push({cx:PAD,cy:PAD+y*SCALE,v:BOUNDARY_VAL});boundary.push({cx:PAD+SANDBOX_W*SCALE,cy:PAD+y*SCALE,v:BOUNDARY_VAL});}
  const bSigma2=(SCALE*1.8)**2;
  for(let py=PAD;py<CH-PAD;py+=STEP){for(let px=PAD;px<CW-PAD;px+=STEP){
    let wsum=0,vsum=0;
    for(const s of sensors){const d2=(px-s.cx)**2+(py-s.cy)**2;const w=Math.exp(-d2/sigma2);wsum+=w;vsum+=w*s.v;}
    for(const b of boundary){const d2=(px-b.cx)**2+(py-b.cy)**2;const w=Math.exp(-d2/bSigma2);wsum+=w;vsum+=w*b.v;}
    const interp=wsum>0?vsum/wsum:0;
    const norm=Math.max(0,Math.min(1,(interp-SCALE_MIN)/(SCALE_MAX-SCALE_MIN)));
    let r,g,b2;const n=norm;
    if(n<0.25){const t=n/0.25;r=0;g=Math.round(20+t*180);b2=Math.round(80+t*175);}
    else if(n<0.5){const t=(n-0.25)/0.25;r=Math.round(t*20);g=Math.round(200+t*55);b2=Math.round(255-t*255);}
    else if(n<0.75){const t=(n-0.5)/0.25;r=Math.round(20+t*235);g=Math.round(255-t*50);b2=0;}
    else{const t=(n-0.75)/0.25;r=255;g=Math.round(205-t*205);b2=0;}
    hCtx.fillStyle=`rgba(${r},${g},${b2},0.82)`;hCtx.fillRect(px,py,STEP,STEP);
  }}
  hCtx.strokeStyle='#2a3d52';hCtx.lineWidth=1;hCtx.strokeRect(PAD,PAD,SANDBOX_W*SCALE,SANDBOX_H*SCALE);
  hCtx.strokeStyle='rgba(42,61,82,0.4)';hCtx.lineWidth=0.5;
  for(let x=0;x<=SANDBOX_W;x+=3){hCtx.beginPath();hCtx.moveTo(toCanvasX(x),PAD);hCtx.lineTo(toCanvasX(x),CH-PAD);hCtx.stroke();}
  for(let y=0;y<=SANDBOX_H;y+=4){hCtx.beginPath();hCtx.moveTo(PAD,toCanvasY(-y));hCtx.lineTo(CW-PAD,toCanvasY(-y));hCtx.stroke();}
  updateLegend(SCALE_MIN,SCALE_MAX);
}

function drawOverlay(values) {
  oCtx.clearRect(0,0,CW,CH);
  SENSOR_KEYS.forEach(k=>{
    if(activeMote!=='all'&&!k.endsWith('_'+activeMote))return;
    const[x,y]=COORDS[k];const cx=toCanvasX(x);const cy=toCanvasY(y);
    const mote=k.split('_')[1];const v=values[k];
    const norm=Math.max(0,Math.min(1,(v-SCALE_MIN)/(SCALE_MAX-SCALE_MIN)));
    const dotColor=intensityColor(norm);const labelColor=contrastText(norm);
    const gsLabel=SENSOR_IDS[k]||k;const dotLabel=gsLabel.replace(/^(GS|HF)/,'');const r=14;
    oCtx.globalAlpha=0.35;oCtx.beginPath();oCtx.arc(cx,cy,r+2,0,Math.PI*2);
    oCtx.strokeStyle=MOTE_COLORS[mote]||'#fff';oCtx.lineWidth=1.5;oCtx.stroke();
    oCtx.globalAlpha=0.92;oCtx.beginPath();oCtx.arc(cx,cy,r,0,Math.PI*2);oCtx.fillStyle=dotColor;oCtx.fill();
    oCtx.globalAlpha=1;oCtx.fillStyle=labelColor;oCtx.font='bold 11px Share Tech Mono, monospace';
    oCtx.textAlign='center';oCtx.textBaseline='middle';oCtx.fillText(dotLabel,cx,cy);
  });
  oCtx.fillStyle='#7a9ab8';oCtx.font='9px Share Tech Mono, monospace';oCtx.textAlign='center';
  for(let x=0;x<=SANDBOX_W;x+=5)oCtx.fillText(x+'"',toCanvasX(x),CH-4);
  oCtx.textAlign='right';
  for(let y=0;y<=SANDBOX_H;y+=6)oCtx.fillText(y+'"',PAD-3,toCanvasY(-y)+4);
}

function updateLegend(minV,maxV){
  const lc=document.getElementById('legend-canvas');const lCtx=lc.getContext('2d');
  const grad=lCtx.createLinearGradient(0,0,140,0);
  grad.addColorStop(0,'rgba(0,80,150,1)');grad.addColorStop(0.25,'rgba(0,210,255,1)');
  grad.addColorStop(0.5,'rgba(20,255,0,1)');grad.addColorStop(0.75,'rgba(255,205,0,1)');
  grad.addColorStop(1,'rgba(255,0,0,1)');
  lCtx.fillStyle=grad;lCtx.fillRect(0,0,140,10);
  document.getElementById('legend-range').textContent=`${minV.toFixed(1)}–${maxV.toFixed(1)} W/m²`;
}

function getCurrentValues(){
  if(currentMode==='spike')return SPIKE_MAX;
  if(currentMode==='baseline')return BASELINE;
  const snap={};SENSOR_KEYS.forEach(k=>{const arr=TS_VALS[k];snap[k]=arr?arr[sliderIdx]:null;});return snap;
}

function render(values){drawHeatmap(values);drawOverlay(values);updateTable(values);}

function setMode(mode){
  currentMode=mode;
  document.querySelectorAll('.btn').forEach(b=>b.classList.remove('active'));
  document.getElementById('btn-'+mode).classList.add('active');
  document.getElementById('timeline-ctrl').style.display=mode==='timeline'?'flex':'none';
  const titles={spike:'Mar 6 Peak Values (W/m²)',baseline:'Baseline Mean — Mar 7 (W/m²)',timeline:`Mar 6 · ${TS_TIMES[sliderIdx].split(' ')[1]} · 10-min avg (W/m²)`};
  document.getElementById('table-title').textContent=titles[mode];
  if(mode==='spike')render(SPIKE_MAX);else if(mode==='baseline')render(BASELINE);else render(getCurrentValues());
}

function toggleMote(mote,el){
  activeMote=mote;
  document.querySelectorAll('.mote-btn').forEach(b=>b.classList.remove('active'));
  el.classList.add('active');render(getCurrentValues());
}

function onSlider(idx){
  sliderIdx=parseInt(idx);
  const timeStr=TS_TIMES[sliderIdx]?TS_TIMES[sliderIdx].split(' ')[1]:'--:--';
  document.getElementById('time-display').textContent=timeStr;
  document.getElementById('table-title').textContent=`Mar 6 · ${timeStr} · 10-min avg (W/m²)`;
  render(getCurrentValues());
}

function updateTable(values){
  const tbody=document.getElementById('table-body');
  const entries=SENSOR_KEYS.filter(k=>activeMote==='all'||k.endsWith('_'+activeMote))
    .map(k=>({key:k,val:values[k]})).sort((a,b)=>(b.val||0)-(a.val||0));
  tbody.innerHTML=entries.map(e=>{
    const gsLabel=SENSOR_IDS[e.key]||e.key;const mote=e.key.split('_')[1];
    const moteColor=MOTE_COLORS[mote]||'#fff';
    const norm=e.val!=null?Math.max(0,Math.min(1,(e.val-SCALE_MIN)/(SCALE_MAX-SCALE_MIN))):0;
    const pct=norm*100;const barColor=valueToColor(norm);const dotColor=intensityColor(norm);
    return`<tr><td class="sensor-name" style="color:${dotColor}">${gsLabel}</td><td style="color:${moteColor}">M${mote}</td><td class="val-cell">${e.val!=null?e.val.toFixed(2):'N/A'}</td><td class="bar-cell"><div class="bar-bg"><div class="bar-fill" style="width:${pct}%;background:${barColor}"></div></div></td></tr>`;
  }).join('');
}

overlayCanvas.style.pointerEvents='auto';
overlayCanvas.addEventListener('mousemove',(e)=>{
  const rect=overlayCanvas.getBoundingClientRect();const mx=e.clientX-rect.left;const my=e.clientY-rect.top;
  const tip=document.getElementById('tooltip');if(!tip)return;const values=getCurrentValues();
  let closest=null,closestD=Infinity;
  SENSOR_KEYS.forEach(k=>{if(activeMote!=='all'&&!k.endsWith('_'+activeMote))return;
    const cx=toCanvasX(COORDS[k][0]);const cy=toCanvasY(COORDS[k][1]);
    const d=Math.sqrt((mx-cx)**2+(my-cy)**2);if(d<closestD){closestD=d;closest=k;}});
  if(closest&&closestD<22){
    const gsLabel=SENSOR_IDS[closest]||closest;const mote=closest.split('_')[1];const v=values[closest];
    const norm=Math.max(0,Math.min(1,((v||0)-SCALE_MIN)/(SCALE_MAX-SCALE_MIN)));const dotColor=intensityColor(norm);
    tip.style.display='block';tip.style.left=(e.clientX+14)+'px';tip.style.top=(e.clientY-10)+'px';
    tip.innerHTML=`<span style="color:${dotColor}">${gsLabel}</span> <span style="color:${MOTE_COLORS[mote]};font-size:0.6rem">M${mote}</span> · ${v!=null?v.toFixed(3):'N/A'} W/m²<br><span style="color:#4a6070;font-size:0.6rem">(${COORDS[closest][0]}", ${COORDS[closest][1]}")</span>`;
  } else { tip.style.display='none'; }
});
overlayCanvas.addEventListener('mouseleave',()=>{const tip=document.getElementById('tooltip');if(tip)tip.style.display='none';});

let tsFilterMote='all';
function setTsFilter(m,el){
  tsFilterMote=m;
  el.closest('.chart-filter-row').querySelectorAll('.chart-fbtn').forEach(b=>b.classList.remove('active'));
  el.classList.add('active');buildChart1();
}

function chartPad(){return{top:18,right:20,bottom:36,left:46};}

function setupCanvas(id,logicalH){
  const canvas=document.getElementById(id);const dpr=window.devicePixelRatio||1;
  const W=canvas.parentElement.clientWidth||960;const H=logicalH;
  canvas.width=W*dpr;canvas.height=H*dpr;canvas.style.width=W+'px';canvas.style.height=H+'px';
  const ctx=canvas.getContext('2d');ctx.setTransform(dpr,0,0,dpr,0,0);return{ctx,W,H,dpr};
}

function drawAxes(ctx,W,H,pad,xLabels,yMin,yMax,yTicks=5){
  ctx.strokeStyle='#2a3d52';ctx.lineWidth=1;
  ctx.beginPath();ctx.moveTo(pad.left,H-pad.bottom);ctx.lineTo(W-pad.right,H-pad.bottom);ctx.stroke();
  ctx.beginPath();ctx.moveTo(pad.left,pad.top);ctx.lineTo(pad.left,H-pad.bottom);ctx.stroke();
  const step=Math.ceil(xLabels.length/8);
  xLabels.forEach((lbl,i)=>{if(i%step!==0)return;
    const x=pad.left+(i/(xLabels.length-1))*(W-pad.left-pad.right);
    ctx.fillStyle='#7a9ab8';ctx.font='10px Share Tech Mono, monospace';ctx.textAlign='center';
    ctx.fillText(lbl,x,H-pad.bottom+13);
    ctx.strokeStyle='rgba(42,61,82,0.3)';ctx.lineWidth=0.5;
    ctx.beginPath();ctx.moveTo(x,pad.top);ctx.lineTo(x,H-pad.bottom);ctx.stroke();});
  for(let i=0;i<=yTicks;i++){
    const v=yMin+(i/yTicks)*(yMax-yMin);const y=H-pad.bottom-(i/yTicks)*(H-pad.top-pad.bottom);
    ctx.fillStyle='#7a9ab8';ctx.font='10px Share Tech Mono, monospace';ctx.textAlign='right';
    ctx.fillText(v.toFixed(0),pad.left-5,y+3);
    ctx.strokeStyle='rgba(42,61,82,0.3)';ctx.lineWidth=0.5;
    ctx.beginPath();ctx.moveTo(pad.left,y);ctx.lineTo(W-pad.right,y);ctx.stroke();}
}

function toChartX(i,n,W,pad){return pad.left+(i/(n-1))*(W-pad.left-pad.right);}
function toChartY(v,yMin,yMax,H,pad){return H-pad.bottom-((v-yMin)/(yMax-yMin))*(H-pad.top-pad.bottom);}

function drawLine(ctx,xs,ys,color,alpha=0.7,width=1){
  ctx.save();ctx.globalAlpha=alpha;ctx.strokeStyle=color;ctx.lineWidth=width;ctx.lineJoin='round';
  ctx.beginPath();let started=false;
  xs.forEach((x,i)=>{if(ys[i]==null){started=false;return;}if(!started){ctx.moveTo(x,ys[i]);started=true;}else ctx.lineTo(x,ys[i]);});
  ctx.stroke();ctx.restore();
}

const SHORT_TIMES = TS_TIMES.map(t=>t.split(' ')[1]);
const MOTE_LIST = [2,3,4,5,6,7];

function buildChart1(){
  const{ctx,W,H}=setupCanvas('chart-ts',240);const pad=chartPad();
  ctx.fillStyle='#0d1520';ctx.fillRect(0,0,W,H);
  const filteredKeys=tsFilterMote==='all'?SENSOR_KEYS:SENSOR_KEYS.filter(k=>k.endsWith('_'+tsFilterMote));
  let yMin=Infinity,yMax=-Infinity;
  filteredKeys.forEach(k=>{TS_VALS[k].forEach(v=>{if(v!=null){yMin=Math.min(yMin,v);yMax=Math.max(yMax,v);}});});
  yMin=Math.floor(yMin/10)*10;yMax=Math.ceil(yMax/10)*10;
  drawAxes(ctx,W,H,pad,SHORT_TIMES,yMin,yMax,5);
  const n=TS_TIMES.length;
  filteredKeys.forEach(k=>{
    const mote=k.split('_')[1];const color=MOTE_COLORS[mote];
    const xs=TS_VALS[k].map((_,i)=>toChartX(i,n,W,pad));
    const ys=TS_VALS[k].map(v=>v==null?null:toChartY(v,yMin,yMax,H,pad));
    drawLine(ctx,xs,ys,color,tsFilterMote==='all'?0.55:0.85,tsFilterMote==='all'?1:1.5);});
  ctx.save();ctx.translate(11,H/2);ctx.rotate(-Math.PI/2);ctx.fillStyle='#7a9ab8';
  ctx.font='10px Share Tech Mono, monospace';ctx.textAlign='center';ctx.fillText('W/m²',0,0);ctx.restore();
}

function buildChart2(){
  const{ctx,W,H}=setupCanvas('chart-mote',220);const pad=chartPad();
  ctx.fillStyle='#0d1520';ctx.fillRect(0,0,W,H);
  const moteAvgs={};
  MOTE_LIST.forEach(m=>{const keys=SENSOR_KEYS.filter(k=>k.endsWith('_'+m));
    moteAvgs[m]=TS_TIMES.map((_,i)=>{const vals=keys.map(k=>TS_VALS[k][i]).filter(v=>v!=null);
      return vals.length?vals.reduce((a,b)=>a+b,0)/vals.length:null;});});
  let yMin=Infinity,yMax=-Infinity;
  MOTE_LIST.forEach(m=>moteAvgs[m].forEach(v=>{if(v!=null){yMin=Math.min(yMin,v);yMax=Math.max(yMax,v);}}));
  yMin=Math.floor(yMin/10)*10;yMax=Math.ceil(yMax/10)*10;
  drawAxes(ctx,W,H,pad,SHORT_TIMES,yMin,yMax,4);
  const n=TS_TIMES.length;
  MOTE_LIST.forEach(m=>{const color=MOTE_COLORS[m];
    const xs=moteAvgs[m].map((_,i)=>toChartX(i,n,W,pad));
    const ys=moteAvgs[m].map(v=>v==null?null:toChartY(v,yMin,yMax,H,pad));
    drawLine(ctx,xs,ys,color,0.9,2);
    let peakI=0,peakV=-Infinity;moteAvgs[m].forEach((v,i)=>{if(v!=null&&v>peakV){peakV=v;peakI=i;}});
    const px=toChartX(peakI,n,W,pad);const py=toChartY(peakV,yMin,yMax,H,pad);
    ctx.fillStyle=color;ctx.font='bold 9px Share Tech Mono, monospace';ctx.textAlign='center';ctx.fillText('M'+m,px,py-6);});
  ctx.save();ctx.translate(11,H/2);ctx.rotate(-Math.PI/2);ctx.fillStyle='#7a9ab8';
  ctx.font='10px Share Tech Mono, monospace';ctx.textAlign='center';ctx.fillText('W/m²',0,0);ctx.restore();
}

function buildChart3(){
  const{ctx,W,H}=setupCanvas('chart-cool',220);const pad=chartPad();
  ctx.fillStyle='#0d1520';ctx.fillRect(0,0,W,H);
  const coolData={};let maxLen=0;
  SENSOR_KEYS.forEach(k=>{const vals=TS_VALS[k];let peakI=0,peakV=-Infinity;
    vals.forEach((v,i)=>{if(v!=null&&v>peakV){peakV=v;peakI=i;}});
    if(peakV<=1)return;const tail=vals.slice(peakI).map(v=>v==null?null:v/peakV);
    coolData[k]=tail;maxLen=Math.max(maxLen,tail.length);});
  const xLabels=Array.from({length:maxLen},(_,i)=>i*10+'m');
  drawAxes(ctx,W,H,pad,xLabels,0,1,4);
  ctx.fillStyle='#0d1520';
  [0,0.25,0.5,0.75,1].forEach(frac=>{const y=toChartY(frac,0,1,H,pad);ctx.fillRect(0,y-8,pad.left-1,14);});
  ctx.fillStyle='#7a9ab8';ctx.font='10px Share Tech Mono, monospace';
  [0,0.25,0.5,0.75,1].forEach(frac=>{const y=toChartY(frac,0,1,H,pad);ctx.textAlign='right';ctx.fillText(Math.round(frac*100)+'%',pad.left-5,y+3);});
  Object.entries(coolData).forEach(([k,tail])=>{
    const mote=k.split('_')[1];const color=MOTE_COLORS[mote];const n=maxLen;
    const xs=tail.map((_,i)=>toChartX(i,n,W,pad));
    const ys=tail.map(v=>v==null?null:toChartY(v,0,1,H,pad));drawLine(ctx,xs,ys,color,0.6,1.5);});
  ctx.fillStyle='#7a9ab8';ctx.font='10px Share Tech Mono, monospace';ctx.textAlign='left';
  ctx.fillText("100% = each sensor's individual peak value",pad.left+6,pad.top+12);
  ctx.save();ctx.translate(11,H/2);ctx.rotate(-Math.PI/2);ctx.fillStyle='#7a9ab8';
  ctx.font='10px Share Tech Mono, monospace';ctx.textAlign='center';ctx.fillText('% of peak',0,0);ctx.restore();
}

function buildAllCharts(){buildChart1();buildChart2();buildChart3();}

// ── TAB 2 RENDERING ──
const SENSOR_KEYS2 = Object.keys(COORDS2);
const PAD2 = 18;
let SCALE2 = 0, CW2 = 0, CH2 = 0;
let mode2='spike', sliderIdx2=0, activeMote2='all', tsFilterMote2='all';

function calcScale2(){
  const byHeight=Math.floor((window.innerHeight*0.80-PAD2*2)/SANDBOX_H2);
  const byWidth=Math.floor((window.innerWidth*0.45-PAD2*2)/SANDBOX_W2);
  return Math.max(22,Math.min(byHeight,byWidth));
}

let heatCanvas2=null, overlayCanvas2=null;

function resizeCanvases2(){
  heatCanvas2=document.getElementById('heatmap2');
  overlayCanvas2=document.getElementById('overlay2');
  if(!heatCanvas2||!overlayCanvas2)return;
  SCALE2=calcScale2();
  CW2=SANDBOX_W2*SCALE2+PAD2*2; CH2=SANDBOX_H2*SCALE2+PAD2*2;
  const DPR=window.devicePixelRatio||1;
  [heatCanvas2,overlayCanvas2].forEach(c=>{c.width=CW2*DPR;c.height=CH2*DPR;c.style.width=CW2+'px';c.style.height=CH2+'px';});
  heatCanvas2.getContext('2d').setTransform(DPR,0,0,DPR,0,0);
  overlayCanvas2.getContext('2d').setTransform(DPR,0,0,DPR,0,0);
  document.getElementById('sandbox-wrap-2').style.width=CW2+'px';
  document.getElementById('sandbox-wrap-2').style.height=CH2+'px';
  drawLegend2();
}

function toX2(x){return PAD2+x*SCALE2;}
function toY2(y){return PAD2+(-y)*SCALE2;}

function drawLegend2(){
  const lc=document.getElementById('legend-canvas-2');if(!lc)return;
  const ctx=lc.getContext('2d');
  const grad=ctx.createLinearGradient(0,0,140,0);
  grad.addColorStop(0,'rgba(0,80,150,1)');grad.addColorStop(0.25,'rgba(0,210,255,1)');
  grad.addColorStop(0.5,'rgba(20,255,0,1)');grad.addColorStop(0.75,'rgba(255,205,0,1)');
  grad.addColorStop(1,'rgba(255,0,0,1)');
  ctx.fillStyle=grad;ctx.fillRect(0,0,140,10);
  const hi2=Math.ceil(Math.max(...SENSOR_KEYS2.map(k=>SPIKE_MAX2[k]))/5)*5;
  document.getElementById('legend-range-2').textContent=`0–${hi2} W/m²`;
}

function getCurrentValues2(){
  if(mode2==='spike')return SPIKE_MAX2;
  if(mode2==='baseline')return BASELINE2;
  return Object.fromEntries(SENSOR_KEYS2.map(k=>[k,TS_VALS2[k]?.[sliderIdx2]??0]));
}

function render2(vals){
  if(!heatCanvas2||!overlayCanvas2)return;
  const ctx=heatCanvas2.getContext('2d');
  ctx.clearRect(0,0,CW2,CH2);
  const lo2=0,hi2=Math.ceil(Math.max(...SENSOR_KEYS2.map(k=>SPIKE_MAX2[k]))/5)*5;
  const positions=SENSOR_KEYS2.map(k=>({cx:toX2(COORDS2[k][0]),cy:toY2(COORDS2[k][1]),v:vals[k]||0}));
  const STEP=2,sigma2=Math.pow(SCALE2*3.5,2);
  // Boundary anchors — 30% of the lowest sensor value in this frame
  const sensorVals = SENSOR_KEYS2.map(k=>vals[k]||0).filter(v=>v>0);
  const BOUNDARY_VAL2 = sensorVals.length ? Math.min(...sensorVals) * 0.40 : 1.0;
  const BSTEP2=1.5;
  const boundary2=[];
  for(let x=0;x<=SANDBOX_W2;x+=BSTEP2){boundary2.push({cx:toX2(x),cy:toY2(0),v:BOUNDARY_VAL2});boundary2.push({cx:toX2(x),cy:toY2(-SANDBOX_H2),v:BOUNDARY_VAL2});}
  for(let y=BSTEP2;y<SANDBOX_H2;y+=BSTEP2){boundary2.push({cx:toX2(0),cy:toY2(-y),v:BOUNDARY_VAL2});boundary2.push({cx:toX2(SANDBOX_W2),cy:toY2(-y),v:BOUNDARY_VAL2});}
  const bSigma2_2=Math.pow(SCALE2*1.8,2);
  for(let py=PAD2;py<CH2-PAD2;py+=STEP){for(let px=PAD2;px<CW2-PAD2;px+=STEP){
    let wsum=0,vsum=0;
    positions.forEach(({cx,cy,v})=>{const d2=(px-cx)**2+(py-cy)**2;const w=Math.exp(-d2/sigma2);wsum+=w;vsum+=w*v;});
    boundary2.forEach(b=>{const d2=(px-b.cx)**2+(py-b.cy)**2;const w=Math.exp(-d2/bSigma2_2);wsum+=w;vsum+=w*b.v;});
    const vi=wsum>0?vsum/wsum:0;
    const norm=Math.max(0,Math.min(1,(vi-lo2)/(hi2-lo2)));
    ctx.fillStyle=valueToColor(norm,1);ctx.fillRect(px,py,STEP,STEP);
  }}
  ctx.strokeStyle='rgba(0,212,255,0.3)';ctx.lineWidth=1;ctx.strokeRect(PAD2,PAD2,SANDBOX_W2*SCALE2,SANDBOX_H2*SCALE2);
  // overlay dots
  const oct=overlayCanvas2.getContext('2d');oct.clearRect(0,0,CW2,CH2);
  SENSOR_KEYS2.forEach(k=>{
    const mote=getMote2(k);if(activeMote2!=='all'&&activeMote2!=mote)return;
    const cx=toX2(COORDS2[k][0]),cy=toY2(COORDS2[k][1]);
    const v=vals[k]||0;const norm=Math.max(0,Math.min(1,(v-lo2)/(hi2-lo2)));
    const dotColor=intensityColor(norm);const labelColor=contrastText(norm);
    const id=SENSOR_IDS2[k]||k;const dotLabel=id.replace(/^(GS|HF)/,'');const r=14;
    oct.globalAlpha=0.35;oct.beginPath();oct.arc(cx,cy,r+2,0,Math.PI*2);
    oct.strokeStyle=MOTE_COLORS2[mote]||'#fff';oct.lineWidth=1.5;oct.stroke();
    oct.globalAlpha=0.92;oct.beginPath();oct.arc(cx,cy,r,0,Math.PI*2);oct.fillStyle=dotColor;oct.fill();
    oct.globalAlpha=1;oct.fillStyle=labelColor;oct.font='bold 11px Share Tech Mono, monospace';
    oct.textAlign='center';oct.textBaseline='middle';oct.fillText(dotLabel,cx,cy);
  });
  oct.globalAlpha=1;oct.fillStyle='#7a9ab8';oct.font='9px Share Tech Mono, monospace';oct.textAlign='center';
  for(let x=0;x<=SANDBOX_W2;x+=5)oct.fillText(x+'"',toX2(x),CH2-4);
  oct.textAlign='right';for(let y=0;y<=SANDBOX_H2;y+=6)oct.fillText(y+'"',PAD2-3,toY2(-y)+4);
  updateTable2(vals);
}

function updateTable2(vals){
  const tbody=document.getElementById('table-body-2');if(!tbody)return;
  const hiVal=Math.max(...SENSOR_KEYS2.map(k=>SPIKE_MAX2[k]));
  const rows=SENSOR_KEYS2.map(k=>({k,v:vals[k]||0,mote:getMote2(k)}))
    .filter(r=>activeMote2==='all'||activeMote2==r.mote).sort((a,b)=>b.v-a.v);
  tbody.innerHTML=rows.map(({k,v,mote})=>{
    const pct=Math.max(0,(v/hiVal)*100).toFixed(0);
    const norm=Math.max(0,Math.min(1,(v-0)/(hiVal-0)));
    const barColor=valueToColor(norm);const id=SENSOR_IDS2[k]||k;
    return`<tr><td>${id}</td><td style="color:${MOTE_COLORS2[mote]||'#fff'}">${mote}</td><td style="text-align:right;font-family:'Share Tech Mono',monospace">${v.toFixed(2)}</td><td><div style="height:6px;width:${pct}%;background:${barColor};border-radius:2px"></div></td></tr>`;
  }).join('');
  const titles={spike:'Mar 12 Peak Values (W/m²)',baseline:'Baseline Values (W/m²)',timeline:`Timeline: ${TS_TIMES2[sliderIdx2]||''}`};
  const el=document.getElementById('table-title-2');if(el)el.textContent=titles[mode2]||'';
}

function setMode2(m){
  mode2=m;['spike','baseline','timeline'].forEach(x=>{const b=document.getElementById('btn2-'+x);if(b)b.classList.toggle('active',x===m);});
  const tc=document.getElementById('timeline-ctrl-2');if(tc)tc.style.display=m==='timeline'?'flex':'none';
  render2(getCurrentValues2());
}

function onSlider2(v){
  sliderIdx2=parseInt(v);const disp=document.getElementById('time-display-2');
  if(disp)disp.textContent=TS_TIMES2[sliderIdx2]||'';render2(getCurrentValues2());
}

function toggleMote2(m,btn){
  activeMote2=m;btn.closest('.mote-group').querySelectorAll('.mote-btn').forEach(b=>b.classList.remove('active'));
  btn.classList.add('active');render2(getCurrentValues2());buildAllCharts2();
}

function setTsFilter2(m,btn){
  tsFilterMote2=m;btn.closest('.chart-filter-row').querySelectorAll('.chart-fbtn').forEach(b=>b.classList.remove('active'));
  btn.classList.add('active');buildTsChart2();
}

function buildTsChart2(){
  const{ctx,W,H}=setupCanvas('chart-ts-2',240);const pad=chartPad();
  ctx.fillStyle='#0d1520';ctx.fillRect(0,0,W,H);
  const filteredKeys=tsFilterMote2==='all'?SENSOR_KEYS2:SENSOR_KEYS2.filter(k=>getMote2(k)==tsFilterMote2);
  let yMin=Infinity,yMax=-Infinity;
  filteredKeys.forEach(k=>{(TS_VALS2[k]||[]).forEach(v=>{if(v!=null){yMin=Math.min(yMin,v);yMax=Math.max(yMax,v);}});});
  if(!isFinite(yMin)){yMin=0;yMax=40;}
  yMin=Math.floor(yMin/10)*10;yMax=Math.ceil(yMax/10)*10;
  drawAxes(ctx,W,H,pad,TS_TIMES2,yMin,yMax,5);
  const n=TS_TIMES2.length;
  SENSOR_KEYS2.forEach(k=>{
    if(tsFilterMote2!=='all'&&getMote2(k)!=tsFilterMote2)return;
    const color=MOTE_COLORS2[getMote2(k)]||'#fff';
    const xs=(TS_VALS2[k]||[]).map((_,i)=>toChartX(i,n,W,pad));
    const ys=(TS_VALS2[k]||[]).map(v=>v==null?null:toChartY(v,yMin,yMax,H,pad));
    drawLine(ctx,xs,ys,color,tsFilterMote2==='all'?0.55:0.85,tsFilterMote2==='all'?1:1.5);});
  ctx.save();ctx.translate(11,H/2);ctx.rotate(-Math.PI/2);ctx.fillStyle='#7a9ab8';
  ctx.font='10px Share Tech Mono, monospace';ctx.textAlign='center';ctx.fillText('W/m²',0,0);ctx.restore();
}

function buildMoteChart2(){
  const{ctx,W,H}=setupCanvas('chart-mote-2',220);const pad=chartPad();
  ctx.fillStyle='#0d1520';ctx.fillRect(0,0,W,H);
  const motes2=[2,3,6,7];const moteAvgs2={};
  motes2.forEach(m=>{const ks=SENSOR_KEYS2.filter(k=>getMote2(k)===m);
    moteAvgs2[m]=TS_TIMES2.map((_,i)=>{const vs=ks.map(k=>(TS_VALS2[k]||[])[i]).filter(v=>v!=null);
      return vs.length?vs.reduce((a,b)=>a+b,0)/vs.length:null;});});
  let yMin=Infinity,yMax=-Infinity;
  motes2.forEach(m=>moteAvgs2[m].forEach(v=>{if(v!=null){yMin=Math.min(yMin,v);yMax=Math.max(yMax,v);}}));
  if(!isFinite(yMin)){yMin=0;yMax=40;}
  yMin=Math.floor(yMin/10)*10;yMax=Math.ceil(yMax/10)*10;
  drawAxes(ctx,W,H,pad,TS_TIMES2,yMin,yMax,4);
  const n=TS_TIMES2.length;
  motes2.forEach(m=>{const color=MOTE_COLORS2[m];
    const xs=moteAvgs2[m].map((_,i)=>toChartX(i,n,W,pad));
    const ys=moteAvgs2[m].map(v=>v==null?null:toChartY(v,yMin,yMax,H,pad));
    drawLine(ctx,xs,ys,color,0.9,2);
    let peakI=0,peakV=-Infinity;moteAvgs2[m].forEach((v,i)=>{if(v!=null&&v>peakV){peakV=v;peakI=i;}});
    if(isFinite(peakV)){const px=toChartX(peakI,n,W,pad);const py=toChartY(peakV,yMin,yMax,H,pad);
      ctx.fillStyle=color;ctx.font='bold 9px Share Tech Mono, monospace';ctx.textAlign='center';ctx.fillText('M'+m,px,py-6);}});
  ctx.save();ctx.translate(11,H/2);ctx.rotate(-Math.PI/2);ctx.fillStyle='#7a9ab8';
  ctx.font='10px Share Tech Mono, monospace';ctx.textAlign='center';ctx.fillText('W/m²',0,0);ctx.restore();
}

function buildCoolChart2(){
  const{ctx,W,H}=setupCanvas('chart-cool-2',220);const pad=chartPad();
  ctx.fillStyle='#0d1520';ctx.fillRect(0,0,W,H);
  const coolData2={};let maxLen=0;
  SENSOR_KEYS2.forEach(k=>{const vals=TS_VALS2[k]||[];let peakI=0,peakV=-Infinity;
    vals.forEach((v,i)=>{if(v!=null&&v>peakV){peakV=v;peakI=i;}});
    if(peakV<=1)return;const tail=vals.slice(peakI).map(v=>v==null?null:v/peakV);
    coolData2[k]=tail;maxLen=Math.max(maxLen,tail.length);});
  const xLabels2=Array.from({length:maxLen},(_,i)=>i*10+'m');
  drawAxes(ctx,W,H,pad,xLabels2,0,1,4);
  ctx.fillStyle='#0d1520';
  [0,0.25,0.5,0.75,1].forEach(frac=>{const y=toChartY(frac,0,1,H,pad);ctx.fillRect(0,y-8,pad.left-1,14);});
  ctx.fillStyle='#7a9ab8';ctx.font='10px Share Tech Mono, monospace';
  [0,0.25,0.5,0.75,1].forEach(frac=>{const y=toChartY(frac,0,1,H,pad);ctx.textAlign='right';ctx.fillText(Math.round(frac*100)+'%',pad.left-5,y+3);});
  Object.entries(coolData2).forEach(([k,tail])=>{
    const color=MOTE_COLORS2[getMote2(k)]||'#fff';const n=maxLen;
    const xs=tail.map((_,i)=>toChartX(i,n,W,pad));
    const ys=tail.map(v=>v==null?null:toChartY(v,0,1,H,pad));drawLine(ctx,xs,ys,color,0.6,1.5);});
  ctx.fillStyle='#7a9ab8';ctx.font='10px Share Tech Mono, monospace';ctx.textAlign='left';
  ctx.fillText("100% = each sensor's individual peak value",pad.left+6,pad.top+12);
  ctx.save();ctx.translate(11,H/2);ctx.rotate(-Math.PI/2);ctx.fillStyle='#7a9ab8';
  ctx.font='10px Share Tech Mono, monospace';ctx.textAlign='center';ctx.fillText('% of peak',0,0);ctx.restore();
}

function buildAllCharts2(){buildTsChart2();buildMoteChart2();buildCoolChart2();}

// ── TAB SWITCHING ──
let tab2Initialized=false;
function switchTab(n,btn){
  document.querySelectorAll('.tab-btn').forEach(b=>b.classList.remove('active'));
  document.querySelectorAll('.tab-panel').forEach(p=>p.classList.remove('active'));
  btn.classList.add('active');document.getElementById('tab-'+n).classList.add('active');
  if(n===2&&!tab2Initialized){tab2Initialized=true;setTimeout(()=>{resizeCanvases2();render2(getCurrentValues2());buildAllCharts2();},50);}
}

window.addEventListener('resize',()=>{
  resizeCanvases();render(getCurrentValues());buildAllCharts();
  if(tab2Initialized){resizeCanvases2();render2(getCurrentValues2());buildAllCharts2();}
});

if(document.readyState==='loading'){document.addEventListener('DOMContentLoaded',()=>setTimeout(buildAllCharts,50));}
else{setTimeout(buildAllCharts,50);}
</script>
</body>
</html>
