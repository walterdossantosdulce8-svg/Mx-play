<!DOCTYPE html>
<html lang="pt">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MX Play</title>
<style>
*{box-sizing:border-box}
body{margin:0;background:#101018;color:white;font-family:Arial,sans-serif}
header{padding:22px;background:#191925;display:flex;align-items:center;gap:12px}
.logo{background:#7657ff;padding:10px;border-radius:12px;font-weight:bold}
h1{font-size:24px;margin:0}
main{padding:20px}
h2{font-size:20px}
.player{width:100%;background:#000;border-radius:14px;overflow:hidden}
video{width:100%;display:block;max-height:60vh}
.note{color:#bbb;font-size:14px;line-height:1.5}
input{width:100%;padding:13px;border-radius:9px;border:1px solid #444;background:#20202d;color:white;margin:8px 0}
button{padding:12px 16px;border:0;border-radius:9px;background:#7657ff;color:white;font-weight:bold}
</style>
</head>
<body>
<header><div class="logo">▶ MX</div><h1>MX Play</h1></header>
<main>
<h2>O teu espaço de vídeos</h2>
<div class="player"><video id="video" controls playsinline></video></div>
<p class="note">Escolhe um vídeo do teu telemóvel para o reproduzir aqui. O vídeo fica no teu dispositivo.</p>
<input id="file" type="file" accept="video/*">
<p class="note">Também podes abrir um vídeo através de uma ligação direta:</p>
<input id="url" type="url" placeholder="Cola aqui o endereço do vídeo">
<button onclick="playUrl()">Reproduzir ligação</button>
</main>
<script>
const video=document.getElementById('video');
document.getElementById('file').addEventListener('change',function(){if(this.files[0]){video.src=URL.createObjectURL(this.files[0]);video.play().catch(()=>{});}});
function playUrl(){const u=document.getElementById('url').value.trim();if(u){video.src=u;video.play().catch(()=>{});}}
</script>
</body>
</html>
