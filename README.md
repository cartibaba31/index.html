<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<title>KCR Sistem</title>

<style>
body {
  margin: 0;
  height: 100vh;
  background: black;
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: monospace;
  color: #00ff88;
}

.kutu {
  background: rgba(0,0,0,0.85);
  padding: 30px;
  border-radius: 15px;
  text-align: center;
  box-shadow: 0 0 25px #00ff88;
  width: 320px;
}

button {
  margin-top: 20px;
  padding: 12px 30px;
  border: none;
  border-radius: 25px;
  cursor: pointer;
  font-size: 16px;
  background: #00ff88;
  color: black;
}

#log {
  margin-top: 15px;
  text-align: left;
  max-height: 180px;
  overflow: hidden;
  font-size: 14px;
}

.titre {
  animation: shake 0.1s infinite;
}

@keyframes shake {
  0% { transform: translate(1px, 1px); }
  50% { transform: translate(-1px, -1px); }
  100% { transform: translate(1px, -1px); }
}
</style>
</head>

<body>

<div class="kutu">
  <h2>KCR KONTROL PANELİ</h2>
  <button onclick="bas()">BAŞLAT</button>
  <div id="log"></div>
</div>

<script>
let adim = 0;

const mesajlar = [
  ">> Sistem başlatılıyor...",
  ">> Kullanıcı tespit edildi",
  ">> Adı: Cartios",
  ">> Grup: KCR",
  ">> Yetkiler kontrol ediliyor...",
  ">> Erişim KCR grubuna ait ✔",
  ">> İşlem başarıyla tamamlandı 😎",
  ">> Hoş geldin Cartios | KCR 🔥"
];

function bas() {
  document.body.classList.add("titre");
  const log = document.getElementById("log");

  log.innerHTML = ""; // tekrar basınca sıfırlansın
  adim = 0;

  const interval = setInterval(() => {
    log.innerHTML += mesajlar[adim] + "<br>";
    adim++;

    if (adim === mesajlar.length) {
      clearInterval(interval);
      document.body.classList.remove("titre");
    }
  }, 650);
}
</script>

</body>
</html>
