<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1.0" />
  <title>Valentine Proposal Card</title>

  <style>
    :root{
      --bg1:#120018;
      --bg2:#22003a;
      --pink:#ff3b93;
      --pink2:#ff86c2;
      --text:#fff;
    }
    *{ box-sizing:border-box; margin:0; padding:0; font-family: system-ui, -apple-system, Segoe UI, Roboto, Arial; }
    body{
      height:100vh;
      display:flex;
      justify-content:center;
      align-items:center;
      background: radial-gradient(circle at 20% 20%, #3b004f, transparent 40%),
                  radial-gradient(circle at 80% 30%, #ff2f85, transparent 35%),
                  linear-gradient(135deg, var(--bg1), var(--bg2));
      overflow:hidden;
      color:var(--text);
    }

    /* Floating 3D hearts background */
    .hearts-bg{
      position:fixed; inset:0;
      pointer-events:none;
      overflow:hidden;
      perspective:900px;
    }
    .heart3d{
      position:absolute;
      width:26px; height:26px;
      background: linear-gradient(135deg, var(--pink), var(--pink2));
      transform: rotate(45deg);
      border-radius: 6px;
      filter: drop-shadow(0 10px 18px rgba(255, 0, 120, .35));
      opacity:.75;
      animation: floatUp var(--dur) linear infinite;
    }
    .heart3d::before, .heart3d::after{
      content:"";
      position:absolute;
      width:26px; height:26px;
      background: inherit;
      border-radius:50%;
    }
    .heart3d::before{ left:-13px; top:0; }
    .heart3d::after{ left:0; top:-13px; }
    @keyframes floatUp{
      0%{ transform: translate3d(0, 120vh, -200px) rotate(45deg); }
      100%{ transform: translate3d(var(--dx), -30vh, 220px) rotate(45deg); }
    }

    /* Card container */
    .wrap{
      width:min(520px, 92vw);
      perspective: 1400px;
      position:relative;
      z-index:2;
    }

    .card{
      width:100%;
      min-height:390px;
      position:relative;
      transform-style:preserve-3d;
      transition: transform 1.1s cubic-bezier(.2,.8,.2,1);
      border-radius:22px;
    }

    .panel{
      position:absolute;
      inset:0;
      padding:26px;
      border-radius:22px;
      background: linear-gradient(180deg, rgba(255,255,255,.10), rgba(255,255,255,.06));
      border: 1px solid rgba(255,255,255,.18);
      backdrop-filter: blur(16px);
      box-shadow: 0 30px 70px rgba(0,0,0,.45);
      transform-style:preserve-3d;
      overflow:hidden;
    }

    .front{
      transform: translateZ(2px);
      display:flex;
      align-items:center;
      justify-content:center;
      flex-direction:column;
      gap:14px;
      text-align:center;
    }

    .inside{
      transform: rotateY(180deg) translateZ(2px);
      display:flex;
      align-items:center;
      justify-content:center;
      flex-direction:column;
      gap:14px;
      text-align:center;
    }

    /* 3D shine */
    .shine{
      position:absolute;
      inset:-60%;
      background: radial-gradient(circle at 30% 20%, rgba(255,255,255,.25), transparent 40%),
                  radial-gradient(circle at 70% 80%, rgba(255,59,147,.20), transparent 45%);
      transform: translateZ(30px);
      pointer-events:none;
      animation: shineMove 5s ease-in-out infinite;
      mix-blend-mode: screen;
    }
    @keyframes shineMove{
      0%,100%{ transform: translateZ(30px) translateX(-2%) rotate(0deg); }
      50%{ transform: translateZ(30px) translateX(2%) rotate(1deg); }
    }

    .title{
      font-size: clamp(22px, 4vw, 36px);
      font-weight: 900;
      text-shadow: 0 14px 25px rgba(0,0,0,.35);
    }
    .sub{ opacity:.9; font-size: 15px; }

    .btn{
      border:none;
      padding: 12px 18px;
      border-radius: 14px;
      font-weight: 900;
      cursor:pointer;
      transition: transform .18s ease, filter .18s ease;
      color:white;
      box-shadow: 0 14px 26px rgba(0,0,0,.30);
      user-select:none;
      transform: translateZ(20px);
    }
    .btn:active{ transform: translateZ(20px) scale(.96); }
    .btn:hover{ filter:brightness(1.05); }

    .btn-open{
      background: linear-gradient(135deg, #ff3b93, #ff86c2);
      font-size: 16px;
    }
    .btn-yes{
      background: linear-gradient(135deg, #00d68f, #46ffd1);
      color:#071c14;
    }
    .btn-no{
      background: linear-gradient(135deg, #ff2d2d, #ff7c7c);
    }

    /* Big heart */
    .big-heart{
      width:120px;height:120px;
      position:relative;
      transform: translateZ(40px);
      margin-bottom: 8px;
      animation: pulse 1.6s ease-in-out infinite;
    }
    .big-heart::before,.big-heart::after{
      content:"";
      position:absolute;
      width:70px;height:110px;
      background: linear-gradient(135deg, var(--pink), var(--pink2));
      border-radius: 70px 70px 10px 10px;
      top:0;left:35px;
      transform: rotate(-45deg);
      transform-origin: 0 100%;
      box-shadow: 0 18px 40px rgba(255,59,147,.35);
    }
    .big-heart::after{
      left:15px;
      transform: rotate(45deg);
      transform-origin: 100% 100%;
    }
    @keyframes pulse{
      0%,100%{ transform: translateZ(40px) scale(1); }
      50%{ transform: translateZ(40px) scale(1.06); }
    }

    .actions{
      display:flex;
      gap:14px;
      justify-content:center;
      flex-wrap:wrap;
      margin-top: 12px;
    }

    /* NO area */
    .no-area{
      position:relative;
      width:240px;
      height:120px;
      display:flex;
      align-items:center;
      justify-content:center;
    }
    .btn-no{ position:absolute; }

    /* NO attempt messages */
    .no-msg{
      min-height: 22px;
      font-weight:900;
      font-size: 15px;
      opacity: 0;
      transform: translateY(6px);
      transition: opacity .25s ease, transform .25s ease;
      text-shadow: 0 12px 22px rgba(0,0,0,.4);
    }
    .no-msg.show{
      opacity: 1;
      transform: translateY(0px);
    }

    .hint{ margin-top:8px; font-size:13px; opacity:.85; }

    /* Final fireworks screen */
    .final{
      position:fixed;
      inset:0;
      display:none;
      align-items:center;
      justify-content:center;
      flex-direction:column;
      gap:14px;
      z-index:9;
      background: radial-gradient(circle at 50% 20%, rgba(255,255,255,.10), transparent 50%),
                  radial-gradient(circle at 30% 80%, rgba(255,59,147,.25), transparent 45%),
                  linear-gradient(135deg, #080011, #22003a);
    }
    .final h1{
      font-size: clamp(30px, 6vw, 64px);
      text-align:center;
      text-shadow: 0 20px 40px rgba(0,0,0,.45);
    }
    canvas{
      position:absolute;
      inset:0;
      width:100%;
      height:100%;
    }

    /* Flip */
    .card.open{ transform: rotateY(180deg); }
  </style>
</head>

<body>
  <div class="hearts-bg" id="heartsBg"></div>

  <div class="wrap">
    <div class="card" id="card">
      <!-- FRONT -->
      <div class="panel front">
        <div class="shine"></div>
        <div class="big-heart"></div>
        <div class="title">Valentine Card 💌</div>
        <div class="sub">Tap to open</div>
        <button class="btn btn-open" id="openBtn">Click → Open Card</button>
        <div class="hint">Premium 3D theme ✨</div>
      </div>

      <!-- INSIDE -->
      <div class="panel inside">
        <div class="shine"></div>
        <div class="title">Will you be my Valentine? 💖</div>

        <div class="actions">
          <button class="btn btn-yes" id="yesBtn">✅ YES</button>

          <div class="no-area" id="noArea">
            <button class="btn btn-no" id="noBtn">❌ NO</button>
          </div>
        </div>

        <div class="no-msg" id="noMsg"></div>
        <div class="hint">Try pressing “NO” 😄</div>
      </div>
    </div>
  </div>

  <!-- FINAL -->
  <div class="final" id="finalScreen">
    <canvas id="fw"></canvas>
    <h1>I knew it ❤️</h1>
    <div class="hint">Happy Valentine’s Day ✨</div>
  </div>

  <script>
    /* Floating hearts */
    const heartsBg = document.getElementById("heartsBg");
    const HEARTS = 22;
    for (let i = 0; i < HEARTS; i++) {
      const h = document.createElement("div");
      h.className = "heart3d";
      h.style.left = (Math.random() * 100) + "vw";
      h.style.setProperty("--dur", (7 + Math.random() * 7) + "s");
      h.style.setProperty("--dx", ((Math.random() * 120 - 60).toFixed(1)) + "px");
      h.style.animationDelay = (-(Math.random() * 6)) + "s";
      h.style.opacity = (0.45 + Math.random() * 0.45).toFixed(2);
      heartsBg.appendChild(h);
    }

    /* Card open */
    const card = document.getElementById("card");
    document.getElementById("openBtn").addEventListener("click", () => {
      card.classList.add("open");
    });

    /* NO runaway + messages */
    const noBtn = document.getElementById("noBtn");
    const noArea = document.getElementById("noArea");
    const noMsg = document.getElementById("noMsg");

    const noTexts = [
      "Think again 😏",
      "Are you sure? 💘",
      "One more chance 🥺",
      "Don’t break my heart 💔",
      "Wrong button 😄",
      "Say YES please 😌",
      "Reconsider 👀",
      "Come on... YES 😍"
    ];
    let noCount = 0;

    function showNoText(){
      noMsg.textContent = noTexts[noCount % noTexts.length];
      noCount++;
      noMsg.classList.add("show");
      clearTimeout(window.__noTimer);
      window.__noTimer = setTimeout(()=> noMsg.classList.remove("show"), 1200);
    }

    function runaway(){
      const rect = noArea.getBoundingClientRect();
      const btnW = noBtn.offsetWidth;
      const btnH = noBtn.offsetHeight;

      const x = Math.random() * (rect.width - btnW);
      const y = Math.random() * (rect.height - btnH);

      noBtn.style.transform = `translate(${x}px, ${y}px) translateZ(20px)`;
    }

    noBtn.addEventListener("mouseenter", () => { showNoText(); runaway(); });
    noBtn.addEventListener("click", (e) => { e.preventDefault(); showNoText(); runaway(); });
    noBtn.addEventListener("touchstart", (e) => {
      e.preventDefault();
      showNoText();
      runaway();
    }, { passive:false });

    /* YES -> fireworks */
    const finalScreen = document.getElementById("finalScreen");
    document.getElementById("yesBtn").addEventListener("click", () => {
      finalScreen.style.display = "flex";
      startFireworks();
    });

    /* Fireworks Canvas */
    const canvas = document.getElementById("fw");
    const ctx = canvas.getContext("2d");

    function resize(){
      canvas.width = window.innerWidth;
      canvas.height = window.innerHeight;
    }
    window.addEventListener("resize", resize);
    resize();

    let particles = [];
    let animId;

    function burst(x, y){
      const count = 70;
      for(let i=0;i<count;i++){
        const angle = Math.random() * Math.PI * 2;
        const speed = 2 + Math.random() * 5;
        particles.push({
          x, y,
          vx: Math.cos(angle)*speed,
          vy: Math.sin(angle)*speed,
          life: 90 + Math.random()*30,
          size: 1 + Math.random()*2.5,
          hue: 300 + Math.random()*60
        });
      }
    }

    function startFireworks(){
      if(animId) cancelAnimationFrame(animId);
      let t=0;

      function loop(){
        animId = requestAnimationFrame(loop);
        ctx.fillStyle = "rgba(0,0,0,0.16)";
        ctx.fillRect(0,0,canvas.width,canvas.height);

        t++;
        if(t%18===0){
          burst(
            Math.random()*canvas.width*0.8 + canvas.width*0.1,
            Math.random()*canvas.height*0.45 + canvas.height*0.05
          );
        }

        particles.forEach(p=>{
          p.x += p.vx;
          p.y += p.vy;
          p.vy += 0.03;
          p.life -= 1;

          ctx.beginPath();
          ctx.fillStyle = `hsla(${p.hue},100%,65%,${Math.max(p.life/120,0)})`;
          ctx.arc(p.x,p.y,p.size,0,Math.PI*2);
          ctx.fill();
        });

        particles = particles.filter(p=>p.life>0);
      }
      loop();
    }
  </script>
</body>
</html>
