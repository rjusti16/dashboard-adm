
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
.hdr{background:#0f2d5c;color:#fff;padding:20px 28px;border-radius:12px;display:flex;justify-content:space-between;align-items:flex-start;flex-wrap:wrap;gap:12px;margin-bottom:20px}
.hdr-co{font-size:10px;font-weight:600;opacity:.65;text-transform:uppercase;letter-spacing:.05em;margin-bottom:4px}
.hdr h1{font-size:19px;font-weight:600;margin-bottom:3px}
.hdr-sub{font-size:12px;opacity:.65}
.hdr-r{text-align:right}
.hdr-date{font-size:12px;font-weight:500}
.hdr-author{font-size:10px;opacity:.6;margin-top:2px}
.btn-ref{margin-top:8px;background:rgba(255,255,255,.15);border:1px solid rgba(255,255,255,.3);color:#fff;padding:5px 14px;border-radius:6px;font-size:11px;cursor:pointer;font-family:inherit}
.btn-ref:hover{background:rgba(255,255,255,.25)}.btn-ref:disabled{opacity:.5;cursor:not-allowed}
.kpi-grid{display:grid;grid-template-columns:repeat(5,1fr);gap:12px;margin-bottom:20px}
.kpi{background:#fff;border-radius:10px;padding:16px 14px;border:1px solid #e8eaed;border-top:3px solid #e8eaed}
.kpi.g{border-top-color:#10b981}.kpi.r{border-top-color:#ef4444}.kpi.b{border-top-color:#0f2d5c}.kpi.n{border-top-color:#9ca3af}
.kpi-lbl{font-size:10px;font-weight:600;color:#6b7280;text-transform:uppercase;letter-spacing:.04em;margin-bottom:6px}
.kpi-val{font-size:22px;font-weight:600}
.kpi.g .kpi-val{color:#10b981}.kpi.r .kpi-val{color:#ef4444}.kpi.b .kpi-val{color:#0f2d5c}.kpi.n .kpi-val{color:#374151}
.row2{display:grid;grid-template-columns:1fr 1fr;gap:16px;margin-bottom:20px}
.card{background:#fff;border-radius:10px;border:1px solid #e8eaed;padding:20px}
.card-full{background:#fff;border-radius:10px;border:1px solid #e8eaed;padding:20px;margin-bottom:20px}
.ct{font-size:13px;font-weight:600;color:#111;margin-bottom:16px}
.pb-row{margin-bottom:12px}
.pb-lbl{display:flex;justify-content:space-between;font-size:11px;color:#6b7280;margin-bottom:4px}
.pb-track{height:10px;background:#f3f4f6;border-radius:5px;overflow:hidden}
.pb-fill{height:100%;border-radius:5px}
.st-box{margin-top:14px;padding:10px 14px;border-radius:8px;font-size:12px;font-weight:500}
.st-box.ok{background:#d1fae5;color:#065f46}.st-box.bad{background:#fee2e2;color:#991b1b}
.dv-row{display:flex;align-items:center;gap:10px;margin-bottom:10px}
.dv-nm{font-size:11px;color:#374151;width:140px;flex-shrink:0}
.dv-track{flex:1;height:8px;background:#f3f4f6;border-radius:4px;overflow:hidden}
.dv-fill{height:100%;border-radius:4px}
.dv-cnt{font-size:11px;font-weight:600;color:#374151;width:22px;text-align:right;flex-shrink:0}
.dv-pct{font-size:10px;color:#9ca3af;width:32px;text-align:right;flex-shrink:0}
.legend{display:flex;flex-wrap:wrap;gap:10px;margin-bottom:12px}
.leg{display:flex;align-items:center;gap:5px;font-size:10px;color:#6b7280}
.leg-dot{width:9px;height:9px;border-radius:2px;flex-shrink:0}
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
.rs-grid{display:grid;grid-template-columns:1fr 1fr;gap:14px}
.rs-item{display:flex;gap:10px}
.rs-bar{width:3px;border-radius:2px;flex-shrink:0}
.rs-t{font-size:11px;font-weight:600;color:#111;margin-bottom:3px}
.rs-p{font-size:11px;color:#6b7280;line-height:1.5}
.loading{text-align:center;padding:80px;color:#6b7280;font-size:14px}
.err-box{background:#fff3cd;border:1px solid #ffc107;border-radius:10px;padding:20px;margin:16px 0;font-size:13px;color:#856404;line-height:1.8}
footer{text-align:center;padding:16px 0;font-size:10px;color:#9ca3af}
@media(max-width:800px){.kpi-grid{grid-template-columns:repeat(3,1fr)}.row2{grid-template-columns:1fr}.rs-grid{grid-template-columns:1fr}}
@media(max-width:480px){.kpi-grid{grid-template-columns:repeat(2,1fr)}}
</style>
</head>
<body>
<div class="wrap"><div id="app"><div class="loading">⏳ Carregando dados da planilha...</div></div></div>
<script>
// ╔══════════════════════════════════════════╗
//   CONFIGURAÇÃO
// ╠══════════════════════════════════════════╣
const SHEET_ID = '1_LDIHQHe809hWdfuVP8MQQqWvzauhDYB';
const GID      = '775705987';
// ╚══════════════════════════════════════════╝

let chart = null;

// Busca a primeira célula que contém o texto (case-insensitive)
function findPos(rows, text, exact) {
  const s = text.toLowerCase().trim();
  for (let r = 0; r < rows.length; r++) {
    if (!rows[r]?.c) continue;
    for (let c = 0; c < rows[r].c.length; c++) {
      const v = String(rows[r].c[c]?.v ?? rows[r].c[c]?.f ?? '').toLowerCase().trim();
      if (exact ? v === s : v.includes(s)) return [r, c];
    }
  }
  return null;
}

function cv(rows, r, c) {
  try { const x = rows[r]?.c?.[c]; return x?.v ?? x?.f ?? null; } catch { return null; }
}

// Converte valor gviz para número percentual
// Lida com vírgula como decimal (padrão br): "81,0%" → 81  |  0.81 → 81
function toNum(v, fb) {
  if (fb === undefined) fb = 0;
  if (v == null) return fb;
  if (typeof v === 'number') return v >= -1 && v <= 1 ? +(v * 100).toFixed(2) : v;
  let s = String(v).trim().replace(/%/g, '');          // remove %
  s = s.replace(/,(\d{1,2})$/, '.$1');                  // vírgula decimal → ponto ("81,0" → "81.0")
  s = s.replace(/[^0-9.\-]/g, '');                      // remove restante
  return parseFloat(s) || fb;
}

function fmtDate(v) {
  if (!v) return '—';
  if (typeof v === 'string') {
    const m = v.match(/Date\((\d+),(\d+),(\d+)/);
    if (m) return `${String(m[3]).padStart(2,'0')}/${String(+m[2]+1).padStart(2,'0')}`;
    const p = v.slice(0,10).split('-');
    if (p.length === 3) return `${p[2]}/${p[1]}`;
  }
  return String(v).slice(0,10);
}

async function fetchRows() {
  const url = `https://docs.google.com/spreadsheets/d/${SHEET_ID}/gviz/tq?tqx=out:json&gid=${GID}`;
  const res = await fetch(url, { cache: 'no-store' });
  const txt = await res.text();
  const js = txt.match(/setResponse\(([\s\S]*?)\);?\s*$/)?.[1];
  if (!js) throw new Error('Resposta inesperada. Verifique se a planilha está pública.');
  return JSON.parse(js).table.rows;
}

function parseAll(rows) {
  // Log diagnóstico (F12 → Console)
  console.group('Dados brutos — Google Sheets');
  rows.forEach((r,i) => {
    const v = r?.c?.map(c => c?.v ?? c?.f ?? null).filter(x => x != null);
    if (v?.length) console.log(`Linha ${i}:`, v.slice(0,12));
  });
  console.groupEnd();

  // ── KPIs: localiza rótulo "% CONCLUÍDO" e lê linha acima ──────────
  let rPct=81, pPct=76.7, dPct=4.35, totAc=72, atrs=27;
  const concPos = findPos(rows, 'CONCLU');
  if (concPos) {
    const [lr, lc] = concPos;
    const dr = lr - 1;
    if (dr >= 0) {
      const v1=cv(rows,dr,lc), v2=cv(rows,dr,lc+1),
            v3=cv(rows,dr,lc+2), v4=cv(rows,dr,lc+3), v5=cv(rows,dr,lc+4);
      if (v1!=null) rPct  = toNum(v1, rPct);
      if (v2!=null) pPct  = toNum(v2, pPct);
      if (v3!=null) dPct  = toNum(v3, dPct);
      if (v4!=null && !isNaN(+v4)) totAc = +v4;
      if (v5!=null && !isNaN(+v5)) atrs  = +v5;
    }
  }

  // ── Desvios: localiza cabeçalho "QTD DESVIOS" ────────────────────
  const devs = [
    {nm:'ADM do Brasil',          qt:7,  cor:'#dc2626'},
    {nm:'Irmãos Passaúra',        qt:11, cor:'#2563eb'},
    {nm:'ADM + Irmãos Passaúra',  qt:1,  cor:'#9ca3af'},
  ];
  const qtdPos = findPos(rows, 'QTD DESVIOS');
  if (qtdPos) {
    const [hr, hc] = qtdPos;
    const nc = hc - 1; // nome está uma coluna à esquerda de "QTD DESVIOS"
    for (let i = 0; i < 3; i++) {
      const nm = String(cv(rows, hr+1+i, nc) ?? '').trim();
      const qt = cv(rows, hr+1+i, hc);
      if (nm && qt != null && !nm.toLowerCase().includes('total')) {
        devs[i] = {...devs[i], nm, qt: Number(qt)};
      }
    }
  }
  const totDv = devs.reduce((a,d)=>a+Number(d.qt),0) || 19;

  // ── Top 5: localiza cabeçalho "EDT" (exato) ──────────────────────
  const top5 = [];
  const edtPos = findPos(rows, 'edt', true);
  if (edtPos) {
    const [hr, hc] = edtPos;
    for (let j = 1; j <= 10; j++) {
      const edt = cv(rows, hr+j, hc);
      if (!edt) continue;
      top5.push({
        edt:  String(edt),
        ativ: String(cv(rows,hr+j,hc+1) ?? '—'),
        real: toNum(cv(rows,hr+j,hc+2)),
        prev: toNum(cv(rows,hr+j,hc+3)),
        dev:  toNum(cv(rows,hr+j,hc+4)),
        term: fmtDate(cv(rows,hr+j,hc+5)),
        area: String(cv(rows,hr+j,hc+6) ?? '—'),
        resp: String(cv(rows,hr+j,hc+7) ?? '—'),
        obs:  String(cv(rows,hr+j,hc+8) ?? '—'),
      });
    }
  }

  return { rPct, pPct, dPct, totAc, atrs, devs, totDv, top5 };
}

function render(d, ts) {
  const ahead = d.dPct >= 0;
  const badgeFn = r => r === 0 ? 'bd' : r < 50 ? 'bw' : 'bg';

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
        <button class="btn-ref" onclick="init()">↺ Atualizar</button>
      </div>
    </div>

    <div class="kpi-grid">
      <div class="kpi g"><div class="kpi-lbl">% Realizado</div><div class="kpi-val">${d.rPct.toFixed(1)}%</div></div>
      <div class="kpi n"><div class="kpi-lbl">% Previsto</div><div class="kpi-val">${d.pPct.toFixed(1)}%</div></div>
      <div class="kpi ${ahead?'g':'r'}"><div class="kpi-lbl">Desvio</div><div class="kpi-val">${ahead?'+':''}${d.dPct.toFixed(2)} p.p.</div></div>
      <div class="kpi b"><div class="kpi-lbl">Atividades</div><div class="kpi-val">${d.totAc}</div></div>
      <div class="kpi r"><div class="kpi-lbl">Atrasadas</div><div class="kpi-val">${d.atrs}</div></div>
    </div>

    <div class="row2">
      <div class="card">
        <div class="ct">Avanço físico</div>
        <div class="pb-row">
          <div class="pb-lbl"><span>Realizado</span><span>${d.rPct.toFixed(1)}%</span></div>
          <div class="pb-track"><div class="pb-fill" style="width:${Math.min(d.rPct,100)}%;background:#10b981"></div></div>
        </div>
        <div class="pb-row">
          <div class="pb-lbl"><span>Previsto</span><span>${d.pPct.toFixed(1)}%</span></div>
          <div class="pb-track"><div class="pb-fill" style="width:${Math.min(d.pPct,100)}%;background:#9ca3af"></div></div>
        </div>
        <div class="st-box ${ahead?'ok':'bad'}">
          ${ahead?'✔ Projeto adiantado':'⚠ Projeto atrasado'} — ${ahead?'+':''}${d.dPct.toFixed(2)} p.p. ${ahead?'acima':'abaixo'} do previsto
        </div>
        <div style="height:18px"></div>
        <div class="ct">Desvios por responsável</div>
        ${d.devs.map(v=>`
          <div class="dv-row">
            <div class="dv-nm">${v.nm}</div>
            <div class="dv-track"><div class="dv-fill" style="width:${Math.round(v.qt/d.totDv*100)}%;background:${v.cor}"></div></div>
            <div class="dv-cnt">${v.qt}</div>
            <div class="dv-pct">${Math.round(v.qt/d.totDv*100)}%</div>
          </div>`).join('')}
      </div>

      <div class="card">
        <div class="ct">Distribuição de desvios</div>
        <div class="legend">
          ${d.devs.map(v=>`<div class="leg"><div class="leg-dot" style="background:${v.cor}"></div>${v.nm} — <strong>${v.qt}</strong> (${Math.round(v.qt/d.totDv*100)}%)</div>`).join('')}
        </div>
        <div style="position:relative;height:190px">
          <canvas id="donut" role="img" aria-label="Distribuição de desvios por responsável"></canvas>
        </div>
        <div style="margin-top:12px;padding:10px 14px;background:#fee2e2;border-radius:8px;font-size:12px;font-weight:600;color:#991b1b">
          Total: ${d.totDv} desvios identificados
        </div>
      </div>
    </div>

    <div class="card-full">
      <div class="ct">Top 10 — atividades críticas (maior desvio)</div>
      ${d.top5.length === 0
        ? '<p style="font-size:12px;color:#9ca3af;text-align:center;padding:20px">Dados não encontrados. Abra o Console (F12) para diagnóstico.</p>'
        : `<div class="tbl-wrap"><table>
          <thead><tr>
            <th>EDT</th><th>Atividade</th>
            <th style="text-align:center">Real</th><th style="text-align:center">Prev.</th>
            <th style="text-align:center">Desvio</th><th style="text-align:center">Término</th>
            <th>Área</th><th>Responsável</th><th>Observação</th>
          </tr></thead>
          <tbody>
            ${d.top5.map(t=>`<tr>
              <td class="mono">${t.edt}</td>
              <td style="max-width:160px;color:#111">${t.ativ}</td>
              <td style="text-align:center"><span class="badge ${badgeFn(t.real)}">${t.real.toFixed(0)}%</span></td>
              <td style="text-align:center">${t.prev.toFixed(0)}%</td>
              <td style="text-align:center" class="td">${t.dev.toFixed(0)}%</td>
              <td style="text-align:center">${t.term}</td>
              <td>${t.area}</td><td>${t.resp}</td><td>${t.obs}</td>
            </tr>`).join('')}
          </tbody>
        </table></div>`}
    </div>

    <div class="card-full">
      <div class="ct">Resumo executivo</div>
      <div class="rs-grid">
        <div class="rs-item">
          <div class="rs-bar" style="background:#10b981;min-height:44px"></div>
          <div><div class="rs-t">Situação geral</div>
          <div class="rs-p">Avanço de ${d.rPct.toFixed(1)}%, superando em ${d.dPct.toFixed(1)} p.p. o previsto (${d.pPct.toFixed(1)}%). Projeto adiantado.</div></div>
        </div>
        <div class="rs-item">
          <div class="rs-bar" style="background:#ef4444;min-height:44px"></div>
          <div><div class="rs-t">Pontos de atenção</div>
          <div class="rs-p">${d.atrs} atividades atrasadas (${Math.round(d.atrs/d.totAc*100)}% do total) — 7 sob responsabilidade da ADM do Brasil e 10 de Irmãos Passaúra.</div></div>
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

  if (chart) chart.destroy();
  chart = new Chart(document.getElementById('donut'), {
    type: 'doughnut',
    data: {
      labels: d.devs.map(v=>v.nm),
      datasets: [{ data: d.devs.map(v=>v.qt), backgroundColor: d.devs.map(v=>v.cor), borderWidth:0, hoverOffset:6 }]
    },
    options: {
      responsive:true, maintainAspectRatio:false, cutout:'66%',
      plugins: { legend:{display:false}, tooltip:{callbacks:{label:c=>` ${c.label}: ${c.raw} desvios`}} }
    }
  });
}

function showError(msg) {
  const ts = new Date().toLocaleString('pt-BR',{day:'2-digit',month:'2-digit',year:'numeric',hour:'2-digit',minute:'2-digit'});
  document.getElementById('app').innerHTML = `
    <div class="hdr"><div><div class="hdr-co">Irmãos Passaúra · ADM do Brasil</div>
      <h1>Relatório Gerencial — Montagem Mecânica</h1></div>
      <div class="hdr-r"><div class="hdr-date">${ts}</div>
        <button class="btn-ref" onclick="init()">↺ Tentar novamente</button></div></div>
    <div class="err-box">
      <strong>⚠ Não foi possível carregar os dados da planilha.</strong><br>
      Erro: ${msg}<br><br>
      <strong>Para resolver:</strong><br>
      1. Abra a planilha no Google Sheets<br>
      2. Compartilhar → <strong>"Qualquer pessoa com o link"</strong> → <strong>Leitor</strong> → Salvar<br>
      3. Recarregue esta página
    </div>`;
}

async function init() {
  const btn = document.querySelector('.btn-ref');
  if (btn) { btn.disabled=true; btn.textContent='↺ Carregando...'; }
  const ts = new Date().toLocaleString('pt-BR',{day:'2-digit',month:'2-digit',year:'numeric',hour:'2-digit',minute:'2-digit'});
  try {
    const rows = await fetchRows();
    const data = parseAll(rows);
    render(data, ts);
  } catch(e) {
    showError(e.message);
  }
}

init();
</script>
</body>
</html>
