# Freeze Command Skript ❄️ / Dondur Komutu ⛔

This Skript allows server admins to **freeze and unfreeze all players** on the server. It includes visual and sound effects to notify players when they are frozen.  

Bu Skript, sunucu yöneticilerinin **tüm oyuncuları dondurup serbest bırakmasına** izin verir. Oyunculara dondurulduklarında bildirim vermek için görsel ve ses efektleri içerir.

---

## Features / Özellikler

- **Toggle freeze / Dondurmayı aç/kapat**  
  Command: `/dondur`  
  Permission: `dondur.admin`  
  - If active, all non-OP players are frozen.  
  - Aktifse, OP olmayan tüm oyuncular dondurulur.
  - Broadcast message with ✅  
  - Yayınlanan mesajlarda ✅

- **Sound alerts / Sesli bildirimler**  
  - When frozen: plays `entity.tnt.primed` sound to all players.  
  - Dondurulduğunda: tüm oyunculara `entity.tnt.primed` sesi çalar.
  - When movement blocked: `entity.villager.no` sound is played.  
  - Hareket engellendiğinde: `entity.villager.no` sesi çalar.

- **Movement restriction / Hareket kısıtlaması**  
  - While `{dondur::active}` is true, all non-OP players cannot move.  
  - `{dondur::active}` true olduğu sürece OP olmayan oyuncular hareket edemez.  
  - Players see a title message:  
    `"&4⛔&7(Hareket edemezsin)&4⛔"`  
  - Oyunculara başlık mesajı gösterilir:  
    `"&4⛔&7(Hareket edemezsin)&4⛔"`

---

## How it works / Nasıl çalışır

1. **Command trigger / Komut tetikleme**  
   - `/dondur` typed by admin  
   - Eğer `{dondur::active}` true → set false (unfreeze)  
   - Eğer `{dondur::active}` false → set true (freeze)

2. **Loop all players / Tüm oyunculara döngü**  
   - When freezing: play TNT sound for each player.  
   - Dondururken: her oyuncuya TNT sesi çalınır.

3. **Player move event / Oyuncu hareketi**  
   - If frozen and not OP → cancel move, show title & play sound.  
   - Eğer dondurulmuş ve OP değilse → hareket iptal, başlık ve ses çalınır.

---

### Variables / Değişkenler

- `{dondur::active}` → true / false  
  - True = players are frozen / oyuncular dondurulmuş  
  - False = players are free / oyuncular serbest
