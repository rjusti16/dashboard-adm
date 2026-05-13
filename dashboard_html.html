<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0">
<title>Dashboard Gerencial — ADM do Brasil | Irmãos Passaúra</title>
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.js"></script>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
body{font-family:system-ui,-apple-system,sans-serif;background:#f0f2f5;color:#1a1a2e;min-height:100vh}
.wrap{max-width:1200px;margin:0 auto;padding:24px}
/* Header */
.hdr{background:#0f2d5c;color:#fff;padding:20px 28px;border-radius:12px;display:flex;justify-content:space-between;align-items:flex-start;flex-wrap:wrap;gap:12px;margin-bottom:20px}
.hdr-co{font-size:10px;font-weight:600;opacity:.65;text-transform:uppercase;letter-spacing:.05em;margin-bottom:4px}
.hdr h1{font-size:19px;font-weight:600;margin-bottom:3px}
.hdr-sub{font-size:12px;opacity:.65}
.hdr-r{text-align:right}
.hdr-date{font-size:12px;font-weight:500}
.hdr-author{font-size:10px;opacity:.6;margin-top:2px}
.btn-refresh{margin-top:8px;background:rgba(255,255,255,.15);border:1px solid rgba(255,255,255,.3);color:#fff;padding:5px 14px;border-radius:6px;font-size:11px;cursor:pointer;font-family:inherit}
.btn-refresh:hover{background:rgba(255,255,255,.25)}
.btn-refresh:disabled{opacity:.5;cursor:not-allowed}
/* KPIs */
.kpi-grid{display:grid;grid-template-columns:repeat(5,1fr);gap:12px;margin-bottom:20px}
.kpi{background:#fff;border-radius:10px;padding:16px 14px;border:1px solid #e8eaed;border-top:3px solid #e8eaed}
.kpi.g{border-top-color:#10b981}.kpi.r{border-top-color:#ef4444}.kpi.b{border-top-color:#0f2d5c}.kpi.n{border-top-color:#9ca3af}
.kpi-lbl{font-size:10px;font-weight:600;color:#6b7280;text-transform:uppercase;letter-spacing:.04em;margin-bottom:6px}
.kpi-val{font-size:22px;font-weight:600}
.kpi.g .kpi-val{color:#10b981}.kpi.r .kpi-val{color:#ef4444}.kpi.b .kpi-val{color:#0f2d5c}.kpi.n .kpi-val{color:#374151}
/* Cards */
.row2{display:grid;grid-template-columns:1fr 1fr;gap:16px;margin-bottom:20px}
.card{background:#fff;border-radius:10px;border:1px solid #e8eaed;padding:20px}
.card+.card-full{margin-top:0}
.card-full{background:#fff;border-radius:10px;border:1px solid #e8eaed;padding:20px;margin-bottom:20px}
.ct{font-size:13px;font-weight:600;color:#111;margin-bottom:16px}
/* Barras */
.pb-row{margin-bottom:12px}
.pb-lbl{display:flex;justify-content:space-between;font-size:11px;color:#6b7280;margin-bottom:4px}
.pb-track{height:10px;background:#f3f4f6;border-radius:5px;overflow:hidden}
.pb-fill{height:100%;border-radius:5px}
.status-box{margin-top:14px;padding:10px 14px;border-radius:8px;font-size:12px;font-weight:500}
.status-box.green{background:#d1fae5;color:#065f46}.status-box.red{background:#fee2e2;color:#991b1b}
/* Dev bars */
.dv-row{display:flex;align-items:center;gap:10px;margin-bottom:10px}
.dv-nm{font-size:11px;color:#374151;width:130px;flex-shrink:0}
.dv-track{flex:1;height:8px;background:#f3f4f6;border-radius:4px;overflow:hidden}
.dv-fill{height:100%;border-radius:4px}
.dv-cnt{font-size:11px;font-weight:600;color:#374151;width:22px;text-align:right;flex-shrink:0}
.dv-pct{font-size:10px;color:#9ca3af;width:32px;text-align:right;flex-shrink:0}
/* Legend */
.legend{display:flex;flex-wrap:wrap;gap:10px;margin-bottom:12px}
.leg{display:flex;align-items:center;gap:5px;font-size:10px;color:#6b7280}
.leg-dot{width:9px;height:9px;border-radius:2px;flex-shrink:0}
/* Table */
.tbl-wrap{overflow-x:auto}
table{width:100%;border-collapse:collapse;font-size:11.5px}
thead th{padding:8px 10px;text-align:left;color:#6b7280;font-weight:600;border-bottom:1px solid #e5e7eb;white-space:nowrap;background:#f9fafb;font-size:10.5px}
tbody td{padding:9px 10px;border-bottom:1px solid #f3f4f6;vertical-align:middle;color:#374151}
tbody tr:last-child td{border-bottom:none}
tbody tr:hover{background:#f9fafb}
.mono{font-family:monospace;font-size:10px;color:#6b7280}
.badge{display:inline-block;padding:2px 8px;border-radius:4px;font-size:10px;font-weight:700}
.bd{background:#fee2e2;color:#991b1b}.bw{background:#fef3c7;color:#92400e}.bg{background:#d1fae5;color:#065f46}
.td{color:#dc2626;font-weight:700}
/* Resumo */
.rs-grid{display:grid;grid-template-columns:1fr 1fr;gap:14px}
.rs-item{display:flex;gap:10px}
.rs-bar{width:3px;border-radius:2px;flex-shrink:0}
.rs-t{font-size:11px;font-weight:600;color:#111;margin-bottom:3px}
.rs-p{font-size:11px;color:#6b7280;line-height:1.5}
/* Util */
.loading{text-align:center;padding:80px;color:#6b7280;font-size:14px}
.err-box{background:#fff3cd;border:1px solid #ffc107;border-radius:10px;padding:20px;margin:16px 0;font-size:13px;color:#856404;line-height:1.7}
footer{text-align:center;padding:16px 0;font-size:10px;color:#9ca3af}
@media(max-width:800px){.kpi-grid{grid-template-columns:repeat(3,1fr)}.row2{grid-template-columns:1fr}.rs-grid{grid-template-columns:1fr}}
@media(max-width:480px){.kpi-grid{grid-template-columns:repeat(2,1fr)}}
</style>
</head>
<body>
<div class="wrap">
  <div id="app"><div class="loading">⏳ Carregando dados da planilha...</div></div>
</div>

<script>
// ╔══════════════════════════════════════════════════╗
//  CONFIGURAÇÃO — altere só estes valores se precisar
// ╠══════════════════════════════════════════════════╣
const SHEET_ID = '1TfQCzg_KcbPuJpI9tH1DVRJb-44f-39i';
const GID      = '775705987';   // aba: Relatório Gerencial
// ╚══════════════════════════════════════════════════╝

let chart = null;

// ─── Helpers ─────────────────────────────────────────
function cell(rows, r, c) {
  try { const v = rows[r]?.c?.[c]; return v?.v ?? v?.f ?? null; } catch { return null; }
}

function num(v, fallback = 0) {
  if (v == null) return fallback;
  if (typeof v === 'number') return v <= 1 && v >= 0 ? v * 100 : v;
  return parseFloat(String(v).replace(/[^0-9.\-]/g, '')) || fallback;
}

function fmtDate(v) {
  if (!v) return '—';
  if (typeof v === 'string' && v.includes('Date')) {
    const m = v.match(/Date\((\d+),(\d+),(\d+)/);
    if (m) return `${String(m[3]).padStart(2,'0')}/${String(+m[2]+1).padStart(2,'0')}`;
  }
  if (typeof v === 'string') {
    const p = v.slice(0,10).split('-');
    return p.length === 3 ? `${p[2]}/${p[1]}` : v.slice(0,5);
  }
  return String(v);
}

function badge(real) {
  if (real === 0) return 'bd';
  if (real < 50)  return 'bw';
  return 'bg';
}

// ─── Fetch ───────────────────────────────────────────
async function fetchRows() {
  const url = `https://docs.google.com/spreadsheets/d/${SHEET_ID}/gviz/tq?tqx=out:json&gid=${GID}`;
  const res  = await fetch(url, { cache: 'no-store' });
  const text = await res.text();
  const js   = text.match(/setResponse\(([\s\S]*?)\);?\s*$/)?.[1];
  if (!js) throw new Error('Formato inesperado na resposta do Google Sheets.');
  return JSON.parse(js).table.rows;
}

// ─── Build ───────────────────────────────────────────
function render(rows, ts) {
  // KPIs — row index 5 (planilha linha 6)
  const rPct  = num(cell(rows, 5, 1), 81.0);
  const pPct  = num(cell(rows, 5, 2), 76.7);
  const dPct  = num(cell(rows, 5, 3),  4.35);
  const totAc = cell(rows, 5, 4) ?? 72;
  const atrs  = cell(rows, 5, 5) ?? 27;
  const ahead = dPct >= 0;

  // Desvios — row indices 18–20
  const devs = [
    { nm: cell(rows,18,1) ?? 'ADM do Brasil',          qt: cell(rows,18,2) ?? 7,  cor:'#dc2626' },
    { nm: cell(rows,19,1) ?? 'Irmãos Passaúra',        qt: cell(rows,19,2) ?? 11, cor:'#2563eb' },
    { nm: cell(rows,20,1) ?? 'ADM + Irmãos Passaúra',  qt: cell(rows,20,2) ?? 1,  cor:'#9ca3af' },
  ];
  const totDv = devs.reduce((a,d) => a + Number(d.qt), 0) || 19;

  // Top 5 — row indices 32–36
  const top5 = [];
  for (let i = 32; i <= 36; i++) {
    if (!rows[i]) continue;
    top5.push({
      edt:  cell(rows,i,1), ativ: cell(rows,i,2),
      real: num(cell(rows,i,3)), prev: num(cell(rows,i,4)),
      dev:  num(cell(rows,i,5)), term: fmtDate(cell(rows,i,6)),
      area: cell(rows,i,7), resp: cell(rows,i,8), obs: cell(rows,i,9),
    });
  }

  // ── HTML ──
  document.getElementById('app').innerHTML = `
    <div class="hdr">
      <div>
        <div class="hdr-co">Irmãos Passaúra · ADM do Brasil · Uberlândia, MG</div>
        <h1>Relatório Gerencial — Montagem Mecânica</h1>
        <div class="hdr-sub">Área 25001 · Parada Geral · Preparação</div>
      </div>
      <div class="hdr-r">
        <div class="hdr-date">Atualizado: ${ts}</div>
        <div class="hdr-author">Raphael Justi Medeiros</div>
        <button class="btn-refresh" onclick="init()">↺ Atualizar</button>
      </div>
    </div>

    <div class="kpi-grid">
      <div class="kpi g"><div class="kpi-lbl">% Realizado</div><div class="kpi-val">${rPct.toFixed(1)}%</div></div>
      <div class="kpi n"><div class="kpi-lbl">% Previsto</div><div class="kpi-val">${pPct.toFixed(1)}%</div></div>
      <div class="kpi ${ahead?'g':'r'}"><div class="kpi-lbl">Desvio</div><div class="kpi-val">${ahead?'+':''}${dPct.toFixed(2)} p.p.</div></div>
      <div class="kpi b"><div class="kpi-lbl">Atividades</div><div class="kpi-val">${totAc}</div></div>
      <div class="kpi r"><div class="kpi-lbl">Atrasadas</div><div class="kpi-val">${atrs}</div></div>
    </div>

    <div class="row2">
      <div class="card">
        <div class="ct">Avanço físico</div>
        <div class="pb-row">
          <div class="pb-lbl"><span>Realizado</span><span>${rPct.toFixed(1)}%</span></div>
          <div class="pb-track"><div class="pb-fill" style="width:${rPct}%;background:#10b981"></div></div>
        </div>
        <div class="pb-row">
          <div class="pb-lbl"><span>Previsto</span><span>${pPct.toFixed(1)}%</span></div>
          <div class="pb-track"><div class="pb-fill" style="width:${pPct}%;background:#9ca3af"></div></div>
        </div>
        <div class="status-box ${ahead?'green':'red'}">
          ${ahead?'✔ Projeto adiantado':'⚠ Projeto atrasado'} — ${ahead?'+':''}${dPct.toFixed(2)} p.p. ${ahead?'acima':'abaixo'} do previsto
        </div>
        <div style="height:18px"></div>
        <div class="ct">Desvios por responsável</div>
        ${devs.map(d=>`
          <div class="dv-row">
            <div class="dv-nm">${d.nm}</div>
            <div class="dv-track"><div class="dv-fill" style="width:${Math.round(d.qt/totDv*100)}%;background:${d.cor}"></div></div>
            <div class="dv-cnt">${d.qt}</div>
            <div class="dv-pct">${Math.round(d.qt/totDv*100)}%</div>
          </div>`).join('')}
      </div>

      <div class="card">
        <div class="ct">Distribuição de desvios</div>
        <div class="legend">
          ${devs.map(d=>`<div class="leg"><div class="leg-dot" style="background:${d.cor}"></div>${d.nm} — ${Math.round(d.qt/totDv*100)}%</div>`).join('')}
        </div>
        <div style="position:relative;height:190px">
          <canvas id="donut" role="img" aria-label="Gráfico de desvios por responsável"></canvas>
        </div>
        <div style="margin-top:12px;padding:10px 14px;background:#fee2e2;border-radius:8px;font-size:12px;font-weight:600;color:#991b1b">
          Total: ${totDv} desvios identificados
        </div>
      </div>
    </div>

    <div class="card-full">
      <div class="ct">Top 5 — atividades críticas (maior desvio)</div>
      <div class="tbl-wrap">
        <table>
          <thead><tr>
            <th>EDT</th><th>Atividade</th>
            <th style="text-align:center">Real</th><th style="text-align:center">Prev.</th>
            <th style="text-align:center">Desvio</th><th style="text-align:center">Término</th>
            <th>Área</th><th>Responsável</th><th>Observação</th>
          </tr></thead>
          <tbody>
            ${top5.map(t=>`<tr>
              <td class="mono">${t.edt??'—'}</td>
              <td style="max-width:160px;color:#111">${t.ativ??'—'}</td>
              <td style="text-align:center"><span class="badge ${badge(t.real)}">${t.real.toFixed(0)}%</span></td>
              <td style="text-align:center">${t.prev.toFixed(0)}%</td>
              <td style="text-align:center" class="td">${t.dev.toFixed(0)}%</td>
              <td style="text-align:center">${t.term}</td>
              <td>${t.area??'—'}</td>
              <td>${t.resp??'—'}</td>
              <td>${t.obs??'—'}</td>
            </tr>`).join('')}
          </tbody>
        </table>
      </div>
    </div>

    <div class="card-full">
      <div class="ct">Resumo executivo</div>
      <div class="rs-grid">
        <div class="rs-item">
          <div class="rs-bar" style="background:#10b981;min-height:44px"></div>
          <div><div class="rs-t">Situação geral</div>
          <div class="rs-p">Avanço de ${rPct.toFixed(1)}%, superando em ${dPct.toFixed(1)} p.p. o previsto (${pPct.toFixed(1)}%). Projeto adiantado.</div></div>
        </div>
        <div class="rs-item">
          <div class="rs-bar" style="background:#ef4444;min-height:44px"></div>
          <div><div class="rs-t">Pontos de atenção</div>
          <div class="rs-p">${atrs} atividades atrasadas (${Math.round(atrs/totAc*100)}% do total) — 7 de responsabilidade da ADM do Brasil e 10 de Irmãos Passaúra.</div></div>
        </div>
        <div class="rs-item">
          <div class="rs-bar" style="background:#f59e0b;min-height:44px"></div>
          <div><div class="rs-t">Principais causas</div>
          <div class="rs-p">Aguardando adequação de piso/civil (ADM Brasil). Peças e materiais não entregues no site (Elevador 2531, correntes).</div></div>
        </div>
        <div class="rs-item">
          <div class="rs-bar" style="background:#2563eb;min-height:44px"></div>
          <div><div class="rs-t">Ação requerida</div>
          <div class="rs-p">Priorizar liberação de frentes civis, entrega do Elevador 2531 e materiais pendentes no site.</div></div>
        </div>
      </div>
    </div>

    <footer>Fonte: Cronograma ADM (MS Project) · Área 25001 — Ampliação Preparação Atual · Atualização automática via Google Sheets</footer>`;

  // Gráfico donut
  if (chart) chart.destroy();
  chart = new Chart(document.getElementById('donut'), {
    type: 'doughnut',
    data: {
      labels: devs.map(d => d.nm),
      datasets: [{ data: devs.map(d => d.qt), backgroundColor: devs.map(d => d.cor), borderWidth: 0, hoverOffset: 6 }]
    },
    options: {
      responsive: true, maintainAspectRatio: false, cutout: '66%',
      plugins: {
        legend: { display: false },
        tooltip: { callbacks: { label: c => ` ${c.label}: ${c.raw} desvios` } }
      }
    }
  });
}

function showError(msg) {
  const ts = new Date().toLocaleString('pt-BR',{day:'2-digit',month:'2-digit',year:'numeric',hour:'2-digit',minute:'2-digit'});
  document.getElementById('app').innerHTML = `
    <div class="hdr"><div><div class="hdr-co">Irmãos Passaúra · ADM do Brasil</div>
      <h1>Relatório Gerencial — Montagem Mecânica</h1></div>
      <div class="hdr-r"><div class="hdr-date">${ts}</div>
        <button class="btn-refresh" onclick="init()">↺ Tentar novamente</button></div></div>
    <div class="err-box">
      <strong>⚠ Não foi possível carregar os dados da planilha.</strong><br><br>
      Erro: ${msg}<br><br>
      <strong>Para resolver:</strong><br>
      1. Abra a planilha no Google Sheets<br>
      2. Clique em <strong>Compartilhar</strong> → <strong>Alterar para qualquer pessoa com o link</strong> → <strong>Leitor</strong><br>
      3. Salve e recarregue esta página
    </div>`;
}

async function init() {
  const btn = document.querySelector('.btn-refresh');
  if (btn) { btn.disabled = true; btn.textContent = '↺ Carregando...'; }
  const ts = new Date().toLocaleString('pt-BR',{day:'2-digit',month:'2-digit',year:'numeric',hour:'2-digit',minute:'2-digit'});
  try {
    const rows = await fetchRows();
    render(rows, ts);
  } catch(e) {
    showError(e.message);
  }
}

init();
</script>
</body>
</html>
