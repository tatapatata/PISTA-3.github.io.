<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Pinta por Números</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background: #111827;
      color: white;
      margin: 0;
    }
    canvas {
      border: 2px solid #444;
      margin-top: 20px;
      max-width: 95vw;
      height: auto;
    }
    .palette {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      margin: 20px 0;
    }
    .color-btn {
      width: 40px;
      height: 40px;
      border: 2px solid white;
      border-radius: 50%;
      margin: 5px;
      cursor: pointer;
    }
    #message {
      margin-top: 20px;
      font-size: 1.2em;
      font-weight: bold;
      color: #FFD700;
    }
    #qr {
      display: none;
      margin: 20px auto;
      width: 200px;
    }
  </style>
</head>
<body>
  <h1>🎨 Pinta por números</h1>
  <p>Toca o haz clic en las áreas y usa los colores correctos.<br>
     Cuando completes el dibujo, aparecerá la sorpresa ✨</p>

  <canvas id="paintCanvas" width="800" height="800"></canvas>

  <div class="palette">
    <button class="color-btn" style="background:#E66A28;" data-color="#E66A28" data-num="1"></button>
    <button class="color-btn" style="background:#F28C34;" data-color="#F28C34" data-num="2"></button>
    <button class="color-btn" style="background:#F5D9A1;" data-color="#F5D9A1" data-num="3"></button>
    <button class="color-btn" style="background:#FFF2C9;" data-color="#FFF2C9" data-num="4"></button>
    <button class="color-btn" style="background:#A8C1D9;" data-color="#A8C1D9" data-num="5"></button>
    <button class="color-btn" style="background:#6B7A8F;" data-color="#6B7A8F" data-num="6"></button>
    <button class="color-btn" style="background:#424B54;" data-color="#424B54" data-num="7"></button>
    <button class="color-btn" style="background:#D4A373;" data-color="#D4A373" data-num="8"></button>
    <button class="color-btn" style="background:#8C6E63;" data-color="#8C6E63" data-num="9"></button>
    <button class="color-btn" style="background:#000;" data-color="#000" data-num="10"></button>
  </div>

  <div id="message"></div>
  <img id="qr" src="https://i.ibb.co/yp3dqR8/qr.png" alt="QR Code">

  <script>
    const canvas = document.getElementById("paintCanvas");
    const ctx = canvas.getContext("2d");

    let selectedColor = null;
    let paintedAreas = 0;
    const totalAreas = 20; // cantidad de zonas para pintar

    // Simulación del dibujo dividido en áreas numeradas
    const areas = [
      {x:150,y:200,w:200,h:200,num:1},
      {x:350,y:200,w:200,h:200,num:2},
      {x:550,y:200,w:200,h:200,num:3},
      {x:150,y:400,w:200,h:200,num:4},
      {x:350,y:400,w:200,h:200,num:5},
      {x:550,y:400,w:200,h:200,num:6},
      {x:250,y:600,w:200,h:200,num:7},
      {x:450,y:600,w:200,h:200,num:8},
      {x:100,y:100,w:100,h:100,num:9},
      {x:600,y:100,w:100,h:100,num:10},
      // repite más para simular
    ];

    // Dibujar áreas
    function drawAreas() {
      ctx.clearRect(0,0,canvas.width,canvas.height);
      ctx.fillStyle = "#fff";
      ctx.fillRect(0,0,canvas.width,canvas.height);

      areas.forEach(area => {
        ctx.strokeStyle = "#000";
        ctx.strokeRect(area.x,area.y,area.w,area.h);
        ctx.fillStyle = "#000";
        ctx.font = "20px Arial";
        ctx.fillText(area.num, area.x+area.w/2-5, area.y+area.h/2+5);
      });
    }

    drawAreas();

    // Selección de color
    document.querySelectorAll(".color-btn").forEach(btn => {
      btn.addEventListener("click", () => {
        selectedColor = { color: btn.dataset.color, num: parseInt(btn.dataset.num)};
      });
    });

    // Pintar al hacer clic
    canvas.addEventListener("click", e => {
      const rect = canvas.getBoundingClientRect();
      const x = e.clientX - rect.left;
      const y = e.clientY - rect.top;

      areas.forEach(area => {
        if(x>area.x && x<area.x+area.w && y>area.y && y<area.y+area.h){
          if(selectedColor && selectedColor.num===area.num && !area.filled){
            ctx.fillStyle = selectedColor.color;
            ctx.fillRect(area.x, area.y, area.w, area.h);
            area.filled = true;
            paintedAreas++;
            checkCompletion();
          }
        }
      });
    });

    function checkCompletion(){
      if(paintedAreas >= areas.length){
        document.getElementById("message").innerText = "¡Felicidades! Has completado el dibujo 🎉";
        document.getElementById("qr").style.display = "block";
      }
    }
  </script>
</body>
</html>
