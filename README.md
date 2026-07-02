# ego-yazilim67
"Ego Yazılım - Profesyonel video kurgu, tasarım ve sosyal medya destek hizmetleri merkezi."
[index (4).html](https://github.com/user-attachments/files/29611500/index.4.html)
<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ego Yazılım | Satış Paneli</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        body { background-color: #030710; color: white; font-family: 'Segoe UI', sans-serif; display: flex; justify-content: center; align-items: center; min-height: 100vh; margin: 0; padding: 10px; }
        .main-card { background: rgba(26, 26, 26, 0.95); padding: 20px; border-radius: 20px; width: 100%; max-width: 400px; border: 1px solid #ff2a6d; box-shadow: 0 10px 30px rgba(0,0,0,0.8); box-sizing: border-box; }
        h2 { color: #ff2a6d; font-size: 1rem; margin: 15px 0 10px; border-left: 3px solid #ff2a6d; padding-left: 10px; }
        .row { display: flex; align-items: center; justify-content: space-between; margin-bottom: 8px; padding: 8px; background: rgba(255, 255, 255, 0.03); border-radius: 8px; font-size: 0.9rem; }
        button { background: #ff2a6d; border: none; padding: 6px 12px; color: white; border-radius: 5px; cursor: pointer; font-weight: bold; flex-shrink: 0; }
        #sepet-listesi { margin: 15px 0; padding: 10px; background: #000; border-radius: 10px; border: 1px solid #333; }
        .toplam-box { font-size: 1.1rem; font-weight: bold; text-align: right; color: #00ff9d; margin-top: 10px; }
        .siparis-btn { width: 100%; padding: 12px; background: linear-gradient(to right, #ff2a6d, #9b51e0); border: none; color: white; font-weight: bold; border-radius: 10px; cursor: pointer; margin-top: 10px; }
        .sosyal-btn { display: flex; align-items: center; justify-content: center; gap: 10px; width: 100%; padding: 8px; margin: 5px 0; border-radius: 10px; color: white; font-weight: bold; text-decoration: none; background: #222; }
        .credits { text-align: center; font-size: 0.7rem; color: #777; margin-top: 20px; border-top: 1px solid #333; padding-top: 10px; line-height: 1.4; }
    </style>
</head>
<body>

<div class="main-card">
    <h2>Dijital Hizmetler</h2>
    <div class="row"><span>Video Edit (150 TL)</span><button onclick="sepetEkle('Video Edit', 150)">Ekle</button></div>
    <div class="row"><span>Logo Tasarım (200 TL)</span><button onclick="sepetEkle('Logo Tasarım', 200)">Ekle</button></div>

    <h2>🎁 Destek (Bahşiş)</h2>
    <div class="row"><span>Küçük Destek (20 TL)</span><button onclick="sepetEkle('Bahşiş', 20)">Ekle</button></div>

    <h2>🛒 Sepetiniz</h2>
    <div id="sepet-listesi">
        <ul id="urunler-listesi" style="padding-left: 20px; font-size: 0.85rem; margin: 5px 0;"><li>Sepetiniz boş.</li></ul>
        <div class="toplam-box">Toplam: <span id="toplam-fiyat">0</span> TL</div>
    </div>

    <button class="siparis-btn" onclick="siparisTamamla()">KREDİ KARTI İLE ÖDE (Shopier)</button>

    <h2>İletişim</h2>
    <a href="https://www.tiktok.com/@egemen45_43" class="sosyal-btn"><i class="fab fa-tiktok"></i> TİKTOK</a>
    <a href="https://wa.me/905376972838" class="sosyal-btn" style="background:#25d366;"><i class="fab fa-whatsapp"></i> WHATSAPP</a>

    <div class="credits">
        Ego Yazılım &copy; 2026 | Kurucu: Egemen Özel <br>
        Destekçiler: İbo, Ahmet | Geliştirme: Egemen Özel
    </div>
</div>

<script>
    let sepet = [];
    let toplam = 0;
    const magazaLinkim = "https://www.shopier.com/MAGAZA_ADIN"; // Burayı Shopier linkinle değiştir

    function sepetEkle(urun, fiyat) {
        sepet.push({isim: urun, fiyat: fiyat});
        toplam += fiyat;
        guncelle();
    }

    function guncelle() {
        let liste = document.getElementById('urunler-listesi');
        if(sepet.length === 0) {
            liste.innerHTML = "<li>Sepetiniz boş.</li>";
        } else {
            liste.innerHTML = "";
            sepet.forEach(item => {
                liste.innerHTML += `<li>${item.isim} - ${item.fiyat} TL</li>`;
            });
        }
        document.getElementById('toplam-fiyat').innerText = toplam;
    }

    function siparisTamamla() {
        if(sepet.length === 0) { alert('Sepet boş, ürün ekleyin!'); return; }
        window.open(magazaLinkim, '_blank');
    }
</script>
</body>
</html>
