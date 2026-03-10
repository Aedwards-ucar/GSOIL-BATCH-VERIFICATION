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
    --border: #1e2d3d;
    --accent: #00d4ff;
    --accent2: #ff6b35;
    --text: #c8d8e8;
    --muted: #4a6070;
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
    margin-bottom: 4px;
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
    align-items: flex-start;
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

  canvas#heatmap {
    display: block;
  }

  canvas#overlay {
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
    max-height: 420px;
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
</style>
</head>
<body>

<h1>Gsoil Sandbox Heatmap</h1>
<p class="subtitle">NCAR · Ground Soil Heat Flux · W/m² · 15×24 in sandbox</p>

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
        <button class="btn active" id="btn-spike" onclick="setMode('spike')">SPIKE MAX</button>
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
      <h3 id="table-title">Spike Peak Values (W/m²)</h3>
      <table id="sensor-table">
        <thead>
          <tr>
            <th>SENSOR</th>
            <th>MOTE</th>
            <th style="text-align:right">VALUE</th>
            <th>MAGNITUDE</th>
          </tr>
        </thead>
        <tbody id="table-body"></tbody>
      </table>
    </div>
  </div>
</div>

<div class="tooltip" id="tooltip"></div>

<script>
const COORDS = {"a_2":[5,10],"b_2":[3,9],"c_2":[3,5.5],"d_2":[5.5,4],"e_2":[7.5,5],"a_3":[4.5,17],"b_3":[5,14],"c_3":[3.5,20.5],"d_3":[3.5,15.5],"e_3":[4.5,13],"a_4":[7.5,13.5],"b_4":[5,20],"c_4":[5.5,18.5],"d_4":[7,17],"e_4":[7.5,11.5],"a_5":[12.5,16],"b_5":[11,20],"c_5":[9.5,17.7],"d_5":[10,13],"e_5":[13.5,18.5],"a_6":[12.5,10.5],"b_6":[6,5.5],"c_6":[12,6.5],"d_6":[10.5,8.5],"e_6":[8,3.5],"a_7":[12,14],"b_7":[10,5],"c_7":[8,8]};
const SPIKE_MAX = {"a_2":286.55,"b_2":248.41,"c_2":72.963,"d_2":65.731,"e_2":65.029,"a_3":99.453,"b_3":15.738,"c_3":42.563,"d_3":172.17,"e_3":23.276,"a_4":46.797,"b_4":99.97,"c_4":43.283,"d_4":7.774,"e_4":54.926,"a_5":29.747,"b_5":9.895,"c_5":113.82,"d_5":142.32,"e_5":79.926,"a_6":17.806,"b_6":64.328,"c_6":105.42,"d_6":176.73,"e_6":6.029,"a_7":93.592,"b_7":35.387,"c_7":36.189};
const BASELINE = {"a_2":0.594,"b_2":0.782,"c_2":0.57,"d_2":0.82,"e_2":0.896,"a_3":0.653,"b_3":0.868,"c_3":0.502,"d_3":0.847,"e_3":0.877,"a_4":0.854,"b_4":0.874,"c_4":0.797,"d_4":0.77,"e_4":0.653,"a_5":0.745,"b_5":1.0,"c_5":0.887,"d_5":0.784,"e_5":0.576,"a_6":0.822,"b_6":0.854,"c_6":0.751,"d_6":0.889,"e_6":0.773,"a_7":0.724,"b_7":0.713,"c_7":0.641};

// Timeseries: 03-06 16:00 to 23:00, 10-min increments (42 steps)
const TS_TIMES = ["2026-03-06 16:00:00","2026-03-06 16:10:00","2026-03-06 16:20:00","2026-03-06 16:30:00","2026-03-06 16:40:00","2026-03-06 16:50:00","2026-03-06 17:00:00","2026-03-06 17:10:00","2026-03-06 17:20:00","2026-03-06 17:30:00","2026-03-06 17:40:00","2026-03-06 17:50:00","2026-03-06 18:00:00","2026-03-06 18:10:00","2026-03-06 18:20:00","2026-03-06 18:30:00","2026-03-06 18:40:00","2026-03-06 18:50:00","2026-03-06 19:00:00","2026-03-06 19:10:00","2026-03-06 19:20:00","2026-03-06 19:30:00","2026-03-06 19:40:00","2026-03-06 19:50:00","2026-03-06 20:00:00","2026-03-06 20:10:00","2026-03-06 20:20:00","2026-03-06 20:30:00","2026-03-06 20:40:00","2026-03-06 20:50:00","2026-03-06 21:00:00","2026-03-06 21:10:00","2026-03-06 21:20:00","2026-03-06 21:30:00","2026-03-06 21:40:00","2026-03-06 21:50:00","2026-03-06 22:00:00","2026-03-06 22:10:00","2026-03-06 22:20:00","2026-03-06 22:30:00","2026-03-06 22:40:00","2026-03-06 22:50:00"];
const TS_VALS = {"a_2":[0.934,0.949,0.961,0.967,0.972,0.984,2.673,12.307,26.28,39.33,50.411,58.679,64.82,69.124,72.096,74.136,75.483,76.347,76.868,77.133,77.234,77.243,77.114,76.865,71.615,57.44,42.385,29.846,20.153,12.919,7.568,3.645,0.805,-1.242,-2.745,-3.825,-4.568,-5.032,-5.268,-5.347,-5.319,-5.251],"b_2":[1.217,1.239,1.259,1.27,1.277,1.289,2.369,10.496,24.145,37.694,49.406,58.122,64.428,68.999,72.336,74.791,76.547,77.811,78.711,79.342,79.778,80.094,80.269,80.347,76.986,64.878,50.299,37.436,27.147,19.294,13.375,8.946,5.67,3.247,1.414,0.042,-0.96,-1.655,-2.089,-2.34,-2.459,-2.524],"c_2":[0.832,0.857,0.877,0.885,0.892,0.903,2.531,11.873,24.906,36.665,46.957,53.806,58.769,62.246,64.697,66.377,67.453,68.214,68.671,68.967,69.114,69.192,69.172,68.954,65.035,53.225,40.327,29.532,21.225,15.09,10.563,7.22,4.77,2.953,1.556,0.509,-0.265,-0.792,-1.12,-1.322,-1.43,-1.515],"d_2":[1.272,1.301,1.321,1.332,1.335,1.341,1.946,6.175,13.568,21.417,28.48,35.404,41.285,45.658,48.788,50.976,52.434,53.466,54.144,54.534,54.732,54.817,54.84,54.764,53.154,47.114,38.929,31.001,24.176,18.642,14.279,10.891,8.297,6.276,4.655,3.382,2.402,1.683,1.168,0.788,0.526,0.313],"e_2":[1.378,1.4,1.421,1.436,1.44,1.448,2.175,8.728,21.276,34.785,46.869,56.816,64.57,70.172,74.115,76.862,78.673,79.861,80.597,81.006,81.197,81.254,81.201,81.06,78.564,68.458,54.745,41.758,30.927,22.426,15.885,10.897,7.165,4.384,2.261,0.67,-0.496,-1.324,-1.871,-2.217,-2.411,-2.515],"a_3":[0.943,0.954,0.963,0.965,0.968,0.974,1.358,5.033,12.407,20.644,28.029,33.872,38.394,41.983,44.834,47.121,48.97,50.428,51.582,52.525,53.321,54.013,54.567,55.049,54.102,48.443,40.176,32.068,25.15,19.545,15.098,11.637,8.978,6.923,5.309,4.037,3.05,2.295,1.738,1.333,1.036,0.795],"b_3":[1.354,1.363,1.37,1.372,1.372,1.378,2.043,7.992,19.611,32.46,43.96,53.772,61.618,67.55,71.965,75.269,77.749,79.568,80.897,81.855,82.566,83.123,83.506,83.818,81.298,70.697,56.589,43.318,32.244,23.442,16.586,11.335,7.379,4.408,2.149,0.443,-0.818,-1.723,-2.328,-2.707,-2.93,-3.072],"c_3":[0.842,0.858,0.876,0.881,0.89,0.9,1.041,1.945,3.57,5.422,7.191,8.767,9.993,10.935,11.663,12.198,12.563,12.759,12.848,12.938,13.051,13.17,13.181,13.218,12.727,11.244,9.211,7.124,5.287,3.718,2.437,1.465,0.729,0.137,-0.349,-0.738,-1.028,-1.223,-1.317,-1.352,-1.353,-1.364],"d_3":[1.201,1.216,1.228,1.232,1.236,1.244,1.767,6.857,17.056,28.311,38.323,46.4,52.627,57.463,61.253,64.278,66.717,68.644,70.188,71.457,72.536,73.476,74.248,74.969,73.532,65.234,53.608,42.547,33.278,25.862,20.032,15.525,12.083,9.435,7.357,5.723,4.453,3.482,2.769,2.249,1.866,1.553],"e_3":[1.331,1.345,1.358,1.363,1.368,1.38,2.644,11.861,27.328,42.825,56.132,66.863,75.046,81.034,85.383,88.578,90.918,92.598,93.815,94.694,95.351,95.862,96.18,96.427,91.712,76.178,58.296,42.845,30.627,21.314,14.298,9.076,5.232,2.401,0.282,-1.292,-2.425,-3.201,-3.677,-3.937,-4.049,-4.098],"a_4":[1.369,1.377,1.384,1.385,1.386,1.393,2.542,10.626,24.018,37.578,49.188,58.625,66.086,71.782,75.994,79.076,81.301,82.849,83.885,84.548,84.961,85.235,85.34,85.286,81.703,69.505,54.622,41.154,30.106,21.4,14.65,9.492,5.61,2.709,0.517,-1.122,-2.316,-3.155,-3.696,-4.01,-4.172,-4.266],"b_4":[1.32,1.334,1.347,1.353,1.358,1.365,1.436,2.251,4.343,7.224,10.286,13.218,15.759,17.879,19.639,21.096,22.301,23.261,24.031,24.688,25.273,25.818,26.261,26.758,26.764,25.623,23.189,20.195,17.246,14.588,12.274,10.345,8.78,7.496,6.407,5.491,4.74,4.137,3.67,3.312,3.025,2.761],"c_4":[1.235,1.243,1.249,1.252,1.251,1.256,1.323,2.081,4.061,6.807,9.729,12.539,15.074,17.221,19.004,20.482,21.716,22.716,23.54,24.21,24.779,25.3,25.729,26.117,26.199,25.238,23.011,20.201,17.389,14.814,12.553,10.653,9.09,7.798,6.705,5.788,5.032,4.424,3.948,3.569,3.255,2.974],"d_4":[1.193,1.201,1.207,1.207,1.205,1.207,1.476,4.466,11.093,18.977,26.372,32.619,37.677,41.695,44.835,47.284,49.198,50.655,51.754,52.577,53.198,53.707,54.098,54.441,53.688,48.835,41.139,33.196,26.172,20.332,15.605,11.862,8.952,6.696,4.927,3.545,2.478,1.669,1.077,0.654,0.353,0.119],"e_4":[1.098,1.112,1.124,1.126,1.133,1.151,4.539,19.165,36.915,52.02,63.872,73.068,79.9,84.681,87.918,90.049,91.349,92.055,92.327,92.27,92.034,91.7,91.193,90.441,82.272,63.931,46.12,31.779,20.793,12.573,6.465,1.964,-1.317,-3.684,-5.411,-6.638,-7.46,-7.947,-8.165,-8.194,-8.106,-7.984],"a_5":[1.159,1.171,1.18,1.181,1.184,1.192,1.72,6.331,14.903,23.919,31.797,37.878,42.459,45.973,48.622,50.623,52.149,53.23,53.961,54.455,54.793,55.059,55.229,55.377,54.199,48.252,39.637,31.28,24.202,18.502,14.013,10.54,7.882,5.852,4.289,3.074,2.139,1.438,0.938,0.595,0.357,0.164],"b_5":[1.474,1.49,1.499,1.5,1.505,1.515,1.754,3.978,8.58,13.898,19.014,23.568,27.232,30.12,32.408,34.262,35.784,36.951,37.879,38.596,39.188,39.706,40.123,40.575,40.363,37.673,33.024,28.063,23.559,19.66,16.404,13.758,11.622,9.892,8.468,7.276,6.294,5.519,4.925,4.462,4.08,3.712],"c_5":[1.339,1.349,1.356,1.358,1.358,1.362,1.642,4.954,12.636,21.962,30.778,38.321,44.423,49.186,52.837,55.644,57.818,59.455,60.669,61.574,62.256,62.811,63.24,63.595,62.944,57.904,49.329,40.188,31.995,25.151,19.6,15.194,11.757,9.086,6.99,5.343,4.059,3.071,2.334,1.792,1.394,1.075],"d_5":[1.217,1.226,1.234,1.24,1.242,1.248,1.937,7.717,18.511,30.185,40.55,49.332,56.356,61.549,65.262,67.893,69.722,70.936,71.696,72.126,72.337,72.428,72.403,72.308,70.306,62.008,50.412,39.147,29.542,21.807,15.716,10.993,7.393,4.681,2.621,1.065,-0.092,-0.936,-1.517,-1.887,-2.115,-2.28],"e_5":[0.857,0.869,0.877,0.88,0.885,0.894,1.345,4.772,10.572,16.384,21.454,25.429,28.476,30.801,32.559,33.912,34.987,35.714,36.186,36.506,36.755,36.969,37.107,37.239,36.337,32.102,26.339,20.939,16.416,12.745,9.833,7.582,5.839,4.49,3.44,2.599,1.929,1.422,1.07,0.83,0.66,0.5],"a_6":[1.186,1.2,1.211,1.215,1.217,1.223,2.28,9.514,20.853,31.883,41.228,48.698,54.467,58.7,61.767,63.994,65.575,66.671,67.416,67.885,68.194,68.417,68.54,68.579,66.554,58.404,47.753,37.868,29.66,23.149,18.097,14.139,11.086,8.746,6.925,5.497,4.385,3.538,2.915,2.467,2.132,1.834],"b_6":[1.313,1.34,1.364,1.379,1.385,1.394,2.33,9.174,20.82,32.883,43.223,52.881,61.005,66.937,71.095,73.961,75.824,77.049,77.798,78.192,78.351,78.37,78.276,78.026,75.462,65.869,53.192,41.188,31.087,23.065,16.858,12.022,8.351,5.574,3.418,1.775,0.547,-0.343,-0.952,-1.366,-1.634,-1.809],"c_6":[1.052,1.068,1.08,1.086,1.088,1.093,1.961,7.84,17.108,26.177,33.757,39.676,44.258,47.688,50.214,52.064,53.357,54.291,54.955,55.379,55.671,55.877,56.003,56.023,54.558,48.439,40.155,32.292,25.692,20.456,16.4,13.217,10.765,8.879,7.388,6.207,5.273,4.545,3.991,3.567,3.229,2.937],"d_6":[1.326,1.343,1.359,1.37,1.374,1.384,2.412,9.673,21.801,34.324,45.222,54.601,62.159,67.741,71.702,74.456,76.282,77.448,78.143,78.471,78.583,78.576,78.457,78.223,75.919,67.098,55.054,43.374,33.374,25.307,18.984,14.0,10.171,7.266,5.033,3.327,2.041,1.088,0.411,-0.052,-0.369,-0.608],"e_6":[1.193,1.215,1.231,1.239,1.242,1.247,1.8,5.596,12.079,19.009,25.34,31.358,36.494,40.39,43.241,45.267,46.634,47.575,48.184,48.531,48.71,48.761,48.704,48.579,47.185,42.165,35.303,28.536,22.594,17.678,13.755,10.629,8.206,6.3,4.753,3.525,2.568,1.856,1.337,0.949,0.665,0.439],"a_7":[1.051,1.062,1.071,1.075,1.078,1.084,1.801,7.531,17.421,27.372,35.885,42.426,47.295,50.967,53.709,55.76,57.29,58.382,59.141,59.655,60.013,60.293,60.475,60.678,59.097,51.985,42.319,33.243,25.702,19.646,14.904,11.24,8.438,6.312,4.667,3.386,2.405,1.667,1.136,0.77,0.508,0.29],"b_7":[1.009,1.024,1.038,1.048,1.05,1.055,1.464,4.99,11.656,18.929,25.576,31.525,36.608,40.53,43.44,45.584,47.121,48.252,49.078,49.655,50.068,50.375,50.596,50.732,49.912,45.505,38.777,31.903,25.848,20.815,16.767,13.551,11.034,9.076,7.504,6.247,5.251,4.465,3.858,3.383,3.003,2.697],"c_7":[0.995,1.01,1.024,1.033,1.036,1.044,1.995,8.238,18.138,27.883,36.31,43.379,49.048,53.253,56.249,58.331,59.687,60.564,61.074,61.303,61.355,61.301,61.148,60.901,58.561,50.57,40.512,31.172,23.376,17.137,12.262,8.486,5.617,3.461,1.8,0.544,-0.382,-1.046,-1.491,-1.779,-1.957,-2.068]};
</script>
<script>
const SENSOR_KEYS = Object.keys(COORDS);

// Canvas setup
const SANDBOX_W = 15, SANDBOX_H = 24;
const SCALE = 22; // pixels per inch
const PAD = 18;
const CW = Math.round(SANDBOX_W * SCALE) + PAD*2;
const CH = Math.round(SANDBOX_H * SCALE) + PAD*2;

const heatCanvas = document.getElementById('heatmap');
const overlayCanvas = document.getElementById('overlay');
heatCanvas.width = overlayCanvas.width = CW;
heatCanvas.height = overlayCanvas.height = CH;

const hCtx = heatCanvas.getContext('2d');
const oCtx = overlayCanvas.getContext('2d');

// Mote colors for overlay
const MOTE_COLORS = {2:'#00d4ff',3:'#7affb0',4:'#ffd600',5:'#ff6b35',6:'#c97bff',7:'#ff4d8f'};

let currentMode = 'spike';
let activeMote = 'all';
let sliderIdx = 0;

function toCanvasX(x) { return PAD + x * SCALE; }
function toCanvasY(y) { return CH - PAD - y * SCALE; }

function valueToColor(norm, alpha=0.85) {
  // Deep blue -> cyan -> yellow -> red
  norm = Math.max(0, Math.min(1, norm));
  let r, g, b;
  if (norm < 0.25) {
    const t = norm / 0.25;
    r = Math.round(0 + t*0); g = Math.round(20 + t*180); b = Math.round(80 + t*175);
  } else if (norm < 0.5) {
    const t = (norm - 0.25) / 0.25;
    r = Math.round(0 + t*20); g = Math.round(200 + t*55); b = Math.round(255 - t*255);
  } else if (norm < 0.75) {
    const t = (norm - 0.5) / 0.25;
    r = Math.round(20 + t*235); g = Math.round(255 - t*50); b = Math.round(0);
  } else {
    const t = (norm - 0.75) / 0.25;
    r = Math.round(255); g = Math.round(205 - t*205); b = Math.round(0);
  }
  return `rgba(${r},${g},${b},${alpha})`;
}

// Fixed color scale: -10 to 110 W/m²
const SCALE_MIN = -10;
const SCALE_MAX = 110;

function drawHeatmap(values) {
  const minV = SCALE_MIN;
  const maxV = SCALE_MAX;

  hCtx.clearRect(0, 0, CW, CH);
  hCtx.fillStyle = '#0d1520';
  hCtx.fillRect(0, 0, CW, CH);

  // Draw sandbox outline
  hCtx.strokeStyle = '#1e2d3d';
  hCtx.lineWidth = 1;
  hCtx.strokeRect(PAD, PAD, SANDBOX_W*SCALE, SANDBOX_H*SCALE);

  // Grid lines
  hCtx.strokeStyle = 'rgba(30,45,61,0.4)';
  hCtx.lineWidth = 0.5;
  for (let x = 0; x <= SANDBOX_W; x += 3) {
    hCtx.beginPath();
    hCtx.moveTo(toCanvasX(x), PAD);
    hCtx.lineTo(toCanvasX(x), CH-PAD);
    hCtx.stroke();
  }
  for (let y = 0; y <= SANDBOX_H; y += 4) {
    hCtx.beginPath();
    hCtx.moveTo(PAD, toCanvasY(y));
    hCtx.lineTo(CW-PAD, toCanvasY(y));
    hCtx.stroke();
  }

  // RBF interpolation heatmap
  const imgData = hCtx.getImageData(PAD, PAD, SANDBOX_W*SCALE, SANDBOX_H*SCALE);
  const data = imgData.data;

  const sensors = SENSOR_KEYS
    .filter(k => activeMote === 'all' || k.endsWith('_'+activeMote))
    .map(k => ({
      cx: toCanvasX(COORDS[k][0]) - PAD,
      cy: toCanvasY(COORDS[k][1]) - PAD,
      v: values[k] || 0
    }));

  const sigma2 = (SCALE * 3.5) ** 2;

  for (let py = 0; py < SANDBOX_H*SCALE; py++) {
    for (let px = 0; px < SANDBOX_W*SCALE; px++) {
      let wsum = 0, vsum = 0;
      for (const s of sensors) {
        const d2 = (px-s.cx)**2 + (py-s.cy)**2;
        const w = Math.exp(-d2 / sigma2);
        wsum += w;
        vsum += w * s.v;
      }
      const interp = wsum > 0 ? vsum / wsum : 0;
      const norm = Math.max(0, Math.min(1, (interp - SCALE_MIN) / (SCALE_MAX - SCALE_MIN)));

      let r, g, b;
      const n = Math.max(0, Math.min(1, norm));
      if (n < 0.25) { const t=n/0.25; r=0; g=Math.round(20+t*180); b=Math.round(80+t*175); }
      else if (n < 0.5) { const t=(n-0.25)/0.25; r=Math.round(t*20); g=Math.round(200+t*55); b=Math.round(255-t*255); }
      else if (n < 0.75) { const t=(n-0.5)/0.25; r=Math.round(20+t*235); g=Math.round(255-t*50); b=0; }
      else { const t=(n-0.75)/0.25; r=255; g=Math.round(205-t*205); b=0; }

      const idx = (py * SANDBOX_W*SCALE + px) * 4;
      data[idx] = r; data[idx+1] = g; data[idx+2] = b; data[idx+3] = 200;
    }
  }
  hCtx.putImageData(imgData, PAD, PAD);

  // Update legend (always fixed scale)
  updateLegend(SCALE_MIN, SCALE_MAX);
  return { minV, maxV };
}

function drawOverlay(values) {
  oCtx.clearRect(0, 0, CW, CH);

  // Always draw ALL sensor locations regardless of value
  SENSOR_KEYS.forEach(k => {
    if (activeMote !== 'all' && !k.endsWith('_'+activeMote)) return;
    const [x, y] = COORDS[k];
    const cx = toCanvasX(x);
    const cy = toCanvasY(y);
    const mote = k.split('_')[1];
    const color = MOTE_COLORS[mote] || '#fff';
    const v = values[k];

    // Normalize using fixed scale, clamp to [0,1]
    const norm = Math.max(0, Math.min(1, (v - SCALE_MIN) / (SCALE_MAX - SCALE_MIN)));
    // Radius always >= 6 so arc never gets negative value
    const r = Math.max(6, 6 + norm * 6);

    // Outer ring
    oCtx.globalAlpha = 0.5;
    oCtx.beginPath();
    oCtx.arc(cx, cy, r + 2, 0, Math.PI * 2);
    oCtx.strokeStyle = color;
    oCtx.lineWidth = 1;
    oCtx.stroke();

    // Dot
    oCtx.globalAlpha = 0.9;
    oCtx.beginPath();
    oCtx.arc(cx, cy, r, 0, Math.PI * 2);
    oCtx.fillStyle = color;
    oCtx.fill();

    // Label
    oCtx.globalAlpha = 1;
    const letter = k.split('_')[0].toUpperCase();
    oCtx.fillStyle = '#0a0e14';
    oCtx.font = `bold ${Math.round(r * 1.1)}px Share Tech Mono, monospace`;
    oCtx.textAlign = 'center';
    oCtx.textBaseline = 'middle';
    oCtx.fillText(letter, cx, cy);
  });

  // Axis labels
  oCtx.fillStyle = '#2a3d50';
  oCtx.font = '9px Share Tech Mono, monospace';
  oCtx.textAlign = 'center';
  for (let x = 0; x <= SANDBOX_W; x += 5) {
    oCtx.fillText(x+'"', toCanvasX(x), CH-4);
  }
  oCtx.textAlign = 'right';
  for (let y = 0; y <= SANDBOX_H; y += 6) {
    oCtx.fillText(y+'"', PAD-3, toCanvasY(y)+4);
  }
}

function updateLegend(minV, maxV) {
  const lc = document.getElementById('legend-canvas');
  const lCtx = lc.getContext('2d');
  const grad = lCtx.createLinearGradient(0,0,140,0);
  grad.addColorStop(0, 'rgba(0,80,150,1)');
  grad.addColorStop(0.25, 'rgba(0,210,255,1)');
  grad.addColorStop(0.5, 'rgba(20,255,0,1)');
  grad.addColorStop(0.75, 'rgba(255,205,0,1)');
  grad.addColorStop(1, 'rgba(255,0,0,1)');
  lCtx.fillStyle = grad;
  lCtx.fillRect(0,0,140,10);
  document.getElementById('legend-range').textContent = `${minV.toFixed(1)}–${maxV.toFixed(1)} W/m²`;
}

function getCurrentValues() {
  if (currentMode === 'spike') return SPIKE_MAX;
  if (currentMode === 'baseline') return BASELINE;
  // timeline: build snapshot at sliderIdx
  const snap = {};
  SENSOR_KEYS.forEach(k => {
    const arr = TS_VALS[k];
    snap[k] = arr ? arr[sliderIdx] : null;
  });
  return snap;
}

function render(values) {
  drawHeatmap(values);
  drawOverlay(values);
  updateTable(values);
}

function setMode(mode) {
  currentMode = mode;
  document.querySelectorAll('.btn').forEach(b => b.classList.remove('active'));
  document.getElementById('btn-'+mode).classList.add('active');
  document.getElementById('timeline-ctrl').style.display = mode === 'timeline' ? 'flex' : 'none';

  const titles = {spike:'Spike Peak Values — Mar 5 (W/m²)', baseline:'Baseline Mean — Mar 7 (W/m²)', timeline:`Mar 6 · ${TS_TIMES[sliderIdx].split(' ')[1]} · 10-min avg (W/m²)`};
  document.getElementById('table-title').textContent = titles[mode];

  if (mode === 'spike') render(SPIKE_MAX);
  else if (mode === 'baseline') render(BASELINE);
  else { render(getCurrentValues()); }
}

function toggleMote(mote, el) {
  activeMote = mote;
  document.querySelectorAll('.mote-btn').forEach(b => b.classList.remove('active'));
  el.classList.add('active');
  render(getCurrentValues());
}

function onSlider(idx) {
  sliderIdx = parseInt(idx);
  const timeStr = TS_TIMES[sliderIdx] ? TS_TIMES[sliderIdx].split(' ')[1] : '--:--';
  document.getElementById('time-display').textContent = timeStr;
  document.getElementById('table-title').textContent = `Mar 6 · ${timeStr} · 10-min avg (W/m²)`;
  render(getCurrentValues());
}

function updateTable(values) {
  const tbody = document.getElementById('table-body');
  const entries = SENSOR_KEYS
    .filter(k => activeMote === 'all' || k.endsWith('_'+activeMote))
    .map(k => ({ key: k, val: values[k] }))
    .sort((a,b) => (b.val||0) - (a.val||0));

  const maxV = SCALE_MAX;

  tbody.innerHTML = entries.map(e => {
    const letter = e.key.split('_')[0].toUpperCase();
    const mote = e.key.split('_')[1];
    const color = MOTE_COLORS[mote] || '#fff';
    const norm = e.val != null ? Math.max(0, Math.min(1, (e.val - SCALE_MIN) / (SCALE_MAX - SCALE_MIN))) : 0;
    const pct = norm * 100;
    const barColor = valueToColor(norm);
    return `<tr>
      <td class="sensor-name" style="color:${color}">${letter}</td>
      <td style="color:${color}">M${mote}</td>
      <td class="val-cell">${e.val != null ? e.val.toFixed(2) : 'N/A'}</td>
      <td class="bar-cell"><div class="bar-bg"><div class="bar-fill" style="width:${pct}%;background:${barColor}"></div></div></td>
    </tr>`;
  }).join('');
}

// Tooltip on overlay canvas
overlayCanvas.style.pointerEvents = 'auto';
overlayCanvas.addEventListener('mousemove', (e) => {
  const rect = overlayCanvas.getBoundingClientRect();
  const mx = e.clientX - rect.left;
  const my = e.clientY - rect.top;
  const tip = document.getElementById('tooltip');
  const values = getCurrentValues();

  let closest = null, closestD = Infinity;
  SENSOR_KEYS.forEach(k => {
    if (activeMote !== 'all' && !k.endsWith('_'+activeMote)) return;
    const cx = toCanvasX(COORDS[k][0]);
    const cy = toCanvasY(COORDS[k][1]);
    const d = Math.sqrt((mx-cx)**2 + (my-cy)**2);
    if (d < closestD) { closestD = d; closest = k; }
  });

  if (closest && closestD < 18) {
    const letter = closest.split('_')[0].toUpperCase();
    const mote = closest.split('_')[1];
    const v = values[closest];
    tip.style.display = 'block';
    tip.style.left = (e.clientX + 14) + 'px';
    tip.style.top = (e.clientY - 10) + 'px';
    tip.innerHTML = `<span style="color:${MOTE_COLORS[mote]}">${letter}${mote}</span> · ${v != null ? v.toFixed(3) : 'N/A'} W/m²<br><span style="color:#4a6070;font-size:0.6rem">(${COORDS[closest][0]}", ${COORDS[closest][1]}")</span>`;
  } else {
    tip.style.display = 'none';
  }
});
overlayCanvas.addEventListener('mouseleave', () => {
  document.getElementById('tooltip').style.display = 'none';
});

// Init
render(SPIKE_MAX);
document.getElementById('time-slider').max = TS_TIMES.length - 1;
document.getElementById('time-slider').value = 0;
document.getElementById('time-display').textContent = TS_TIMES[0].split(' ')[1];
</script>
</body>
</html>
