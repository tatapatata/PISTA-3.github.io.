<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Pinta por Números – Panda Rojo & Mapache</title>
<style>
  :root{
    --bg:#0f1221; --panel:#11162a; --ink:#d8e1ff; --muted:#8ea2ff33;
  }
  html,body{margin:0;height:100%;background:var(--bg);color:var(--ink);font-family:system-ui,-apple-system,Segoe UI,Roboto,Inter,sans-serif}
  .wrap{display:grid;grid-template-columns:320px 1fr;gap:16px;height:100%}
  .left{background:var(--panel);padding:18px 16px;overflow:auto}
  .title{font-size:22px;font-weight:800;margin:0 0 6px}
  .sub{opacity:.8;margin:0 0 14px}
  .palette{display:grid;grid-template-columns:repeat(5,1fr);gap:10px;margin:8px 0 14px}
  .sw{height:36px;border-radius:10px;border:2px solid #ffffff33;cursor:pointer;outline:0;display:flex;align-items:center;justify-content:center;font-weight:700}
  .sw.active{box-shadow:0 0 0 3px #ffffff66}
  .legend{display:grid;grid-template-columns:repeat(2,1fr);gap:8px;font-size:14px}
  .legend div{display:flex;gap:8px;align-items:center;background:#ffffff08;border:1px solid #ffffff12;border-radius:10px;padding:8px 10px}
  .legend b{display:inline-grid;place-items:center;width:26px;height:26px;border-radius:8px;border:2px solid #ffffff22}
  .btn{appearance:none;border:0;background:#4f6aff;color:white;border-radius:12px;padding:10px 14px;font-weight:700;cursor:pointer}
  .btn.ghost{background:#ffffff10}
  .tog{display:flex;align-items:center;gap:8px;margin-top:8px}
  .stage{position:relative;overflow:auto;background:#0b0f1f;border-left:1px solid #ffffff10}
  svg{max-width:none;width:2000px;height:2000px;display:block;margin:auto;background:#0b0f1f}
  .area{fill:#00000000;stroke:#b9c6ff;stroke-opacity:.55;stroke-width:4;cursor:pointer;transition:transform .08s ease}
  .area:hover{transform:scale(1.01)}
  .num{font: 64px/1.1 ui-monospace,Menlo,Consolas,monospace;fill:#b9c6ff;opacity:.7;pointer-events:none}
  .hiddenNums .num{display:none}
  .wrong{animation:shake .28s linear 1}
  @keyframes shake{0%,100%{transform:translateX(0)}25%{transform:translateX(-8px)}75%{transform:translateX(8px)}}
  .qrWrap{position:absolute;inset:0;display:none;place-items:center;background:#0b0f1fcc;backdrop-filter:blur(4px)}
  .qrCard{background:#0f142a;border:1px solid #ffffff22;border-radius:20px;padding:20px;max-width:560px;text-align:center;box-shadow:0 12px 40px #0008}
  .qrCard img{width:320px;height:320px;object-fit:contain;border-radius:14px;border:1px solid #ffffff22;background:white}
  .done{display:inline-block;margin-top:10px;font-weight:700;color:#9be7ff}
  .progress{margin-top:10px;font-size:14px;opacity:.8}
  .footer{opacity:.7;font-size:12px;margin-top:16px}
</style>
</head>
<body>
<div class="wrap">
  <aside class="left">
    <h1 class="title">Pinta por números</h1>
    <p class="sub">Elige un <b>número</b> y pinta solo las zonas con ese número. Cuando completes todo, aparecerá una sorpresa.</p>

    <div class="palette" id="palette"></div>

    <div class="legend" id="legend"></div>

    <div class="tog">
      <button class="btn" id="reset">Reiniciar</button>
      <button class="btn ghost" id="toggleNums">Mostrar/ocultar números</button>
    </div>

    <div class="progress" id="progress">Progreso: 0 / 32 zonas</div>
    <p class="footer">Consejo: haz zoom con dos dedos (móvil) o Ctrl+rueda (PC) en el navegador para detalles finos.</p>
  </aside>

  <main class="stage">
    <!-- capa QR al completar -->
    <div class="qrWrap" id="qr">
      <div class="qrCard">
        <h2>¡Completado! 🧩</h2>
        <p>Escanéame para seguir con la siguiente pista.</p>
        <img src="qr.png" alt="QR siguiente pista">
        <div class="done">Desbloqueado: Panda rojo + Mapache</div>
      </div>
    </div>

    <!-- Lienzo 2000x2000 -->
    <svg id="board" viewBox="0 0 2000 2000" aria-label="Pinta por números">
      <!-- Fondo decorativo -->
      <defs>
        <radialGradient id="bgGrad" cx="50%" cy="30%" r="70%">
          <stop offset="0%" stop-color="#12204a"/>
          <stop offset="100%" stop-color="#0b0f1f"/>
        </radialGradient>
      </defs>
      <rect x="0" y="0" width="2000" height="2000" fill="url(#bgGrad)"/>

      <!-- ===== Panda rojo (izquierda) ===== -->
      <g id="redPanda" transform="translate(260,380)">
        <!-- cuerpo principal -->
        <ellipse class="area" data-num="1" id="rp_body" cx="520" cy="760" rx="420" ry="520"/>
        <text class="num" x="480" y="760">1</text>

        <!-- vientre claro -->
        <ellipse class="area" data-num="3" id="rp_belly" cx="520" cy="1020" rx="260" ry="300"/>
        <text class="num" x="480" y="1040">3</text>

        <!-- cabeza -->
        <circle class="area" data-num="1" id="rp_head" cx="520" cy="380" r="260"/>
        <text class="num" x="480" y="390">1</text>

        <!-- orejas -->
        <ellipse class="area" data-num="3" id="rp_earL" cx="360" cy="200" rx="120" ry="140"/>
        <text class="num" x="340" y="210">3</text>
        <ellipse class="area" data-num="3" id="rp_earR" cx="680" cy="200" rx="120" ry="140"/>
        <text class="num" x="660" y="210">3</text>

        <!-- mofletes claros -->
        <ellipse class="area" data-num="3" id="rp_cheekL" cx="420" cy="420" rx="110" ry="90"/>
        <text class="num" x="400" y="430">3</text>
        <ellipse class="area" data-num="3" id="rp_cheekR" cx="620" cy="420" rx="110" ry="90"/>
        <text class="num" x="600" y="430">3</text>

        <!-- nariz oscura -->
        <ellipse class="area" data-num="10" id="rp_nose" cx="520" cy="420" rx="46" ry="36"/>
        <text class="num" x="508" y="430">10</text>

        <!-- pata izquierda -->
        <ellipse class="area" data-num="6" id="rp_legL" cx="360" cy="1240" rx="120" ry="160"/>
        <text class="num" x="340" y="1250">6</text>

        <!-- pata derecha -->
        <ellipse class="area" data-num="6" id="rp_legR" cx="680" cy="1240" rx="120" ry="160"/>
        <text class="num" x="660" y="1250">6</text>

        <!-- brazo izquierdo -->
        <ellipse class="area" data-num="6" id="rp_armL" cx="290" cy="860" rx="110" ry="170" transform="rotate(-20 290 860)"/>
        <text class="num" x="260" y="860">6</text>

        <!-- brazo derecho (uniendo mano con mapache) -->
        <ellipse class="area" data-num="6" id="rp_armR" cx="760" cy="860" rx="110" ry="170" transform="rotate(20 760 860)"/>
        <text class="num" x="740" y="860">6</text>

        <!-- cola anillada (varias zonas para más detalle) -->
        <g id="rp_tail" transform="translate(100,1120) rotate(12)">
          <ellipse class="area" data-num="1" cx="930" cy="110" rx="320" ry="140"/>
          <text class="num" x="880" y="120">1</text>
          <rect class="area" data-num="2" x="720" y="30" width="180" height="160" rx="70"/>
          <text class="num" x="760" y="120">2</text>
          <rect class="area" data-num="4" x="910" y="30" width="180" height="160" rx="70"/>
          <text class="num" x="950" y="120">4</text>
          <rect class="area" data-num="2" x="1100" y="30" width="180" height="160" rx="70"/>
          <text class="num" x="1140" y="120">2</text>
        </g>
      </g>

      <!-- ===== Mapache (derecha) ===== -->
      <g id="raccoon" transform="translate(1120,430)">
        <!-- cuerpo -->
        <ellipse class="area" data-num="9" id="rc_body" cx="340" cy="760" rx="380" ry="520"/>
        <text class="num" x="310" y="770">9</text>

        <!-- vientre claro -->
        <ellipse class="area" data-num="5" id="rc_belly" cx="340" cy="1020" rx="240" ry="300"/>
        <text class="num" x="320" y="1040">5</text>

        <!-- cabeza -->
        <circle class="area" data-num="9" id="rc_head" cx="340" cy="380" r="240"/>
        <text class="num" x="310" y="390">9</text>

        <!-- orejas -->
        <ellipse class="area" data-num="5" id="rc_earL" cx="210" cy="190" rx="100" ry="120"/>
        <text class="num" x="195" y="200">5</text>
        <ellipse class="area" data-num="5" id="rc_earR" cx="470" cy="190" rx="100" ry="120"/>
        <text class="num" x="455" y="200">5</text>

        <!-- antifaz oscuro -->
        <ellipse class="area" data-num="10" id="rc_mask" cx="340" cy="380" rx="220" ry="120"/>
        <text class="num" x="320" y="390">10</text>

        <!-- ojos claros -->
        <circle class="area" data-num="5" id="rc_eyeL" cx="270" cy="380" r="50"/>
        <text class="num" x="255" y="390">5</text>
        <circle class="area" data-num="5" id="rc_eyeR" cx="410" cy="380" r="50"/>
        <text class="num" x="395" y="390">5</text>

        <!-- nariz -->
        <ellipse class="area" data-num="10" id="rc_nose" cx="340" cy="440" rx="36" ry="28"/>
        <text class="num" x="330" y="448">10</text>

        <!-- patas -->
        <ellipse class="area" data-num="8" id="rc_legL" cx="210" cy="1240" rx="110" ry="160"/>
        <text class="num" x="190" y="1250">8</text>
        <ellipse class="area" data-num="8" id="rc_legR" cx="470" cy="1240" rx="110" ry="160"/>
        <text class="num" x="450" y="1250">8</text>

        <!-- brazos (uniendo mano con panda) -->
        <ellipse class="area" data-num="8" id="rc_armL" cx="100" cy="860" rx="100" ry="160" transform="rotate(-18 100 860)"/>
        <text class="num" x="80" y="860">8</text>
        <ellipse class="area" data-num="8" id="rc_armR" cx="570" cy="860" rx="100" ry="160" transform="rotate(18 570 860)"/>
        <text class="num" x="550" y="860">8</text>

        <!-- cola anillada -->
        <g id="rc_tail" transform="translate(200,1120) rotate(-8)">
          <ellipse class="area" data-num="9" cx="120" cy="110" rx="320" ry="140"/>
          <text class="num" x="70" y="120">9</text>
          <rect class="area" data-num="10" x="-60" y="30" width="170" height="160" rx="70"/>
          <text class="num" x="-15" y="120">10</text>
          <rect class="area" data-num="7" x="110" y="30" width="170" height="160" rx="70"/>
          <text class="num" x="150" y="120">7</text>
          <rect class="area" data-num="10" x="280" y="30" width="170" height="160" rx="70"/>
          <text class="num" x="320" y="120">10</text>
        </g>

        <!-- manitas unidas -->
        <ellipse class="area" data-num="4" id="hands_join" cx="-140" cy="940" rx="90" ry="70"/>
        <text class="num" x="-165" y="950">4</text>
      </g>
    </svg>
  </main>
</div>

<script>
/* ===== Configuración de colores ===== */
const COLORS = {
  1:"#e25544", // rojo panda
  2:"#f39c12", // naranja anillo
  3:"#f8e9c9", // crema claro
  4:"#ffd166", // amarillo cálido
  5:"#d6e6ff", // celeste muy claro
  6:"#39558a", // azul oscuro (patas panda)
  7:"#9b59b6", // púrpura (detalle cola mapache)
  8:"#566c86", // gris azulado (brazos/patas mapache)
  9:"#95a5a6", // gris cuerpo mapache
 10:"#2e3440"  // oscuro (nariz/antifaz)
};

/* ===== Construir paleta y leyenda ===== */
const palette = document.getElementById('palette');
const legend  = document.getElementById('legend');
let current = null;

Object.entries(COLORS).forEach(([num,color],i)=>{
  const b=document.createElement('button');
  b.className='sw'; b.style.background=color; b.textContent=num;
  b.onclick=()=>{ document.querySelectorAll('.sw').forEach(s=>s.classList.remove('active')); b.classList.add('active'); current=num; };
  if(i===0){ b.classList.add('active'); current=num; }
  palette.appendChild(b);

  const row=document.createElement('div');
  const dot=document.createElement('b'); dot.style.background=color; dot.textContent=num;
  const label=document.createElement('span'); label.textContent=`Zona número ${num}`;
  row.append(dot,label); legend.appendChild(row);
});

/* ===== Lógica de pintado ===== */
const board = document.getElementById('board');
const areas = Array.from(board.querySelectorAll('.area'));
const progressEl = document.getElementById('progress');
const qrLayer = document.getElementById('qr');
const total = areas.length;

areas.forEach(a=>{
  a.addEventListener('click', ()=>{
    if(!current) return;
    const needs = a.getAttribute('data-num');
    if(String(current)===String(needs)){
      a.style.fill = COLORS[needs];
      a.setAttribute('data-done','1');
      checkDone();
    }else{
      a.classList.remove('wrong'); // reset anim
      void a.offsetWidth;          // reflow
      a.classList.add('wrong');    // shake
    }
  }, false);
});

function checkDone(){
  const done = areas.filter(a=>a.getAttribute('data-done')==='1').length;
  progressEl.textContent = `Progreso: ${done} / ${total} zonas`;
  if(done===total){ qrLayer.style.display='grid'; }
}

/* ===== Controles ===== */
document.getElementById('reset').onclick=()=>{
  areas.forEach(a=>{ a.style.fill='transparent'; a.removeAttribute('data-done'); });
  qrLayer.style.display='none';
  current = Object.keys(COLORS)[0];
  document.querySelectorAll('.sw').forEach((s,i)=>s.classList.toggle('active',i===0));
  checkDone();
};
const boardRoot = document.getElementById('board');
let numsHidden=false;
document.getElementById('toggleNums').onclick=()=>{
  numsHidden = !numsHidden;
  boardRoot.classList.toggle('hiddenNums', numsHidden);
};

checkDone();
</script>
</body>
</html>
