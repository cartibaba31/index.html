<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<title>KILLER TERMINAL</title>

<style>
body{
  margin:0;
  background:black;
  font-family: monospace;
  height:100vh;
  overflow:hidden;
}

#terminal{
  padding:20px;
  white-space: pre-line;
  font-size:15px;
  color:#00ff66;
  text-shadow: 0 0 8px #00ff66;
}

.cursor{
  display:inline-block;
  width:10px;
  height:18px;
  background:#00ff66;
  animation:blink 1s infinite;
}

@keyframes blink{
  0%,50%{opacity:1}
  51%,100%{opacity:0}
}
</style>
</head>

<body>

<div id="terminal"></div>

<script>
const terminal = document.getElementById("terminal");

const satirlar = [
  "KILLER CORE v7.0",
  "--------------------------------",
  "Bağlantı kuruluyor...",
  "Gizli protokol aktif ✔",
  "",
  "KILLERIM SAYFASINA HOŞ GELDİN",
  "",
  "Kod kralı burada yazıyor.",
  "Sessiz. Hızlı. Görünmez.",
  "",
  "KILLER bir isim değildir.",
  "KILLER karanlıkta bırakılan izdir.",
  "KILLER sistemlerin korkusudur.",
  "",
  "Loglar silindi.",
  "İz bırakılmadı.",
  "Takip: KAPALI",
  "",
  "Erişim seviyesi: MAKSİMUM",
  "Yetki: SINIRSIZ",
  "",
  "Unutma:",
  "Kod konuşur.",
  "Diğerleri sadece izler.",
  "",
  ">> KILLER BEKLİYOR _"
];

let i = 0;

function yaz(){
  if(i < satirlar.length){
    terminal.innerHTML += satirlar[i] + "\n";
    i++;
    setTimeout(yaz, 450);
  } else {
    terminal.innerHTML += "<span class='cursor'></span>";
  }
}

yaz();
</script>

</body>
</html>
