TE AMO
<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>🎂 Feliz 26 — Para Mi Amor</title>
  <!-- Tarjeta virtual 26: un solo archivo HTML/CSS/JS, sin librerías externas -->
  <style>
    :root{
      /* Personaliza la paleta */
      --bg1:#0f1025; --bg2:#2b2a66; --accent:#ffd166; --love:#ff477e; --ink:#fff8fb;
      --card:#ffffff14; --glass:#ffffff19; --stroke:#ffffff33;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0; color:var(--ink); font-family: system-ui, -apple-system, Segoe UI, Roboto, "Helvetica Neue", Arial;
      background: radial-gradient(1000px 800px at 50% 110%, #8c2eff33, transparent 60%),
                  linear-gradient(160deg,var(--bg1),var(--bg2));
      overflow-x:hidden;
    }

    /* Fondo con estrellas suaves */
    .stars{position:fixed; inset:0; pointer-events:none; background-image:radial-gradient(#ffffff 0.8px,transparent 1px); background-size:3px 3px; opacity:.25; filter:drop-shadow(0 0 3px #fff)}

    /* Contenedor */
    .wrap{min-height:100dvh; display:grid; place-items:center; padding:clamp(12px,3vw,28px)}

    /* Tarjeta principal */
    .card{position:relative; width:min(1000px,92vw); border-radius:28px; padding:clamp(18px,5vw,44px); backdrop-filter: blur(10px) saturate(130%);
      background:linear-gradient(180deg,var(--glass),#ffffff0e); border:1px solid var(--stroke); box-shadow:0 20px 80px #0008, inset 0 0 30px #ffffff12; overflow:hidden}

    /* Encabezado */
    .top{display:flex; align-items:center; justify-content:space-between; gap:12px; margin-bottom:12px}
    .badge{display:inline-flex; align-items:center; gap:8px; border:1px solid var(--stroke); background:#ffffff12; padding:8px 12px; border-radius:999px; font-weight:700}
    .controls{display:flex; gap:8px}
    .btn{border:1px solid var(--stroke); background:#ffffff12; color:var(--ink); padding:10px 14px; border-radius:999px; font-weight:700; cursor:pointer; transition:.15s}
    .btn:hover{transform:translateY(-1px) scale(1.02); background:#ffffff22}

    /* Hero con número 26 */
    .hero{position:relative; display:grid; place-items:center; padding:28px 0 18px 0}
    .num{font-size: clamp(80px, 22vw, 220px); line-height:.9; font-weight:900; letter-spacing: -6px; position:relative; text-shadow:0 10px 40px #0008}
    .num .fill{background: linear-gradient(180deg, #fff, #ffe2a8 60%, #fffa 70%);
      -webkit-background-clip:text; background-clip:text; color:transparent; filter: drop-shadow(0 0 30px #ffd16660)}
    .num::after{content:""; position:absolute; inset:-6px; border-radius:18px; background: conic-gradient(from 120deg, #fff0 0 70%, #ffd16644 85%, #fff0 100%);
      filter:blur(24px); opacity:.7; pointer-events:none}

    .love{display:flex; align-items:center; gap:10px; margin-top:6px; font-weight:800; letter-spacing:1.4px; text-transform:uppercase}
    .heart{width:22px; height:22px; display:inline-block; background:var(--love); transform: rotate(45deg); border-radius:4px; position:relative; box-shadow:0 4px 18px #ff477e66}
    .heart::before,.heart::after{content:""; position:absolute; width:22px; height:22px; background:var(--love); border-radius:50%}
    .heart::before{left:-11px}
    .heart::after{top:-11px}
    .pulse{animation:pulse 1.6s ease-in-out infinite}
    @keyframes pulse{0%,100%{transform:scale(1)}50%{transform:scale(1.08)}}

    /* Secciones */
    .grid{display:grid; grid-template-columns:1fr; gap:16px; margin-top:20px}
    @media(min-width:820px){.grid{grid-template-columns:1.2fr .8fr}}
    .panel{border:1px solid var(--stroke); background:#ffffff10; border-radius:22px; padding:16px 16px}

    .title{font-size:clamp(18px,2.4vw,26px); margin:0 0 8px 0}
    .lead{font-size:clamp(14px,2vw,18px); opacity:.9}

    /* Galería simple */
    .gallery{display:grid; grid-template-columns:repeat(2,1fr); gap:10px; margin-top:8px}
    @media(min-width:620px){.gallery{grid-template-columns:repeat(3,1fr)}}
    .ph{position:relative; aspect-ratio:1; border-radius:16px; overflow:hidden; background:#ffffff12; border:1px dashed #ffffff44; display:grid; place-items:center; font-weight:700}
    .ph img{position:absolute; inset:0; width:100%; height:100%; object-fit:cover}

    /* Carta desplegable */
    details{border:1px solid var(--stroke); background:#ffffff0f; border-radius:16px; padding:12px 14px}
    summary{cursor:pointer; font-weight:800; letter-spacing:.5px}
    .note{margin:8px 0 0 0; line-height:1.6}

    /* Footer */
    .foot{display:flex; flex-wrap:wrap; gap:10px; justify-content:center; margin-top:16px}

    /* Confeti canvas */
    #confetti{position:fixed; inset:0; pointer-events:none; z-index:2}

    /* Modal de portada */
    .cover{position:fixed; inset:0; display:grid; place-items:center; background:radial-gradient(1200px 900px at 50% 120%, #ff4d6d22, transparent 60%), linear-gradient(160deg,var(--bg1),var(--bg2)); z-index:10}
    .cover .inner{width:min(720px,92vw); text-align:center; padding:34px; border-radius:28px; border:1px solid var(--stroke); background:linear-gradient(180deg,var(--glass),#ffffff12); box-shadow:0 20px 80px #0008}
    .cover h1{margin:0 0 10px 0; font-size: clamp(26px,6vw,44px)}
    .cover p{opacity:.92; margin:.4rem 0 1.2rem}
    .big-cta{font-size:clamp(16px,3.8vw,20px); padding:14px 18px}

    .hint{font-size:12px; opacity:.7; margin-top:8px}

    /* Tooltip mínimo */
    .tip{position:relative}
    .tip:hover::after{content:attr(data-tip); position:absolute; bottom:calc(100% + 6px); left:50%; transform:translateX(-50%); background:#000b; color:#fff; padding:6px 8px; border-radius:8px; font-size:12px; white-space:nowrap}
  </style>
</head>
<body>
  <canvas id="confetti"></canvas>
  <div class="stars"></div>

  <!-- Portada para abrir la tarjeta -->
  <div class="cover" id="cover">
    <div class="inner">
      <h1>Feliz cumpleaños <br>🎉<span id="nameCover">Hillary</span> 🎉</h1>
      <p>Preparé algo especial para celebrar tu día. Toca el botón para abrir tu tarjeta 💌</p>
      <button class="btn big-cta" id="openBtn">Abrir mi tarjeta</button>
      <div class="hint">Puedes activar música y lanzar confeti dentro ✨</div>
    </div>
  </div>

  <div class="wrap">
    <div class="card">
      <div class="top">
        <div class="badge">🎂 Cumple 26 • <span id="name">Hillary</span></div>
        <div class="controls">
          <button class="btn tip" id="partyBtn" data-tip="Lanzar confeti">🎉</button>
          <button class="btn tip" id="musicBtn" data-tip="Música on/off">🎵</button>
        </div>
      </div>

      <div class="hero">
        <div class="num"><span class="fill">26</span></div>
        <div class="love"><span class="heart pulse"></span><span id="loveText">TE AMO</span></div>
      </div>

      <div class="grid">
        <section class="panel">
          <h3 class="title">Para ti, amor</h3>
          <p class="lead" id="message">Hoy celebro tu vida, tu risa y lo increíble que eres. Gracias por cada momento. Que este nuevo año te traiga aventuras, salud y mucha felicidad. 💖</p>
          <details>
            <summary>Leer una cartita 💌</summary>
            <div class="note" id="letter">
              Mi vida,
              <br><br>
              Desde que te conocí, mis días son más bonitos. Admiro tu fuerza, tu ternura y todo lo que sueñas. Que a los 26 cumplas metas que aún no imaginas; yo estaré a tu lado para celebrarlas.
              <br><br>
              Con todo mi amor,
              <br>
              — Tu persona favorita 🫶
            </div>
          </details>
        </section>

        <aside class="panel">
          <h3 class="title">Momentos</h3>
          <div class="gallery" id="gallery">
            <!-- Reemplaza src por tus fotos (mis-fotos/1.jpg, etc.) -->
            <div class="ph"><img alt="" src="1.jpeg" onerror="this.replaceWith(ph())"></div>
            <div class="ph"><img alt="" src="2.jpeg" onerror="this.replaceWith(ph())"></div>
            <div class="ph"><img alt="" src="3.jpeg" onerror="this.replaceWith(ph())"></div>
            <div class="ph"><img alt="" src="4.jpeg" onerror="this.replaceWith(ph())"></div>
            <div class="ph"><img alt="" src="5.jpeg" onerror="this.replaceWith(ph())"></div>
            <div class="ph"><img alt="" src="6.jpeg" onerror="this.replaceWith(ph())"></div>
            <div class="ph"><img alt="" src="7.jpeg" onerror="this.replaceWith(ph())"></div>
            <div class="ph"><img alt="" src="8.jpeg" onerror="this.replaceWith(ph())"></div>
            <div class="ph"><img alt="" src="9.jpeg" onerror="this.replaceWith(ph())"></div>
          </div>
        </aside>
      </div>

      <div class="foot">
        <button class="btn" id="toastBtn">Brindis 🥂</button>
        <button class="btn" id="colorBtn">Cambiar colores 🎨</button>
      </div>
    </div>
  </div>

  <audio id="song" preload="auto">
    <!-- Reemplaza por tu archivo: <source src="musica.mp3" type="audio/mpeg"> -->
  </audio>

  <script>
    /* =====================
       PERSONALIZA ACÁ 👇
       ===================== */
    const DATA = {
      nombre: 'Mi ChiKisTrikis',
      edad: 26,
      mensaje: 'Hoy celebro tu vida, tu risa y lo increíble que eres. Gracias por cada momento. Que este nuevo año te traiga aventuras, salud y mucha felicidad. 💖',
      carta: `Mi vida,\n\nDesde que te conocí, mis días son más bonitos. Admiro tu fuerza, tu ternura y todo lo que sueñas. Que a los 26 cumplas metas que aún no imaginas; yo estaré a tu lado para celebrarlas.\n\nCon todo mi amor,\n— Tu persona favorita 🫶`,
      whatsapp: '+50578517528', // ← cambia al número de tu novia (con código de país)
      musica: 'por primera vez.mp3', // ejemplo: 'musica.mp3'
      paletas: [
        ['#0f1025','#2b2a66','#ffd166','#ff477e'],
        ['#0b3e27','#0a2a6a','#47ffd1','#ff5d8f'],
        ['#2d0a31','#5d0f40','#ffd3ba','#ff4d6d'],
        ['#071952','#0b666a','#ffd166','#ff2e63'],
      ]
    }

    // Pintar nombre, textos y música
    const nameEls = [document.getElementById('name'), document.getElementById('nameCover')];
    nameEls.forEach(el=> el.textContent = DATA.nombre);
    document.getElementById('message').textContent = DATA.mensaje;
    document.getElementById('letter').innerText = DATA.carta;
    const audio = document.getElementById('song');
    if(DATA.musica){
      const src = document.createElement('source'); src.src = DATA.musica; src.type = 'audio/mpeg'; audio.appendChild(src);
    }
    // Confeti
    const canvas = document.getElementById('confetti'); const ctx = canvas.getContext('2d'); const DPR = Math.min(devicePixelRatio||1,2);
    let W,H; function R(){W=canvas.width=Math.floor(innerWidth*DPR); H=canvas.height=Math.floor(innerHeight*DPR);} addEventListener('resize',R,{passive:true}); R();
    const colors = ['#FFD166','#06D6A0','#118AB2','#EF476F','#F7B801','#A8E6CF','#9B5DE5','#00D1FF'];
    const pieces=[]; class P{constructor(x,y){this.x=x;this.y=y;this.vx=(Math.random()-.5)*6;this.vy=Math.random()*-8-6;this.s=Math.random()*8+4;this.c=colors[Math|Math.random()*colors.length];this.r=Math.random()*Math.PI;this.vr=(Math.random()-.5)*.2;this.life=0}
      step(){this.vy+=.22; this.x+=this.vx; this.y+=this.vy; this.r+=this.vr; this.life++}
      draw(){ctx.save(); ctx.globalAlpha=Math.max(0,1-this.life/220); ctx.translate(this.x,this.y); ctx.rotate(this.r); ctx.fillStyle=this.c; if(Math.random()<.5){ctx.fillRect(-this.s/2,-this.s/2,this.s,this.s*.6)} else {ctx.beginPath(); ctx.arc(0,0,this.s/2,0,Math.PI*2); ctx.fill()} ctx.restore()} }
    function boom(n=80,x=W/2,y=H*.35){for(let i=0;i<n;i++) pieces.push(new P(x,y))}
    (function loop(){ctx.clearRect(0,0,W,H); for(let i=pieces.length-1;i>=0;i--){const p=pieces[i]; p.step(); p.draw(); if(p.y>H+80||p.x<-80||p.x>W+80||p.life>260) pieces.splice(i,1)} requestAnimationFrame(loop)})()

    // Portada abrir
    const cover = document.getElementById('cover');
    document.getElementById('openBtn').addEventListener('click', ()=>{ cover.style.display='none'; boom(140); playMusic(); });

    // Botones
    document.getElementById('partyBtn').addEventListener('click', ()=> boom(140, Math.random()*W, Math.random()*H*.5 + H*.1));
    document.getElementById('toastBtn').addEventListener('click', ()=>{ toast(`Por tus ${DATA.edad}, por nosotros y por todo lo bonito que viene 🥂`); boom(100)});
    document.getElementById('musicBtn').addEventListener('click', toggleMusic);
    document.getElementById('colorBtn').addEventListener('click', cyclePalette);
    document.getElementById('shareBtn').addEventListener('click', shareCard);

    // Tocar/click para chispas
    addEventListener('click', e=> sparkle(e.clientX, e.clientY));
    addEventListener('touchstart', e=>{ const t=e.touches[0]; sparkle(t.clientX,t.clientY)}, {passive:true});

    // Sparkle
    function sparkle(x,y){ const n=16+Math.floor(Math.random()*12); const u=document.createDocumentFragment(); for(let i=0;i<n;i++){ const d=document.createElement('div'); d.className='pop'; d.style.cssText=`position:fixed;left:${x}px;top:${y}px;width:10px;height:10px;border-radius:50%;mix-blend-mode:screen;background:${colors[Math|Math.random()*colors.length]};opacity:.95;transform:translate(-50%,-50%);animation:pop 700ms ease-out forwards`; document.body.appendChild(d); setTimeout(()=>d.remove(),800) } boom(36,x*DPR,y*DPR) }

    // Anim pop keyframes (inyectamos para compatibilidad)
    const style = document.createElement('style'); style.textContent = `@keyframes pop{to{opacity:0; transform:translate(-50%,-50%) scale(6); filter:blur(2px)}}`; document.head.appendChild(style);

    // Galería placeholders
    function ph(){ const wrap=document.createElement('div'); wrap.className='ph'; wrap.textContent='Foto'; return wrap }

    // Toast minimalista
    function toast(text){
      const t=document.createElement('div'); t.textContent=text; t.style.cssText='position:fixed;left:50%;bottom:26px;transform:translateX(-50%);background:#000c;color:#fff;padding:10px 14px;border-radius:999px;border:1px solid #ffffff33;z-index:5;box-shadow:0 6px 30px #0008'; document.body.appendChild(t); setTimeout(()=>t.remove(),3000)
    }

    // Música
    function playMusic(){ if(!DATA.musica) return; audio.volume=.8; audio.loop=true; audio.play().catch(()=>{}) }
    function toggleMusic(){ if(!DATA.musica) { toast('Agrega un archivo de música en DATA.musica'); return } if(audio.paused){audio.play(); toast('Música ▶️')} else {audio.pause(); toast('Música ⏸️')} }

    // Paletas de color
    let palIndex=0; function applyPalette([bg1,bg2,accent,love]){ const r=document.documentElement; r.style.setProperty('--bg1',bg1); r.style.setProperty('--bg2',bg2); r.style.setProperty('--accent',accent); r.style.setProperty('--love',love) }
    function cyclePalette(){ palIndex=(palIndex+1)%DATA.paletas.length; applyPalette(DATA.paletas[palIndex]); boom(80) }

    // Compartir
    async function shareCard(){ const data={ title:`Feliz ${DATA.edad} ${DATA.nombre}`, text:`Te hice esta tarjeta 💌`, url:location.href }; if(navigator.share){ try{ await navigator.share(data) }catch{} } else { navigator.clipboard.writeText(location.href); toast('Enlace copiado 📋') } }

    // Ajustes iniciales
    applyPalette(DATA.paletas[0]);
  </script>
</body>
</html>
