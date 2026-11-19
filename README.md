# Hacı Axundzadə — Portfolio

Data Scientist portfoliom: AZ / EN / RU dillərində, tünd və açıq temalı, asılılıqsız statik sayt (GitHub Pages).
Canlı: **https://hajye.github.io/** · Canlı demo: **https://hajye.github.io/demo/menu/**

## Quruluş

```
index.html                 ← bütün sayt (HTML + CSS + JS bir faylda)
demo/menu/index.html       ← brauzerdə işləyən McDonald's menyu generatoru (server/Gradio lazım deyil)
demo/menu/img/             ← məhsul şəkilləri (webp)
assets/                    ← layihə kartı şəkilləri
certificates/              ← sertifikat şəkilləri və PDF-ləri
Haci_Axundzade_CV-1.pdf    ← CV (AZ)
Haji_Akhundzada_CV_EN-1.pdf← CV (EN / RU)
og-image.png               ← sosial şəbəkədə link önizləməsi (1200×630)
robots.txt, sitemap.xml    ← axtarış sistemləri üçün
```

## Bölmələr

Profile · Toolkit (ikonlu bacarıqlar) · Languages · Experience · Education · Projects · Certificates · Contact.
HA dairəsi interaktivdir (hover/klik), layihələr kateqoriyaya görə filtrlənir, hər layihənin **Case study** pəncərəsi var.

## Layihələr

| # | Layihə | Demo / kod |
|---|--------|-----------|
| 01 | AI-Based Menu Recommendation (McDonald's) | Canlı demo, Colab |
| 02 | Solar System (Image Synthesis) | GitHub, video |
| 03 | MovieLens Recommender | Colab |
| 04 | Fastener Defect Classification (M1 DSAI / DL) | GitHub, izahat PDF, kod |

## Yeni layihə əlavə etmək

1. **Kart.** `index.html`-də `#projects` bölməsindəki bir `<article class="panel project" data-category="data|simulation">` blokunu kopyalayın. Şəkli `assets/` qovluğuna qoyun (`.webp` tövsiyə olunur). Sayğacı (`0X PROJECTS`) və `0X / 0X` nömrələrini yeniləyin.
2. **Tərcümə.** Kartdakı mətn üçün `translations` obyektinə yeni açar əlavə edin (məs. `"proj.p5": {az:"…", en:"…", ru:"…"}`) və elementə `data-i18n="proj.p5"` yazın.
3. **Case study.** `CS` obyektinə yeni açar əlavə edin (məs. `p5`). Hər açarda `img`, `stack`, `links` (ümumi) və `az` / `en` / `ru` bloku var; hər dil blokunda `title`, `sub`, `metrics`, `sections` olur. Şəkil ağ fonda tam görünməlidirsə (qrafik), `fit` əlavə edin. Kartdakı düymədə `data-project="p5"` olsun.
4. Brauzerdə yoxlayın: 3 dil, 2 tema, 390 px mobil görünüş.

## Analitika (könüllü, cookie-siz)

[GoatCounter](https://www.goatcounter.com) istifadə olunur. Hazırda **söndürülüb**.

1. goatcounter.com-da pulsuz hesab açın (məs. `hajye` → `hajye.goatcounter.com`).
2. İki faylda `GOATCOUNTER_CODE=""` sətrinə kodu yazın: `index.html` və `demo/menu/index.html`.
3. "Do Not Track" aktiv olan və localhost-dan gələn ziyarətlər sayılmır.

## SEO və link önizləməsi

`<head>`-də description, canonical, Open Graph / Twitter kartları və JSON-LD (`Person`) var. Önizləmə şəkli `og-image.png`-dir. Yeni domen istifadə etsəniz `canonical`, `og:url`, `sitemap.xml` və `robots.txt` daxilindəki `hajye.github.io` ünvanlarını dəyişin.
Önizləməni yoxlamaq üçün: LinkedIn Post Inspector və ya opengraph.xyz.

## CV faylları

CV düyməsi seçilmiş dilə uyğun faylı yükləyir (`cvFiles` dəyişəni, `index.html`). Faylın adını dəyişsəniz, həmin dəyişəni və `#cvLink` ünvanını da yeniləyin.

## Lokal işə salma

```bash
git clone https://github.com/haJye/haJye.github.io.git
cd haJye.github.io
python3 -m http.server 8000   # sonra http://localhost:8000
```

`index.html`-i birbaşa açmaq da işləyir, amma demo və şəkillər üçün lokal server daha etibarlıdır.

## Deployment (GitHub Pages)

Repo → **Settings → Pages** → Source: `Deploy from a branch` → `main` / `(root)`. Bir neçə dəqiqəyə sayt canlı olur.

## Əlaqə

GitHub: [@haJye](https://github.com/haJye)

© 2026 Hacı Axundzadə
