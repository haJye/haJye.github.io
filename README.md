# Hacı Axundzadə — Portfolio
 
Data Scientist portfoliom — statik, tək fayllı HTML sayt. [Canlı demoya bax →](https://hajye.github.io/) <!-- GitHub Pages linkini burda yeniləyin -->
 
![preview](https://raw.githubusercontent.com/haJye/DSAI/main/M2DSAI/Dissertation/Peek%202026-07-21%2023-05.gif)
 
## Haqqında
 
Bu repo mənim şəxsi portfolio saytımın mənbə kodunu saxlayır. Sayt tərminal-temalı, "Jupyter notebook" estetikası ilə hazırlanıb (`In [ ]:` / `Out [ ]:` bölmələri) və aşağıdakı hissələrdən ibarətdir:
 
- **Haqqımda** — qısa təqdimat
- **Bacarıqlar** — Data & ML, Backend, Frontend, Alətlər, Dillər
- **Təcrübə & Təhsil** — iş tarixçəsi və UFAZ / ADNSU təhsili
- **Layihələr** — GIF/video demolarla birlikdə seçilmiş layihələr
- **Currently Learning** — texnologiya istiqamətləri, kurslar və şəxsi eksperimentlər
- **GitHub Live Activity** — seçilmiş repoların ulduz, fork, əsas dillər və son yenilənmə məlumatları (GitHub API ilə)
- **Əlaqə** — e-poçt və sosial linklər
## Texnologiyalar
 
Sadə, asılılıqsız (dependency-free) tək HTML fayl:
 
- Vanilla HTML5 / CSS3 (custom properties, grid, flexbox)
- Google Fonts: Space Grotesk, Inter, JetBrains Mono
- Heç bir build addımı, framework və ya paket meneceri tələb olunmur
## Lokal işə salma
 
Faylı brauzerdə açmaq kifayətdir:
 
```bash
git clone https://github.com/haJye/haJye.github.io.git
cd haJye.github.io
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
 
Yeni layihə əlavə etmək üçün `index.html` faylında `#projects` bölməsindəki `.project` blokunu kopyalayıb məzmunu dəyişdirmək kifayətdir:
 
```html
<article class="panel project" data-category="data">
  <div class="project-media">
    <img src="GIF_VƏ_YA_ŞƏKİL_LİNKİ" alt="Layihə adı demo" loading="lazy">
  </div>
  <div class="project-meta"><span>Kateqoriya</span><span>Out [5.x]</span></div>
  <div class="project-body">
    <h3>Layihə adı</h3>
    <div class="stack"><span>Texnologiya 1</span><span>Texnologiya 2</span></div>
    <p>Qısa təsvir.</p>
    <div class="project-links">
      <a href="LİNK" target="_blank">GitHub →</a>
    </div>
  </div>
</article>
```
 
## Əlaqə
 
- GitHub: [@haJye](https://github.com/haJye)
- Sayt üzərindən e-poçt və sosial şəbəkələr
---
 
© 2026 Hacı Axundzadə. Bütün hüquqlar qorunur.
 
