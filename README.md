# Chq & Cash Receiving — Mobile App (PWA)

Ye GitHub Pages par chalne wala chhota "app ka dabba" hai. Andar aapka Google Apps Script web app khulta hai.
Phone par **Install / Add to Home screen** karke ise app ki tarah chala sakte ho.

## 1. Apps Script taiyaar karo
1. Naya **Code.gs** aur **Index.html** paste karke Save karo.
   (Naye Code.gs mein `setXFrameOptionsMode(ALLOWALL)` hai — iske bina app GitHub ke andar nahi khulega.)
2. **Deploy → Manage deployments → Edit (✏️) → Version: New version → Deploy**
3. Settings: *Execute as* = **Me**, *Who has access* = **Anyone**
4. Web app URL copy karo (`.../exec` wala, `/dev` wala nahi).

## 2. GitHub par daalo
1. github.com par naya repository banao, jaise `chq-cash-app` (Public).
2. Is folder ki **saari files** upload karo (folder structure same rakho):
   ```
   index.html
   config.js
   manifest.webmanifest
   sw.js
   icons/icon-192.png
   icons/icon-512.png
   icons/maskable-512.png
   icons/apple-touch-icon.png
   ```
3. **config.js** kholo (GitHub par ✏️ edit) aur apna `/exec` link daalo:
   ```js
   window.APP_URL = 'https://script.google.com/macros/s/AKfycb..../exec';
   ```
4. Repository → **Settings → Pages** → *Source*: **Deploy from a branch**, Branch: **main** / **(root)** → Save.
5. 1-2 minute baad link milega: `https://<aapka-username>.github.io/chq-cash-app/`

## 3. Phone mein install karo
- **Android (Chrome):** link kholo → ⋮ menu → **Install app** / **Add to Home screen**
- **iPhone (Safari):** link kholo → Share ⬆️ → **Add to Home Screen**

## Dhyan rakho
- Google har Apps Script app ke upar ek chhoti patti dikhata hai ("This application was created by a Google Apps Script user"). Ye hataayi nahi ja sakti.
- Login 6 ghante tak yaad rehta hai; uske baad dobara login.
- Code.gs / Index.html badlo to sirf Apps Script mein **New version** deploy karo — GitHub files dobara upload karne ki zaroorat nahi
  (jab tak `/exec` link same hai).
- Excel/PDF download kuch phones par app ke andar se na ho to **Print → Save as PDF** ya **WhatsApp** use karo.
