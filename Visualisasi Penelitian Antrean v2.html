<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Dashboard Simulasi Antrean M/M/s</title>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.js"></script>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      font-family: 'Segoe UI', system-ui, sans-serif;
      background: #0f0f1a;
      color: #e2e8f0;
      min-height: 100vh;
      padding: 24px;
    }

    /* ── Hero ── */
    .hero {
      background: rgba(49,130,206,0.12);
      border: 1px solid rgba(99,179,237,0.2);
      border-radius: 14px;
      padding: 24px 30px;
      margin-bottom: 24px;
    }
    .hero-badge {
      display: inline-block;
      background: rgba(99,179,237,0.15);
      border: 1px solid rgba(99,179,237,0.35);
      border-radius: 20px;
      padding: 3px 14px;
      font-size: 11px;
      color: #63b3ed;
      font-weight: 600;
      letter-spacing: .08em;
      text-transform: uppercase;
      margin-bottom: 10px;
    }
    .hero h1 { font-size: 1.7rem; font-weight: 800; color: #fff; letter-spacing: -.02em; margin-bottom: 6px; }
    .hero p  { font-size: 13px; color: #90cdf4; }

    /* ── Params ── */
    .params {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 12px;
      margin-bottom: 20px;
    }
    .param-card {
      background: rgba(255,255,255,0.05);
      border: 1px solid rgba(255,255,255,0.08);
      border-radius: 12px;
      padding: 14px 16px;
    }
    .param-sym  { font-family: 'Courier New', monospace; font-size: 11px; color: #718096; margin-bottom: 3px; }
    .param-label{ font-size: 12px; color: #90cdf4; font-weight: 600; margin-bottom: 8px; }
    .param-row  { display: flex; align-items: center; gap: 8px; }
    .param-row input[type=range] { flex: 1; accent-color: #63b3ed; }
    .param-val  { font-family: 'Courier New', monospace; font-size: 15px; font-weight: 700; color: #fff; min-width: 26px; text-align: right; }
    .param-unit { font-size: 11px; color: #718096; }

    /* ── Unstable warning ── */
    .unstable {
      display: none;
      background: rgba(252,129,129,0.1);
      border: 1px solid rgba(252,129,129,0.3);
      border-radius: 10px;
      padding: 12px 16px;
      color: #fc8181;
      font-size: 13px;
      margin-bottom: 20px;
    }

    /* ── Metrics ── */
    .metrics {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 10px;
      margin-bottom: 20px;
    }
    .mc {
      background: rgba(255,255,255,0.04);
      border: 1px solid rgba(255,255,255,0.08);
      border-top: 2px solid #185FA5;
      border-radius: 12px;
      padding: 14px 16px;
      transition: border-color .2s;
    }
    .mc.green { border-top-color: #48bb78; }
    .mc.amber { border-top-color: #f6ad55; }
    .mc.red   { border-top-color: #fc8181; }
    .mc.blue  { border-top-color: #63b3ed; }
    .mc-lbl  { font-size: 10px; color: #a0aec0; text-transform: uppercase; letter-spacing: .08em; margin-bottom: 4px; }
    .mc-sym  { font-family: 'Courier New', monospace; font-size: 11px; color: #718096; margin-bottom: 2px; }
    .mc-val  { font-family: 'Courier New', monospace; font-size: 22px; font-weight: 700; color: #fff; line-height: 1.1; }
    .mc-unit { font-size: 11px; color: #718096; margin-top: 2px; }
    .mc-badge {
      display: inline-block; font-size: 10px; font-weight: 700;
      padding: 2px 8px; border-radius: 20px; margin-top: 5px;
      letter-spacing: .04em;
    }
    .badge-green { background: rgba(72,187,120,.15); color: #68d391; }
    .badge-amber { background: rgba(246,173,85,.15);  color: #f6ad55; }
    .badge-red   { background: rgba(252,129,129,.15); color: #fc8181; }
    .badge-blue  { background: rgba(99,179,237,.15);  color: #63b3ed; }

    /* ── Charts ── */
    .charts {
      display: grid;
      grid-template-columns: 3fr 2fr;
      gap: 14px;
      margin-bottom: 20px;
    }
    .chart-card {
      background: rgba(255,255,255,0.04);
      border: 1px solid rgba(255,255,255,0.08);
      border-radius: 12px;
      padding: 16px;
    }
    .chart-title { font-size: 13px; font-weight: 600; color: #e2e8f0; margin-bottom: 10px; }
    .legend { display: flex; gap: 14px; flex-wrap: wrap; margin-bottom: 8px; font-size: 11px; color: #a0aec0; }
    .legend span { display: flex; align-items: center; gap: 5px; }
    .leg-dot { width: 10px; height: 10px; border-radius: 2px; flex-shrink: 0; }

    /* ── Analysis ── */
    .analysis {
      border-radius: 12px;
      padding: 16px 20px;
      border: 1px solid;
    }
    .analysis.good { background: rgba(72,187,120,.07);  border-color: rgba(72,187,120,.25); }
    .analysis.warn { background: rgba(246,173,85,.07);  border-color: rgba(246,173,85,.25); }
    .analysis.bad  { background: rgba(252,129,129,.07); border-color: rgba(252,129,129,.25); }
    .analysis-title { font-size: 13px; font-weight: 700; margin-bottom: 6px; }
    .analysis.good .analysis-title { color: #68d391; }
    .analysis.warn .analysis-title { color: #f6ad55; }
    .analysis.bad  .analysis-title { color: #fc8181; }
    .analysis-body { font-size: 13px; color: #cbd5e0; line-height: 1.7; }

    /* ── Footer ── */
    footer { text-align: center; font-size: 11px; color: #4a5568; margin-top: 24px; }

    @media (max-width: 700px) {
      .params  { grid-template-columns: 1fr; }
      .metrics { grid-template-columns: repeat(2, 1fr); }
      .charts  { grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>

  <!-- HERO -->
  <div class="hero">
    <div class="hero-badge">🍽️ Riset Operasional · Restoran</div>
    <h1>Dashboard Simulasi Antrean M/M/s</h1>
    <p id="heroSub">Model Multi-Channel Single Phase · λ = 14 p/jam · μ = 15 p/jam · s = 3 staf</p>
  </div>

  <!-- PARAMS -->
  <div class="params">
    <div class="param-card">
      <div class="param-sym">λ (lambda)</div>
      <div class="param-label">Tingkat kedatangan</div>
      <div class="param-row">
        <input type="range" id="lam" min="5" max="50" value="14" step="1" oninput="update()">
        <span class="param-val" id="lamVal">14</span>
        <span class="param-unit">p/jam</span>
      </div>
    </div>
    <div class="param-card">
      <div class="param-sym">μ (mu)</div>
      <div class="param-label">Pelayanan per staf</div>
      <div class="param-row">
        <input type="range" id="mu" min="5" max="50" value="15" step="1" oninput="update()">
        <span class="param-val" id="muVal">15</span>
        <span class="param-unit">p/jam</span>
      </div>
    </div>
    <div class="param-card">
      <div class="param-sym">s (server)</div>
      <div class="param-label">Jumlah staf aktif</div>
      <div class="param-row">
        <input type="range" id="s" min="1" max="5" value="3" step="1" oninput="update()">
        <span class="param-val" id="sVal">3</span>
        <span class="param-unit">staf</span>
      </div>
    </div>
  </div>

  <!-- UNSTABLE -->
  <div class="unstable" id="unstableBox">
    ⚠️ Sistem tidak stabil (ρ ≥ 1). Kapasitas layanan lebih kecil dari kedatangan — antrean tidak terbatas. Tambah staf atau turunkan λ.
  </div>

  <!-- METRICS -->
  <div class="metrics" id="metricsGrid">
    <div class="mc blue" id="mc-rho">
      <div class="mc-lbl">Utilisasi staf</div>
      <div class="mc-sym">ρ</div>
      <div class="mc-val" id="v-rho">—</div>
      <div class="mc-unit">%</div>
      <span class="mc-badge badge-blue" id="b-rho">—</span>
    </div>
    <div class="mc blue" id="mc-p0">
      <div class="mc-lbl">Probabilitas sistem kosong</div>
      <div class="mc-sym">P₀</div>
      <div class="mc-val" id="v-p0">—</div>
      <div class="mc-unit">%</div>
      <span class="mc-badge badge-blue" id="b-p0">—</span>
    </div>
    <div class="mc blue" id="mc-lq">
      <div class="mc-lbl">Pesanan dalam antrean</div>
      <div class="mc-sym">Lq</div>
      <div class="mc-val" id="v-lq">—</div>
      <div class="mc-unit">pesanan</div>
      <span class="mc-badge badge-blue" id="b-lq">—</span>
    </div>
    <div class="mc blue" id="mc-ls">
      <div class="mc-lbl">Pesanan dalam sistem</div>
      <div class="mc-sym">Ls</div>
      <div class="mc-val" id="v-ls">—</div>
      <div class="mc-unit">pesanan</div>
      <span class="mc-badge badge-blue" id="b-ls">—</span>
    </div>
    <div class="mc blue" id="mc-wq">
      <div class="mc-lbl">Waktu tunggu antrean</div>
      <div class="mc-sym">Wq</div>
      <div class="mc-val" id="v-wq">—</div>
      <div class="mc-unit">menit</div>
      <span class="mc-badge badge-blue" id="b-wq">—</span>
    </div>
    <div class="mc blue" id="mc-ws">
      <div class="mc-lbl">Waktu total dalam sistem</div>
      <div class="mc-sym">Ws</div>
      <div class="mc-val" id="v-ws">—</div>
      <div class="mc-unit">menit</div>
      <span class="mc-badge badge-blue" id="b-ws">—</span>
    </div>
  </div>

  <!-- CHARTS -->
  <div class="charts">
    <div class="chart-card">
      <div class="chart-title">Pengaruh jumlah staf terhadap waktu tunggu (Wq)</div>
      <div class="legend">
        <span><span class="leg-dot" style="background:#fc8181;"></span>s = 1 staf</span>
        <span><span class="leg-dot" style="background:#f6ad55;"></span>s = 2 staf</span>
        <span><span class="leg-dot" style="background:#68d391;"></span>s = 3 staf</span>
        <span><span class="leg-dot" style="background:#63b3ed;border:1px dashed #63b3ed;"></span>λ saat ini</span>
      </div>
      <div style="position:relative;width:100%;height:240px;">
        <canvas id="chartWq"></canvas>
      </div>
    </div>
    <div class="chart-card">
      <div class="chart-title">Distribusi waktu staf (utilisasi vs idle)</div>
      <div style="position:relative;width:100%;height:270px;">
        <canvas id="chartUtil"></canvas>
      </div>
    </div>
  </div>

  <!-- ANALYSIS -->
  <div class="analysis good" id="analysisBox">
    <div class="analysis-title" id="analysisTitle">—</div>
    <p class="analysis-body" id="analysisBody">—</p>
  </div>

  <footer>Dashboard Simulasi Antrean M/M/s · Riset Operasional Restoran</footer>

  <script>
    function factorial(n) {
      let r = 1;
      for (let i = 2; i <= n; i++) r *= i;
      return r;
    }

    function calcMMS(lam, mu, s) {
      const rho = lam / (s * mu);
      if (rho >= 1) return null;
      const a = lam / mu;
      let sum = 0;
      for (let n = 0; n < s; n++) sum += Math.pow(a, n) / factorial(n);
      const P0 = 1 / (sum + Math.pow(a, s) / (factorial(s) * (1 - rho)));
      const Lq = P0 * Math.pow(a, s) * rho / (factorial(s) * Math.pow(1 - rho, 2));
      const Ls = Lq + a;
      const Wq = (Lq / lam) * 60;
      const Ws = Wq + (1 / mu) * 60;
      return { rho, P0, Lq, Ls, Wq, Ws };
    }

    // ── Init Charts ──────────────────────────────
    const gridColor = 'rgba(255,255,255,0.07)';
    const tickColor = 'rgba(255,255,255,0.4)';

    const chartWq = new Chart(document.getElementById('chartWq'), {
      type: 'line',
      data: {
        labels: [],
        datasets: [
          { label: 's=1', data: [], borderColor: '#fc8181', backgroundColor: 'transparent', borderWidth: 2, pointRadius: 0 },
          { label: 's=2', data: [], borderColor: '#f6ad55', backgroundColor: 'transparent', borderWidth: 2, pointRadius: 0, borderDash: [5,3] },
          { label: 's=3', data: [], borderColor: '#68d391', backgroundColor: 'transparent', borderWidth: 2, pointRadius: 0 },
          { label: 'λ saat ini', data: [], borderColor: '#63b3ed', backgroundColor: 'transparent', borderWidth: 1.5, pointRadius: 0, borderDash: [3,3] },
        ]
      },
      options: {
        responsive: true, maintainAspectRatio: false,
        plugins: { legend: { display: false } },
        scales: {
          x: { grid: { color: gridColor }, ticks: { color: tickColor, font: { size: 11 } }, title: { display: true, text: 'λ (pesanan/jam)', color: tickColor, font: { size: 11 } } },
          y: { grid: { color: gridColor }, ticks: { color: tickColor, font: { size: 11 } }, title: { display: true, text: 'Wq (menit)', color: tickColor, font: { size: 11 } }, beginAtZero: true }
        }
      }
    });

    const chartUtil = new Chart(document.getElementById('chartUtil'), {
      type: 'bar',
      data: {
        labels: ['Sibuk', 'Idle'],
        datasets: [{ data: [70, 30], backgroundColor: ['#68d391', '#4299e1'], borderRadius: 6, borderSkipped: false }]
      },
      options: {
        responsive: true, maintainAspectRatio: false,
        plugins: { legend: { display: false } },
        scales: {
          x: { grid: { display: false }, ticks: { color: tickColor, font: { size: 12 } } },
          y: { grid: { color: gridColor }, ticks: { color: tickColor, font: { size: 11 }, callback: v => v + '%' }, max: 100, beginAtZero: true }
        }
      }
    });

    // ── Helpers ──────────────────────────────────
    function setMetric(id, colorClass, val, badge, badgeClass) {
      document.getElementById('mc-' + id).className = 'mc ' + colorClass;
      document.getElementById('v-' + id).textContent = val;
      const b = document.getElementById('b-' + id);
      b.textContent = badge;
      b.className = 'mc-badge badge-' + badgeClass;
    }

    // ── Main update ───────────────────────────────
    function update() {
      const lam = +document.getElementById('lam').value;
      const mu  = +document.getElementById('mu').value;
      const s   = +document.getElementById('s').value;

      document.getElementById('lamVal').textContent = lam;
      document.getElementById('muVal').textContent  = mu;
      document.getElementById('sVal').textContent   = s;
      document.getElementById('heroSub').textContent =
        `Model Multi-Channel Single Phase · λ = ${lam} p/jam · μ = ${mu} p/jam · s = ${s} staf`;

      const r = calcMMS(lam, mu, s);
      const unstable  = document.getElementById('unstableBox');
      const metrics   = document.getElementById('metricsGrid');
      const analysisEl = document.getElementById('analysisBox');

      if (!r) {
        unstable.style.display = 'block';
        metrics.style.opacity  = '0.3';
        analysisEl.style.display = 'none';
        return;
      }
      unstable.style.display   = 'none';
      metrics.style.opacity    = '1';
      analysisEl.style.display = 'block';

      // Metric values
      const rhoP = (r.rho * 100).toFixed(1);
      const p0P  = (r.P0  * 100).toFixed(1);
      const lqV  = r.Lq.toFixed(2);
      const lsV  = r.Ls.toFixed(2);
      const wqV  = r.Wq.toFixed(2);
      const wsV  = r.Ws.toFixed(2);

      let rhoC, rhoB, rhoBc;
      if (+rhoP >= 80)      { rhoC = 'red';   rhoB = 'SIBUK';   rhoBc = 'red'; }
      else if (+rhoP >= 50) { rhoC = 'green'; rhoB = 'OPTIMAL'; rhoBc = 'green'; }
      else                  { rhoC = 'amber'; rhoB = 'IDLE';    rhoBc = 'amber'; }

      setMetric('rho', rhoC,  rhoP, rhoB,                 rhoBc);
      setMetric('p0',  'blue', p0P, p0P + '% waktu',      'blue');

      const lqC = r.Lq < 2 ? 'green' : r.Lq >= 5 ? 'red' : 'amber';
      const lqB = r.Lq < 2 ? 'BAIK'  : r.Lq >= 5 ? 'PADAT' : 'SEDANG';
      setMetric('lq', lqC,   lqV, lqB,                   lqC);
      setMetric('ls', 'blue', lsV, 'Total: ' + lsV,       'blue');

      const wqC = r.Wq < 5 ? 'green' : r.Wq >= 15 ? 'red' : 'amber';
      const wqB = r.Wq < 5 ? 'CEPAT' : r.Wq >= 15 ? 'LAMBAT' : 'SEDANG';
      setMetric('wq', wqC,   wqV, wqB,                   wqC);
      setMetric('ws', 'blue', wsV, 'Termasuk layanan',    'blue');

      // Chart 1: Wq vs lambda for s=1,2,3
      const maxL = Math.min(mu * s - 0.5, 49.5);
      const labels = [];
      for (let l = 5; l < maxL; l += 0.5) labels.push(+l.toFixed(1));
      const d1 = [], d2 = [], d3 = [];
      labels.forEach(l => {
        const r1 = calcMMS(l, mu, 1); d1.push(r1 ? +r1.Wq.toFixed(3) : null);
        const r2 = calcMMS(l, mu, 2); d2.push(r2 ? +r2.Wq.toFixed(3) : null);
        const r3 = calcMMS(l, mu, 3); d3.push(r3 ? +r3.Wq.toFixed(3) : null);
      });
      const maxWq = Math.max(...[...d1, ...d2, ...d3].filter(x => x !== null), 1);
      const vLine = labels.map(l => Math.abs(l - lam) < 0.27 ? maxWq * 1.05 : null);

      chartWq.data.labels         = labels;
      chartWq.data.datasets[0].data = d1;
      chartWq.data.datasets[1].data = d2;
      chartWq.data.datasets[2].data = d3;
      chartWq.data.datasets[3].data = vLine;
      chartWq.update('none');

      // Chart 2: Busy vs Idle
      const busy = +rhoP;
      const idle = +(100 - busy).toFixed(1);
      const bColor = +rhoP >= 80 ? '#fc8181' : +rhoP >= 50 ? '#68d391' : '#f6ad55';
      chartUtil.data.datasets[0].data            = [busy, idle];
      chartUtil.data.datasets[0].backgroundColor = [bColor, '#4299e1'];
      chartUtil.update('none');

      // Analysis text
      const idleP = (100 - +rhoP).toFixed(1);
      let boxCls, title, body;
      if (+rhoP >= 80) {
        boxCls = 'bad';
        title  = '🔴 Sistem terlalu sibuk — risiko kepuasan pelanggan menurun';
        body   = `Utilisasi ${rhoP}% mendekati kapasitas penuh. Waktu tunggu rata-rata ${wqV} menit sebelum dilayani, total ${wsV} menit dalam sistem. Ada rata-rata ${lqV} pesanan mengantre setiap saat. Pertimbangkan penambahan staf ke ${s+1} jalur, terutama di jam sibuk.`;
      } else if (+rhoP < 50) {
        boxCls = 'warn';
        title  = '🟡 Utilisasi rendah — potensi pemborosan biaya tenaga kerja';
        body   = `Staf idle selama ${idleP}% waktu kerja. Dengan ${s} staf dan λ = ${lam} p/jam, sistem sangat longgar — pelanggan hanya menunggu ${wqV} menit. Pada jam sepi, pertimbangkan mengurangi staf aktif menjadi ${Math.max(1,s-1)} jalur untuk menekan biaya operasional.`;
      } else {
        boxCls = 'good';
        title  = '🟢 Sistem beroperasi pada zona efisien';
        body   = `Utilisasi ${rhoP}% berada di zona optimal (50–80%). Staf cukup sibuk untuk membenarkan biaya tenaga kerja namun tidak overloaded. Pelanggan menunggu ${wqV} menit dalam antrean dan ${wsV} menit total. Konfigurasi ${s} staf dengan λ=${lam}, μ=${mu} merupakan titik keseimbangan yang baik.`;
      }
      analysisEl.className = 'analysis ' + boxCls;
      document.getElementById('analysisTitle').textContent = title;
      document.getElementById('analysisBody').textContent  = body;
    }

    update();
  </script>
</body>
</html>
