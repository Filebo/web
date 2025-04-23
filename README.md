<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Mi Windows 93</title>
  <link rel="shortcut icon" type="image/x-icon" href="Icon.png" />
  <link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      background: url('Cortadapng.png') no-repeat center center;
      background-size: cover;
      font-family: 'Press Start 2P', cursive;
      overflow: hidden;
      color: #000;
    }

    #desktop {
      position: relative;
      width: 100vw;
      height: 100vh;
    }

    .icon {
      position: absolute;
      top: 40px;
      left: 40px;
      text-align: center;
      width: 64px;
      cursor: pointer;
    }

    .icon img {
      width: 48px;
    }

    .window {
      position: absolute;
      top: 100px;
      left: 100px;
      width: 300px;
      background: #c0c0c0;
      border: 2px solid #000;
      box-shadow: 5px 5px #888;
      display: none;
    }

    .title-bar {
      background: #000080;
      color: #fff;
      padding: 4px;
      cursor: move;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .close-btn {
      background: #ff0000;
      color: #fff;
      padding: 0 8px;
      cursor: pointer;
    }

    .content {
      padding: 20px;
      background: #fff;
    }

   

  </style>
</head>
<body>
  <div id="desktop">
    <div class="icon" ondblclick="openWindow()">
      <img src="https://www.iconarchive.com/download/i103437/treetog/classic-computers/Old-Computer.ico" alt="icono" />
      <div>Mi App</div>
    </div>

    <div class="window" id="myWindow">
      <div class="title-bar" onmousedown="startDrag(event)">
        <span>Ventana Retro</span>
        <div class="close-btn" onclick="closeWindow()">X</div>
      </div>
      <div class="content">
        <p>¡Hola desde los 90s!</p>
      </div>
    </div>
  </div>

  <script>
    const win = document.getElementById("myWindow");
    let offsetX, offsetY, isDragging = false;

    function openWindow() {
      win.style.display = "block";
    }

    function closeWindow() {
      win.style.display = "none";
    }

    function startDrag(e) {
      isDragging = true;
      offsetX = e.clientX - win.offsetLeft;
      offsetY = e.clientY - win.offsetTop;
      document.onmousemove = drag;
      document.onmouseup = stopDrag;
    }

    function drag(e) {
      if (!isDragging) return;
      win.style.left = (e.clientX - offsetX) + "px";
      win.style.top = (e.clientY - offsetY) + "px";
    }

    function stopDrag() {
      isDragging = false;
      document.onmousemove = null;
      document.onmouseup = null;
    }
  </script>
</body>
</html>
