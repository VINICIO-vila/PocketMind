<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Control de Gastos Diarios</title>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@latest/tabler-icons.min.css" />
<style>
  * { box-sizing: border-box; margin: 0; padding: 0; }
  body { font-family: system-ui, sans-serif; background: #f5f5f0; color: #1a1a18; min-height: 100vh; }
  .app { max-width: 720px; margin: 0 auto; padding: 1.5rem 1rem; }
  h1 { font-size: 22px; font-weight: 500; margin-bottom: 1.5rem; }
  .tabs { display: flex; gap: 4px; margin-bottom: 1.5rem; border-bottom: 0.5px solid #ccc; }
  .tab { padding: 8px 16px; font-size: 13px; color: #666; cursor: pointer; border: none; background: none; border-bottom: 2px solid transparent; margin-bottom: -1px; transition: all .15s; }
  .tab.active { color: #1a1a18; border-bottom-color: #1a1a18; font-weight: 500; }
  .section { display: none; }
  .section.active { display: block; }
  .metric-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(140px, 1fr)); gap: 12px; margin-bottom: 1.5rem; }
  .metric { background: #e8e8e2; border-radius: 8px; padding: 1rem; }
  .metric-label { font-size: 12px; color: #666; margin-bottom: 4px; }
  .metric-value { font-size: 22px; font-weight: 500; color: #1a1a18; }
  .metric-sub { font-size: 11px; color: #999; margin-top: 2px; }
  .card { background: #fff; border: 0.5px solid #ddd; border-radius: 12px; padding: 1rem 1.25rem; margin-bottom: 1rem; }
  .card-title { font-size: 13px; font-weight: 500; color: #666; margin-bottom: 1rem; }
  input, select, button { font-family: inherit; font-size: 14px; border-radius: 8px; outline: none; }
  input, select { border: 0.5px solid #ccc; padding: 0 12px; height: 36px; background: #fff; color: #1a1a18; width: 100%; }
  input:focus, select:focus { border-color: #888; }
  button { border: 0.5px solid #bbb; background: transparent; padding: 0 16px; height: 36px; cursor: pointer; color: #1a1a18; transition: background .15s; }
  button:hover { background: #f0f0ea; }
  button:active { transform: scale(0.98); }
  .add-form { display: grid; grid-template-columns: 1fr 1fr 1fr auto; gap: 8px; align-items: end; margin-bottom: 1rem; }
  .field label { font-size: 11px; color: #666; display: block; margin-bottom: 4px; }
  .expense-list { display: flex; flex-direction: column; gap: 6px; }
  .expense-item { display: flex; align-items: center; gap: 10px; padding: 8px 12px; background: #f5f5f0; border-radius: 8px; }
  .cat-dot { width: 8px; height: 8px; border-radius: 50%; flex-shrink: 0; }
  .exp-desc { flex: 1; font-size: 14px; }
  .exp-cat { font-size: 11px; color: #999; }
  .exp-amount { font-size: 14px; font-weight: 500; }
  .exp-delete { background: none; border: none; cursor: pointer; color: #bbb; padding: 4px; font-size: 16px; line-height: 1; height: auto; }
  .exp-delete:hover { color: #e24b4a; background: none; }
  .progress-bar-wrap { background: #e8e8e2; border-radius: 4px; height: 8px; overflow: hidden; margin: 6px 0; }
  .progress-bar { height: 100%; border-radius: 4px; transition: width .3s; }
  .bar-green { background: #639922; }
  .bar-amber { background: #BA7517; }
  .bar-red { background: #E24B4A; }
  .alert-box { padding: 10px 14px; border-radius: 8px; font-size: 13px; margin-bottom: 1rem; display: none; }
  .alert-warn { background: #FAEEDA; color: #633806; border: 0.5px solid #FAC775; }
  .alert-danger { background: #FCEBEB; color: #501313; border: 0.5px solid #F7C1C1; }
  .cat-breakdown { display: flex; flex-direction: column; gap: 8px; }
  .cat-row { display: flex; align-items: center; gap: 10px; }
  .cat-name { font-size: 13px; color: #666; width: 120px; flex-shrink: 0; }
  .cat-bar-wrap { flex: 1; background: #e8e8e2; border-radius: 4px; height: 6px; overflow: hidden; }
  .cat-bar { height: 100%; border-radius: 4px; }
  .cat-amount { font-size: 13px; font-weight: 500; min-width: 80px; text-align: right; }
  .hormiga-list { display: flex; flex-direction: column; gap: 6px; }
  .hormiga-item { display: flex; justify-content: space-between; align-items: center; padding: 8px 12px; background: #f5f5f0; border-radius: 8px; }
  .hormiga-name { font-size: 13px; }
  .hormiga-count { font-size: 11px; color: #999; }
  .hormiga-total { font-size: 13px; font-weight: 500; color: #BA7517; }
  .racha-display { text-align: center; padding: 1.5rem 0; }
  .racha-num { font-size: 56px; font-weight: 500; line-height: 1; }
  .racha-label { font-size: 14px; color: #666; margin-top: 4px; }
  .racha-days { display: flex; gap: 6px; justify-content: center; flex-wrap: wrap; margin-top: 1rem; }
  .racha-day { width: 36px; height: 36px; border-radius: 8px; display: flex; align-items: center; justify-content: center; font-size: 11px; }
  .day-ok { background: #EAF3DE; color: #3B6D11; }
  .day-bad { background: #e8e8e2; color: #999; }
  .day-today { border: 1.5px solid #1a1a18; }
  .goal-list { display: flex; flex-direction: column; gap: 8px; }
  .goal-item { background: #f5f5f0; border-radius: 8px; padding: 12px; }
  .goal-header { display: flex; justify-content: space-between; align-items: baseline; margin-bottom: 6px; }
  .goal-name { font-size: 14px; font-weight: 500; }
  .goal-sub { font-size: 12px; color: #666; margin-top: 4px; }
  .currency-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; margin-bottom: 1rem; }
  .currency-card { background: #f5f5f0; border-radius: 8px; padding: 1rem; text-align: center; }
  .currency-flag { font-size: 28px; margin-bottom: 4px; }
  .currency-rate { font-size: 20px; font-weight: 500; }
  .currency-label { font-size: 11px; color: #666; }
  .convert-row { display: flex; gap: 8px; align-items: center; margin-top: 1rem; }
  .convert-result { font-size: 18px; font-weight: 500; min-width: 120px; text-align: right; }
  .empty-state { text-align: center; padding: 2rem; color: #aaa; font-size: 14px; }
  @media (max-width: 500px) {
    .add-form { grid-template-columns: 1fr 1fr; }
    .add-form button { grid-column: 1 / -1; }
  }
  @media (prefers-color-scheme: dark) {
    body { background: #1a1a18; color: #e8e8e2; }
    .metric { background: #2c2c2a; }
    .metric-label, .metric-sub { color: #888; }
    .metric-value { color: #e8e8e2; }
    .card { background: #222220; border-color: #3a3a38; }
    .card-title { color: #888; }
    input, select { background: #2c2c2a; border-color: #444; color: #e8e8e2; }
    button { border-color: #444; color: #e8e8e2; }
    button:hover { background: #2c2c2a; }
    .expense-item, .goal-item, .hormiga-item, .currency-card { background: #2c2c2a; }
    .progress-bar-wrap, .cat-bar-wrap { background: #3a3a38; }
    .racha-day.day-bad { background: #2c2c2a; }
    .empty-state { color: #555; }
    .cat-name, .goal-sub, .racha-label, .currency-label { color: #888; }
    .hormiga-count, .exp-cat { color: #666; }
    .alert-warn { background: #3a2800; color: #FAC775; border-color: #6b4a00; }
    .alert-danger { background: #3a0000; color: #F7C1C1; border-color: #6b0000; }
  }
</style>
</head>
<body>
<div class="app">
  <h1>💰 Control de Gastos</h1>

  <div class="tabs">
    <button class="tab active" onclick="showTab('inicio', this)"><i class="ti ti-home"></i> Inicio</button>
    <button class="tab" onclick="showTab('metas', this)"><i class="ti ti-target"></i> Metas</button>
    <button class="tab" onclick="showTab('analisis', this)"><i class="ti ti-chart-bar"></i> Análisis</button>
    <button class="tab" onclick="showTab('moneda', this)"><i class="ti ti-currency-dollar"></i> Moneda</button>
  </div>

  <!-- INICIO -->
  <div id="tab-inicio" class="section active">
    <div class="metric-grid">
      <div class="metric"><div class="metric-label">Hoy</div><div class="metric-value" id="m-hoy">$0</div><div class="metric-sub">ARS</div></div>
      <div class="metric"><div class="metric-label">Este mes</div><div class="metric-value" id="m-mes">$0</div><div class="metric-sub" id="m-presupuesto-label">sin presupuesto</div></div>
      <div class="metric"><div class="metric-label">Racha sin exceso</div><div class="metric-value" id="m-racha">0</div><div class="metric-sub">días</div></div>
      <div class="metric"><div class="metric-label">Presupuesto restante</div><div class="metric-value" id="m-restante">$0</div><div class="metric-sub" id="m-restante-label">configurá presupuesto</div></div>
    </div>

    <div id="alert-80" class="alert-box alert-warn"><i class="ti ti-alert-triangle"></i> Alcanzaste el 80% de tu presupuesto mensual</div>
    <div id="alert-100" class="alert-box alert-danger"><i class="ti ti-alert-circle"></i> Superaste tu presupuesto mensual</div>

    <div class="card">
      <div class="card-title">Presupuesto mensual</div>
      <div style="display:flex; gap:8px; align-items:center;">
        <input type="number" id="inp-presupuesto" placeholder="Ej: 150000" oninput="updatePresupuesto()" />
        <span style="font-size:13px; color:#888; white-space:nowrap;">ARS/mes</span>
      </div>
      <div class="progress-bar-wrap" style="margin-top:10px;">
        <div class="progress-bar bar-green" id="bar-presupuesto" style="width:0%"></div>
      </div>
      <div style="font-size:11px; color:#888; margin-top:4px;" id="bar-label">0% usado</div>
    </div>

    <div class="card">
      <div class="card-title">Agregar gasto</div>
      <div class="add-form">
        <div class="field"><label>Monto (ARS)</label><input type="number" id="inp-monto" placeholder="1500" /></div>
        <div class="field">
          <label>Categoría</label>
          <select id="inp-cat">
            <option value="Comida">🍔 Comida</option>
            <option value="Transporte">🚌 Transporte</option>
            <option value="Entretenimiento">🎬 Entretenimiento</option>
            <option value="Supermercado">🛒 Supermercado</option>
            <option value="Salud">💊 Salud</option>
            <option value="Café">☕ Café</option>
            <option value="Ropa">👕 Ropa</option>
            <option value="Otros">📦 Otros</option>
          </select>
        </div>
        <div class="field"><label>Descripción</label><input type="text" id="inp-desc" placeholder="Ej: Almuerzo" /></div>
        <button onclick="addExpense()"><i class="ti ti-plus"></i> Agregar</button>
      </div>
    </div>

    <div class="card">
      <div class="card-title">Gastos de hoy</div>
      <div class="expense-list" id="expense-list"><div class="empty-state">Todavía no agregaste gastos hoy</div></div>
    </div>
  </div>

  <!-- METAS -->
  <div id="tab-metas" class="section">
    <div class="card">
      <div class="card-title">Nueva meta de ahorro</div>
      <div style="display:grid; grid-template-columns:1fr 1fr; gap:8px; margin-bottom:8px;">
        <div class="field"><label>Nombre</label><input type="text" id="meta-nombre" placeholder="Ej: Vacaciones" /></div>
        <div class="field"><label>Monto objetivo (ARS)</label><input type="number" id="meta-objetivo" placeholder="200000" /></div>
      </div>
      <div style="display:grid; grid-template-columns:1fr 1fr; gap:8px; margin-bottom:10px;">
        <div class="field"><label>Ya tengo (ARS)</label><input type="number" id="meta-actual" placeholder="0" /></div>
        <div class="field"><label>Plazo (meses)</label><input type="number" id="meta-meses" placeholder="3" /></div>
      </div>
      <button style="width:100%;" onclick="addMeta()"><i class="ti ti-plus"></i> Agregar meta</button>
    </div>
    <div class="goal-list" id="goal-list"><div class="empty-state">No tenés metas aún. ¡Agregá una!</div></div>
  </div>

  <!-- ANÁLISIS -->
  <div id="tab-analisis" class="section">
    <div class="card">
      <div class="card-title">En qué más gastás este mes</div>
      <div class="cat-breakdown" id="cat-breakdown"><div class="empty-state">Sin datos todavía</div></div>
    </div>
    <div class="card">
      <div class="card-title">Días con más gastos (últimos 7 días)</div>
      <div style="position:relative; width:100%; height:220px;">
        <canvas id="myChartDias" role="img" aria-label="Gastos por día de la semana"></canvas>
      </div>
    </div>
    <div class="card">
      <div class="card-title"><i class="ti ti-bug"></i> Gasto hormiga — pequeños gastos frecuentes</div>
      <div class="hormiga-list" id="hormiga-list"><div class="empty-state">Sin gastos hormigas detectados</div></div>
    </div>
    <div class="card" style="text-align:center;">
      <div class="card-title">Racha sin exceso diario</div>
      <div class="racha-display">
        <div class="racha-num" id="racha-num">0</div>
        <div class="racha-label">días consecutivos dentro del límite</div>
      </div>
      <div class="racha-days" id="racha-days"></div>
    </div>
  </div>

  <!-- MONEDA -->
  <div id="tab-moneda" class="section">
    <div class="card">
      <div class="card-title">Tasas de referencia</div>
      <div class="currency-grid">
        <div class="currency-card"><div class="currency-flag">🇺🇸</div><div class="currency-rate">1 USD</div><div class="currency-label">= <span id="rate-usd-val">1200</span> ARS</div></div>
        <div class="currency-card"><div class="currency-flag">🇧🇷</div><div class="currency-rate">1 BRL</div><div class="currency-label">= <span id="rate-brl-val">220</span> ARS</div></div>
        <div class="currency-card"><div class="currency-flag">🇪🇺</div><div class="currency-rate">1 EUR</div><div class="currency-label">= <span id="rate-eur-val">1300</span> ARS</div></div>
        <div class="currency-card"><div class="currency-flag">🇺🇾</div><div class="currency-rate">1 UYU</div><div class="currency-label">= <span id="rate-uyu-val">28</span> ARS</div></div>
      </div>
      <div style="font-size:11px; color:#888; margin-bottom:1rem;">Tasas aproximadas — actualizalas según el tipo de cambio del día</div>
      <div style="display:grid; grid-template-columns:1fr 1fr; gap:8px;">
        <div class="field"><label>Tasa USD/ARS</label><input type="number" id="custom-usd" placeholder="1200" oninput="updateRates()" /></div>
        <div class="field"><label>Tasa EUR/ARS</label><input type="number" id="custom-eur" placeholder="1300" oninput="updateRates()" /></div>
      </div>
    </div>
    <div class="card">
      <div class="card-title">Convertir</div>
      <div class="convert-row">
        <input type="number" id="conv-amount" placeholder="Monto" oninput="convert()" style="flex:2;" />
        <select id="conv-from" onchange="convert()" style="flex:1;">
          <option value="ARS">ARS</option>
          <option value="USD">USD</option>
          <option value="EUR">EUR</option>
          <option value="BRL">BRL</option>
          <option value="UYU">UYU</option>
        </select>
        <span style="color:#888; font-size:18px;">→</span>
        <select id="conv-to" onchange="convert()" style="flex:1;">
          <option value="USD">USD</option>
          <option value="ARS" selected>ARS</option>
          <option value="EUR">EUR</option>
          <option value="BRL">BRL</option>
          <option value="UYU">UYU</option>
        </select>
      </div>
      <div style="margin-top:1rem; padding:1rem; background:#f5f5f0; border-radius:8px; text-align:center;">
        <div class="convert-result" id="conv-result">—</div>
        <div style="font-size:11px; color:#888; margin-top:4px;" id="conv-label"></div>
      </div>
    </div>
    <div class="card">
      <div class="card-title">Total gastado este mes en otras monedas</div>
      <div id="gastos-moneda"><div class="empty-state">Cargá gastos para ver el equivalente</div></div>
    </div>
  </div>
</div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.js"></script>
<script>
const CAT_COLORS = {
  'Comida': '#E24B4A', 'Transporte': '#378ADD', 'Entretenimiento': '#D4537E',
  'Supermercado': '#639922', 'Salud': '#1D9E75', 'Café': '#BA7517',
  'Ropa': '#7F77DD', 'Otros': '#888780'
};

let expenses = JSON.parse(localStorage.getItem('gastos_expenses') || '[]');
let metas = JSON.parse(localStorage.getItem('gastos_metas') || '[]');
let presupuesto = parseFloat(localStorage.getItem('gastos_presupuesto') || '0');
let rates = { USD: 1200, EUR: 1300, BRL: 220, UYU: 28 };
let diasChart = null;

function save() {
  localStorage.setItem('gastos_expenses', JSON.stringify(expenses));
  localStorage.setItem('gastos_metas', JSON.stringify(metas));
  localStorage.setItem('gastos_presupuesto', presupuesto);
}

function todayStr() { return new Date().toISOString().slice(0, 10); }

function showTab(name, btn) {
  document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));
  document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
  document.getElementById('tab-' + name).classList.add('active');
  btn.classList.add('active');
  if (name === 'analisis') renderAnalisis();
  if (name === 'moneda') renderMoneda();
}

function updatePresupuesto() {
  presupuesto = parseFloat(document.getElementById('inp-presupuesto').value) || 0;
  save(); renderMetrics();
}

function addExpense() {
  const monto = parseFloat(document.getElementById('inp-monto').value);
  const cat = document.getElementById('inp-cat').value;
  const desc = document.getElementById('inp-desc').value || cat;
  if (!monto || monto <= 0) return;
  expenses.push({ id: Date.now(), monto, cat, desc, date: todayStr() });
  save();
  document.getElementById('inp-monto').value = '';
  document.getElementById('inp-desc').value = '';
  renderAll();
}

function deleteExpense(id) {
  expenses = expenses.filter(e => e.id !== id);
  save(); renderAll();
}

function addMeta() {
  const nombre = document.getElementById('meta-nombre').value;
  const objetivo = parseFloat(document.getElementById('meta-objetivo').value);
  const actual = parseFloat(document.getElementById('meta-actual').value) || 0;
  const meses = parseInt(document.getElementById('meta-meses').value) || 1;
  if (!nombre || !objetivo) return;
  metas.push({ id: Date.now(), nombre, objetivo, actual, meses });
  save();
  ['meta-nombre','meta-objetivo','meta-actual','meta-meses'].forEach(id => document.getElementById(id).value = '');
  renderMetas();
}

function deleteMeta(id) {
  metas = metas.filter(m => m.id !== id);
  save(); renderMetas();
}

function fmt(n) { return '$' + Math.round(n).toLocaleString('es-AR'); }

function renderMetrics() {
  const today = todayStr();
  const thisMonth = today.slice(0, 7);
  const todayTotal = expenses.filter(e => e.date === today).reduce((s, e) => s + e.monto, 0);
  const mesTotal = expenses.filter(e => e.date.startsWith(thisMonth)).reduce((s, e) => s + e.monto, 0);
  document.getElementById('m-hoy').textContent = fmt(todayTotal);
  document.getElementById('m-mes').textContent = fmt(mesTotal);
  document.getElementById('m-presupuesto-label').textContent = presupuesto > 0 ? 'de ' + fmt(presupuesto) : 'sin presupuesto';
  const restante = presupuesto > 0 ? presupuesto - mesTotal : 0;
  document.getElementById('m-restante').textContent = fmt(Math.max(0, restante));
  document.getElementById('m-restante-label').textContent = presupuesto > 0 ? 'disponible' : 'configurá presupuesto';
  const pct = presupuesto > 0 ? Math.min(100, (mesTotal / presupuesto) * 100) : 0;
  const bar = document.getElementById('bar-presupuesto');
  bar.style.width = pct.toFixed(1) + '%';
  bar.className = 'progress-bar ' + (pct >= 100 ? 'bar-red' : pct >= 80 ? 'bar-amber' : 'bar-green');
  document.getElementById('bar-label').textContent = Math.round(pct) + '% usado';
  document.getElementById('alert-80').style.display = (pct >= 80 && pct < 100) ? 'block' : 'none';
  document.getElementById('alert-100').style.display = pct >= 100 ? 'block' : 'none';
  renderRacha();
}

function renderRacha() {
  const limite = presupuesto > 0 ? presupuesto / 30 : 5000;
  const days = [];
  for (let i = 6; i >= 0; i--) {
    const d = new Date(); d.setDate(d.getDate() - i);
    const ds = d.toISOString().slice(0, 10);
    const total = expenses.filter(e => e.date === ds).reduce((s, e) => s + e.monto, 0);
    days.push({ ds, ok: total <= limite, isToday: i === 0, label: d.toLocaleDateString('es', { weekday: 'short' }).slice(0, 2) });
  }
  let streak = 0;
  for (let i = days.length - 1; i >= 0; i--) { if (days[i].ok) streak++; else break; }
  document.getElementById('m-racha').textContent = streak;
  const rn = document.getElementById('racha-num');
  if (rn) rn.textContent = streak;
  const rd = document.getElementById('racha-days');
  if (rd) rd.innerHTML = days.map(d => `<div class="racha-day ${d.ok ? 'day-ok' : 'day-bad'} ${d.isToday ? 'day-today' : ''}" title="${d.ds}">${d.label}</div>`).join('');
}

function renderExpenses() {
  const today = todayStr();
  const list = expenses.filter(e => e.date === today).reverse();
  const container = document.getElementById('expense-list');
  if (list.length === 0) { container.innerHTML = '<div class="empty-state">Todavía no agregaste gastos hoy</div>'; return; }
  container.innerHTML = list.map(e => `
    <div class="expense-item">
      <div class="cat-dot" style="background:${CAT_COLORS[e.cat] || '#888'}"></div>
      <div style="flex:1"><div class="exp-desc">${e.desc}</div><div class="exp-cat">${e.cat}</div></div>
      <div class="exp-amount">${fmt(e.monto)}</div>
      <button class="exp-delete" onclick="deleteExpense(${e.id})" aria-label="Eliminar"><i class="ti ti-x"></i></button>
    </div>`).join('');
}

function renderMetas() {
  const container = document.getElementById('goal-list');
  if (metas.length === 0) { container.innerHTML = '<div class="empty-state">No tenés metas aún. ¡Agregá una!</div>'; return; }
  container.innerHTML = metas.map(m => {
    const pct = Math.min(100, (m.actual / m.objetivo) * 100);
    const porMes = Math.max(0, (m.objetivo - m.actual) / m.meses);
    return `<div class="goal-item">
      <div class="goal-header">
        <div class="goal-name">${m.nombre}</div>
        <div style="display:flex;align-items:center;gap:8px;">
          <span style="font-size:12px;color:#888;">${Math.round(pct)}%</span>
          <button onclick="deleteMeta(${m.id})" style="background:none;border:none;cursor:pointer;color:#bbb;font-size:14px;padding:0;height:auto;" aria-label="Eliminar meta"><i class="ti ti-trash"></i></button>
        </div>
      </div>
      <div class="progress-bar-wrap"><div class="progress-bar bar-green" style="width:${pct.toFixed(1)}%"></div></div>
      <div class="goal-sub">${fmt(m.actual)} de ${fmt(m.objetivo)} — ahorrá ${fmt(porMes / 30)}/día o ${fmt(porMes)}/mes para lograrlo en ${m.meses} mes${m.meses > 1 ? 'es' : ''}</div>
    </div>`;
  }).join('');
}

function renderAnalisis() {
  const thisMonth = todayStr().slice(0, 7);
  const mes = expenses.filter(e => e.date.startsWith(thisMonth));
  const catTotals = {};
  mes.forEach(e => { catTotals[e.cat] = (catTotals[e.cat] || 0) + e.monto; });
  const sorted = Object.entries(catTotals).sort((a, b) => b[1] - a[1]);
  const total = sorted.reduce((s, [, v]) => s + v, 0);
  const bd = document.getElementById('cat-breakdown');
  bd.innerHTML = sorted.length === 0 ? '<div class="empty-state">Sin datos todavía</div>' :
    sorted.map(([cat, val]) => `
      <div class="cat-row">
        <div class="cat-name">${cat}</div>
        <div class="cat-bar-wrap"><div class="cat-bar" style="width:${total > 0 ? (val/total*100).toFixed(1) : 0}%; background:${CAT_COLORS[cat] || '#888'};"></div></div>
        <div class="cat-amount">${fmt(val)}</div>
      </div>`).join('');
  renderDiasChart();
  renderHormiga(mes);
  renderRacha();
}

function renderDiasChart() {
  const labels = [], data = [];
  for (let i = 6; i >= 0; i--) {
    const d = new Date(); d.setDate(d.getDate() - i);
    const ds = d.toISOString().slice(0, 10);
    labels.push(d.toLocaleDateString('es', { weekday: 'short' }));
    data.push(Math.round(expenses.filter(e => e.date === ds).reduce((s, e) => s + e.monto, 0)));
  }
  if (diasChart) diasChart.destroy();
  diasChart = new Chart(document.getElementById('myChartDias'), {
    type: 'bar',
    data: { labels, datasets: [{ label: 'ARS', data, backgroundColor: data.map((v, i) => i === 6 ? '#378ADD' : '#B5D4F4'), borderRadius: 4 }] },
    options: {
      responsive: true, maintainAspectRatio: false,
      plugins: { legend: { display: false } },
      scales: {
        y: { ticks: { callback: v => '$' + Math.round(v).toLocaleString('es-AR') }, grid: { color: 'rgba(128,128,128,0.1)' } },
        x: { grid: { display: false }, ticks: { autoSkip: false } }
      }
    }
  });
}

function renderHormiga(mes) {
  const counts = {};
  mes.forEach(e => { if (!counts[e.desc]) counts[e.desc] = { total: 0, n: 0 }; counts[e.desc].total += e.monto; counts[e.desc].n++; });
  const hormigas = Object.entries(counts).filter(([, v]) => v.n >= 2 && v.total / v.n < 3000).sort((a, b) => b[1].total - a[1].total);
  const container = document.getElementById('hormiga-list');
  container.innerHTML = hormigas.length === 0 ? '<div class="empty-state">Sin gastos hormigas detectados (gastos pequeños y frecuentes)</div>' :
    hormigas.map(([desc, v]) => `
      <div class="hormiga-item">
        <div><div class="hormiga-name">${desc}</div><div class="hormiga-count">${v.n} veces · ${fmt(Math.round(v.total / v.n))} promedio</div></div>
        <div class="hormiga-total">${fmt(v.total)} este mes</div>
      </div>`).join('');
}

function updateRates() {
  const usd = parseFloat(document.getElementById('custom-usd').value);
  const eur = parseFloat(document.getElementById('custom-eur').value);
  if (usd > 0) rates.USD = usd;
  if (eur > 0) rates.EUR = eur;
  renderMoneda();
}

function renderMoneda() {
  document.getElementById('rate-usd-val').textContent = Math.round(rates.USD).toLocaleString('es-AR');
  document.getElementById('rate-eur-val').textContent = Math.round(rates.EUR).toLocaleString('es-AR');
  document.getElementById('rate-brl-val').textContent = Math.round(rates.BRL).toLocaleString('es-AR');
  document.getElementById('rate-uyu-val').textContent = Math.round(rates.UYU).toLocaleString('es-AR');
  const thisMonth = todayStr().slice(0, 7);
  const totalARS = expenses.filter(e => e.date.startsWith(thisMonth)).reduce((s, e) => s + e.monto, 0);
  const container = document.getElementById('gastos-moneda');
  if (totalARS === 0) { container.innerHTML = '<div class="empty-state">Cargá gastos para ver el equivalente en otras monedas</div>'; return; }
  container.innerHTML = [['🇺🇸 USD', totalARS / rates.USD, 'USD'], ['🇪🇺 EUR', totalARS / rates.EUR, 'EUR'], ['🇧🇷 BRL', totalARS / rates.BRL, 'BRL'], ['🇺🇾 UYU', totalARS / rates.UYU, 'UYU']]
    .map(([flag, val, cur]) => `<div style="display:flex;justify-content:space-between;align-items:center;padding:10px 0;border-bottom:0.5px solid #ddd;"><span style="font-size:14px;color:#888;">${flag}</span><span style="font-size:15px;font-weight:500;">${val.toFixed(2)} ${cur}</span></div>`).join('');
}

function convert() {
  const amount = parseFloat(document.getElementById('conv-amount').value) || 0;
  const from = document.getElementById('conv-from').value;
  const to = document.getElementById('conv-to').value;
  const toARS = (v, cur) => cur === 'ARS' ? v : v * rates[cur];
  const fromARS = (v, cur) => cur === 'ARS' ? v : v / rates[cur];
  const result = fromARS(toARS(amount, from), to);
  document.getElementById('conv-result').textContent = result.toFixed(2) + ' ' + to;
  document.getElementById('conv-label').textContent = amount + ' ' + from + ' → ' + result.toFixed(2) + ' ' + to;
}

function renderAll() { renderMetrics(); renderExpenses(); renderMetas(); }

if (presupuesto > 0) document.getElementById('inp-presupuesto').value = presupuesto;
renderAll();
</script>
</body>
</html>
