# Hacı Axundzadə — Portfolio
 
Data Scientist portfoliom — statik, tək fayllı HTML sayt. [Canlı demoya bax →](https://hajye.github.io/) <!-- GitHub Pages linkini burda yeniləyin -->
 
![preview](https://raw.githubusercontent.com/haJye/DSAI/main/M2DSAI/Dissertation/Peek%202026-07-21%2023-05.gif)
 
## Haqqında
 
Bu repo mənim şəxsi portfolio saytımın mənbə kodunu saxlayır. Sayt tərminal-temalı, "Jupyter notebook" estetikası ilə hazırlanıb (`In [ ]:` / `Out [ ]:` bölmələri) və aşağıdakı hissələrdən ibarətdir:
 
- **Haqqımda** — qısa təqdimat
- **Bacarıqlar** — Data & ML, Backend, Frontend, Alətlər, Dillər
- **Təcrübə & Təhsil** — iş tarixçəsi və UFAZ / ADNSU təhsili
- **Layihələr** — GIF/video demolarla birlikdə seçilmiş layihələr
- **Əlaqə** — birbaşa əlaqə formu və sosial linklər
## Texnologiyalar
 
Sadə, asılılıqsız (dependency-free) tək HTML fayl:
 
- Vanilla HTML5 / CSS3 (custom properties, grid, flexbox)
- Google Fonts: Space Grotesk, Inter, JetBrains Mono
- Heç bir build addımı, framework və ya paket meneceri tələb olunmur
## Lokal işə salma
 
Faylı brauzerdə açmaq kifayətdir:
 
```bash
git clone https://github.com/haJye/portfolio.git
cd portfolio
open index.html   # macOS
# və ya
xdg-open index.html   # Linux
# və ya sadəcə index.html üzərinə iki dəfə klikləyin (Windows)
```
 
## Deployment (GitHub Pages)
 
1. Repo → **Settings** → **Pages**
2. **Source**: `Deploy from a branch`
3. **Branch**: `main`, qovluq: `/ (root)`
4. Saxlayın — bir neçə dəqiqəyə sayt `https://hajye.github.io/` ünvanında canlı olacaq
## Layihələri yeniləmək
 
Yeni layihə əlavə etmək üçün `index.html` faylında `#projects` bölməsindəki `proj-card` blokunu kopyalayıb məzmunu dəyişdirmək kifayətdir:
 
```html
<div class="proj-card">
  <div class="proj-media">
    <img src="GIF_VƏ_YA_ŞƏKİL_LİNKİ" alt="Layihə adı demo" loading="lazy">
  </div>
  <div class="proj-top"><span>Out [5.x]</span><span>Kateqoriya</span></div>
  <div class="proj-body">
    <h3>Layihə adı</h3>
    <div class="stack-row"><span>Texnologiya 1</span><span>Texnologiya 2</span></div>
    <p>Qısa təsvir.</p>
    <div class="proj-links">
      <a href="LİNK" target="_blank">GitHub →</a>
    </div>
  </div>
</div>
```
 
## Əlaqə
 
- GitHub: [@haJye](https://github.com/haJye)
- Sayt üzərindən əlaqə formu
---
 
© 2026 Hacı Axundzadə. Bütün hüquqlar qorunur.
 
