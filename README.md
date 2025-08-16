<!doctype html>
<html lang="es">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Colorea por números — Panda rojo & Mapache</title>
<style>
  :root{
    --bg:#0f1220;
    --card:#151a2b;
    --ink:#eaeaf2;
    --muted:#9aa3b2;
    --ok:#49d17d;
    --accent:#a78bfa;
  }
  *{box-sizing:border-box}
  body{
    margin:0;
    font-family: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, "Helvetica Neue", Arial;
    background: radial-gradient(1200px 800px at 20% -10%, #1b2140 0%, #0f1220 55%);
    color:var(--ink);
    min-height:100dvh;
    display:flex;
    align-items:center;
    justify-content:center;
    padding:24px;
  }
  .wrap{width:min(1000px,96vw)}
  .title{
    text-align:center;
    margin:0 0 8px 0;
    letter-spacing:.3px;
  }
  .subtitle{color:var(--muted); text-align:center; margin:0 0 18px}
  .board{
    display:grid;
    grid-template-columns: 320px 1fr;
    gap:18px;
  }
  @media (max-width:860px){
    .board{grid-template-columns: 1fr; gap:12px;}
  }
  .card{
    background:linear-gradient(180deg, #171d33, #14192a);
    border:1px solid #222744;
    border-radius:16px;
    box-shadow: 0 10px 30px rgba(0,0,0,.35);
    padding:14px;
  }
  .palette{
    display:grid;
    grid-template-columns: repeat(3, minmax(0,1fr));
    gap:10px;
    margin-top:8px;
  }
  .swatch{
    display:flex; align-items:center; gap:10px;
    padding:10px; border-radius:12px; border:1px solid #232741;
    cursor:pointer; user-select:none;
    transition:transform .06s ease, border-color .2s ease;
  }
  .swatch:hover{ transform: translateY(-2px); }
  .swatch.active{ border-color: var(--accent); outline: 2px solid color-mix(in oklab, white 12%, transparent); }
  .dot{
    width:26px; height:26px; border-radius:8px; border:1px solid rgba(0,0,0,.25);
  }
  .legend{ color:var(--muted); font-size:.92rem; margin-top:6px; line-height:1.25rem; }
  svg{
    width:100%; height:auto; display:block; background:#0c1020;
    border-radius:16px; border:1px solid #222744;
  }
  .zone{ fill:#0c1020; stroke:#3a4169; stroke-width:2; cursor:pointer; transition: fill .15s ease; }
  .num{ fill:#94a3b8; font-weight:700; font-size:18px; pointer-events:none; user-select:none; }
  .toolbar{
    display:flex; gap:10px; flex-wrap:wrap; margin-top:12px;
  }
  button{
    background:#222849; color:#eaeaf2; border:1px solid #2a3160; padding:10px 14px; border-radius:12px;
    cursor:pointer; font-weight:600; letter-spacing:.2px;
  }
  button:hover{ filter:brightness(1.05); }
  .hint{ color:#cbd5e1; }
  .progress{
    margin-top:10px; color:var(--muted); font-size:.95rem;
  }
  /* Modal */
  .modal{
    position:fixed; inset:0; display:flex; align-items:center; justify-content:center;
    background:rgba(6,8,20,.75); backdrop-filter: blur(6px);
    opacity:0; pointer-events:none; transition: opacity .25s ease;
    padding:24px;
  }
  .modal.show{ opacity:1; pointer-events:auto; }
  .modal-card{
    width:min(680px, 96vw);
    background:linear-gradient(180deg, #171d33, #14192a);
    border:1px solid #2a3160;
    border-radius:18px; padding:20px;
    text-align:center;
  }
  .modal h2{ margin:10px 0 8px }
  .qr{
    width:min(380px, 72vw);
    aspect-ratio:1/1;
    background:#fff; margin:16px auto; border-radius:12px; padding:8px;
    display:flex; align-items:center; justify-content:center;
  }
  .qr img{ width:100%; height:100%; object-fit:contain; }
  .success{ color:var(--ok); font-weight:800; letter-spacing:.3px; }
  .tiny{ color:var(--muted); font-size:.9rem; }
  .footer-note{ text-align:center; color:#8b93ad; margin-top:12px; font-size:.9rem }
</style>
</head>
<body>
<div class="wrap">
  <h1 class="title">Pinta por Números — <span style="opacity:.85">Panda rojo & Mapache</span></h1>
  <p class="subtitle">Elige un color, haz clic en las zonas numeradas y completa el dúo. Cuando todo esté correcto… algo se revelará ✨</p>

  <div class="board">
    <!-- Lienzo -->
    <div class="card">
      <!-- SVG súper simplificado estilo “libro de colorear” -->
      <svg viewBox="0 0 700 420" aria-labelledby="title desc" role="img">
        <title id="title">Panda rojo y Mapache tomados de la mano</title>
        <desc id="desc">Ilustración simple con áreas numeradas para colorear correctamente.</desc>

        <!-- SUELO -->
        <rect x="0" y="360" width="700" height="60" class="zone" data-id="ground" data-need="4"></rect>
        <text class="num" x="340" y="395">4</text>

        <!-- PANDA ROJO (izquierda) -->
        <!-- Cola -->
        <ellipse class="zone" cx="135" cy="285" rx="85" ry="26" transform="rotate(-15 135 285)" data-id="rp_tail" data-need="1"></ellipse>
        <rect class="zone" x="55" y="272" width="90" height="20" transform="rotate(-15 55 272)" data-id="rp_tail_ring1" data-need="2"></rect>
        <rect class="zone" x="90" y="276" width="90" height="20" transform="rotate(-15 90 276)" data-id="rp_tail_ring2" data-need="2"></rect>

        <!-- Cuerpo -->
        <ellipse class="zone" cx="230" cy="280" rx="70" ry="82" data-id="rp_body" data-need="1"></ellipse>
        <!-- Barriga clara -->
        <ellipse class="zone" cx="230" cy="300" rx="38" ry="46" data-id="rp_belly" data-need="5"></ellipse>

        <!-- Cabeza -->
        <ellipse class="zone" cx="230" cy="190" rx="65" ry="55" data-id="rp_face" data-need="1"></ellipse>
        <!-- Máscara clara -->
        <ellipse class="zone" cx="230" cy="205" rx="38" ry="28" data-id="rp_mask" data-need="5"></ellipse>
        <!-- Orejas -->
        <circle class="zone" cx="185" cy="155" r="20" data-id="rp_ear_l" data-need="1"></circle>
        <circle class="zone" cx="275" cy="155" r="20" data-id="rp_ear_r" data-need="1"></circle>
        <circle class="zone" cx="185" cy="155" r="10" data-id="rp_ear_l_in" data-need="2"></circle>
        <circle class="zone" cx="275" cy="155" r="10" data-id="rp_ear_r_in" data-need="2"></circle>

        <!-- Manito que toma -->
        <circle class="zone" cx="300" cy="300" r="16" data-id="rp_hand" data-need="1"></circle>

        <!-- Números del panda rojo -->
        <text class="num" x="230" y="192">1</text>
        <text class="num" x="230" y="308">5</text>
        <text class="num" x="230" y="270">1</text>
        <text class="num" x="183" y="158">1</text>
        <text class="num" x="275" y="158">1</text>
        <text class="num" x="185" y="158" dy="14">2</text>
        <text class="num" x="275" y="158" dy="14">2</text>
        <text class="num" x="300" y="304">1</text>
        <text class="num" x="135" y="290">1</text>
        <text class="num" x="100" y="280">2</text>
        <text class="num" x="140" y="284">2</text>

        <!-- MAPACHE (derecha) -->
        <!-- Cola con franjas -->
        <ellipse class="zone" cx="560" cy="290" rx="90" ry="28" transform="rotate(15 560 290)" data-id="rac_tail" data-need="3"></ellipse>
        <rect class="zone" x="516" y="278" width="90" height="20" transform="rotate(15 516 278)" data-id="rac_tail_band1" data-need="6"></rect>
        <rect class="zone" x="554" y="286" width="90" height="20" transform="rotate(15 554 286)" data-id="rac_tail_band2" data-need="6"></rect>

        <!-- Cuerpo -->
        <ellipse class="zone" cx="470" cy="280" rx="70" ry="82" data-id="rac_body" data-need="3"></ellipse>
        <!-- Barriga -->
        <ellipse class="zone" cx="470" cy="300" rx="38" ry="46" data-id="rac_belly" data-need="4"></ellipse>

        <!-- Cabeza -->
        <ellipse class="zone" cx="470" cy="190" rx="65" ry="55" data-id="rac_face" data-need="4"></ellipse>
        <!-- Máscara oscura -->
        <ellipse class="zone" cx="470" cy="205" rx="42" ry="22" data-id="rac_mask" data-need="6"></ellipse>
        <!-- Orejas -->
        <circle class="zone" cx="425" cy="155" r="20" data-id="rac_ear_l" data-need="4"></circle>
        <circle class="zone" cx="515" cy="155" r="20" data-id="rac_ear_r" data-need="4"></circle>
        <circle class="zone" cx="425" cy="155" r="10" data-id="rac_ear_l_in" data-need="6"></circle>
        <circle class="zone" cx="515" cy="155" r="10" data-id="rac_ear_r_in" data-need="6"></circle>

        <!-- Manito que toma -->
        <circle class="zone" cx="400" cy="300" r="16" data-id="rac_hand" data-need="3"></circle>

        <!-- Números del mapache -->
        <text class="num" x="470" y="192">4</text>
        <text class="num" x="470" y="308">4</text>
        <text class="num" x="470" y="270">3</text>
        <text class="num" x="515" y="158">4</text>
        <text class="num" x="425" y="158">4</text>
        <text class="num" x="515" y="168">6</text>
        <text class="num" x="425" y="168">6</text>
        <text class="num" x="400" y="304">3</text>
        <text class="num" x="560" y="294">3</text>
        <text class="num" x="528" y="286">6</text>
        <text class="num" x="566" y="294">6</text>

        <!-- MANOS UNIDAS (pequeño corazón entre manos) -->
        <path class="zone" d="M350 292c10-12 22-12 32 0-10 18-22 18-32 0z" data-id="heart" data-need="2"></path>
        <text class="num" x="360" y="292">2</text>
      </svg>

      <div class="progress" id="progress">Zonas correctas: 0 / 24</div>
      <div class="toolbar">
        <button id="reset">Reiniciar</button>
        <button id="hint" class="hint">Mostrar/Ocultar guía</button>
      </div>
    </div>

    <!-- Paleta + Guía -->
    <div class="card">
      <h3 style="margin:6px 6px 10px">Paleta</h3>
      <div id="palette" class="palette">
        <!-- Los colores se inyectan por JS -->
      </div>
      <div class="legend" id="legend" style="display:none; margin-top:12px">
        <strong>Guía:</strong><br/>
        1 = Rojo (panda rojo) · 2 = Naranja (interior orejas / corazón) · 3 = Gris oscuro (mapache) ·
        4 = Gris claro (mapache & suelo) · 5 = Crema (manchas claras panda) · 6 = Negro (máscara mapache)
      </div>
      <p class="footer-note">Pista: cuando todo esté perfecto, aparecerá una nueva ventana…</p>
    </div>
  </div>
</div>

<!-- Modal con el QR -->
<div id="modal" class="modal" aria-hidden="true">
  <div class="modal-card" role="dialog" aria-modal="true" aria-labelledby="winTitle">
    <h2 id="winTitle" class="success">¡Completado! 🌟</h2>
    <p>Desbloqueaste la pista secreta. Escanea el QR o toca el botón para abrir la playlist.</p>
    <div class="qr"><img src="qr.png" alt="Código QR a la playlist" /></div>
    <p><a id="openLink" target="_blank" rel="noopener" href="https://open.spotify.com/playlist/6rGxHrCj9w4WLERyNcsbBK?si=rLIOE8kHTDuNQpqXp7lUuw&pi=WxPawjn9RyWAr&nd=1&dlsi=e72b2da00549458d">
      <button>Abrir la playlist directamente</button>
    </a></p>
    <p class="tiny">Si no ves el QR, asegúrate de subir <code>qr.png</code> al mismo repositorio.</p>
  </div>
</div>

<script>
/* ============ Configuración ============ */
const COLORS = {
  1: { name: "Rojo",       hex: "#e63946" },
  2: { name: "Naranja",    hex: "#f4a261" },
  3: { name: "Gris oscuro",hex: "#464646" },
  4: { name: "Gris claro", hex: "#b0b0b0" },
  5: { name: "Crema",      hex: "#fff5d7" },
  6: { name: "Negro",      hex: "#111111" }
};

// Mapea cada zona -> número correcto
const ANSWER = {};
document.querySelectorAll('.zone').forEach(z=>{
  ANSWER[z.dataset.id] = Number(z.dataset.need);
});

let currentNumber = 1; // color seleccionado
const paletteEl = document.getElementById('palette');
const legendEl = document.getElementById('legend');
const progressEl = document.getElementById('progress');
const modal = document.getElementById('modal');
const totalZones = Object.keys(ANSWER).length;

// Construye la paleta
for (const n of Object.keys(COLORS)) {
  const data = COLORS[n];
  const sw = document.createElement('div');
  sw.className = 'swatch' + (Number(n)===currentNumber ? ' active':'');
  sw.dataset.num = n;

  const dot = document.createElement('div');
  dot.className = 'dot';
  dot.style.background = data.hex;

  const label = document.createElement('div');
  label.innerHTML = `<strong>${n}</strong> — ${data.name}`;

  sw.appendChild(dot);
  sw.appendChild(label);
  sw.addEventListener('click', ()=>{
    currentNumber = Number(n);
    [...paletteEl.children].forEach(c=>c.classList.remove('active'));
    sw.classList.add('active');
  });
  paletteEl.appendChild(sw);
}

// Pintar zonas
document.querySelectorAll('.zone').forEach(zone=>{
  zone.addEventListener('click', ()=>{
    const want = ANSWER[zone.dataset.id];
    const chosen = currentNumber;
    // Siempre pinta con el color elegido
    zone.style.fill = COLORS[chosen].hex;

    // ¿Correcto?
    if (chosen === want) {
      zone.dataset.ok = '1';
    } else {
      zone.dataset.ok = '0';
    }
    updateProgress();
  });
});

function updateProgress(){
  const okCount = [...document.querySelectorAll('.zone')]
    .filter(z => z.dataset.ok === '1').length;

  progressEl.textContent = `Zonas correctas: ${okCount} / ${totalZones}`;

  if (okCount === totalZones) {
    win();
  }
}

// Reiniciar
document.getElementById('reset').addEventListener('click', ()=>{
  document.querySelectorAll('.zone').forEach(z=>{
    z.style.fill = '#0c1020';
    z.dataset.ok = '0';
  });
  progressEl.textContent = `Zonas correctas: 0 / ${totalZones}`;
});

// Hint
document.getElementById('hint').addEventListener('click', ()=>{
  legendEl.style.display = (legendEl.style.display==='none' || !legendEl.style.display) ? 'block' : 'none';
});

function win(){
  modal.classList.add('show');
  modal.setAttribute('aria-hidden','false');
}
// Cierra modal haciendo click fuera de la tarjeta
modal.addEventListener('click', (e)=>{
  if (e.target === modal) {
    modal.classList.remove('show');
    modal.setAttribute('aria-hidden','true');
  }
});
</script>
</body>
</html>
