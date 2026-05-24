# 05 — ترجمة النظام إلى ويب (HTML / CSS)

> كيف يصبح "Cinematic Documentary" موقعاً فعلياً داخل `output/`.
>
> **تنبيهات سريعة:**
> - التوقيع داخل **الصور** = `@𝓚𝓱𝓪𝓵𝓭𝓸𝓾𝓷𝓐𝓪𝓀𝓻𝓪𝓶𝓪𝓱` bottom-right (راجع `01` و `04`).
> - التوقيع داخل **الموقع** = نص footer `— Khaldoun A. Akramah`.
> - الأداة المولّدة للصور = **GPT Image 2** (راجع `04-image-prompts.md`).

## بنية `output/` المتوقعة

```
output/
├── index.html
├── style.css
└── images/
    ├── hero.png
    ├── scene-01.png
    ├── ...
    └── image_prompts.md   ← محلي فقط
```

> ملف واحد `index.html` كافٍ للأغلب. لا تنشئ Multi-page إلا إذا النص يستدعي ذلك.

## الـHTML الأساسي

```html
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title><!-- عنوان قصير ضربة --></title>
  <meta name="description" content="<!-- جملة واحدة تحت 160 حرف -->" />
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <main>
    <section class="hero">
      <img src="images/hero.png" alt="<!-- وصف عربي قصير، ليس البرومبت -->" />
      <h1><!-- عنوان ضربة --></h1>
      <p class="caption"><!-- caption_energy --></p>
    </section>

    <article>
      <!-- نص input.md مُحوَّلاً إلى فقرات + صور داخلية -->
    </article>

    <footer>
      <p>— Khaldoun A. Akramah</p>
    </footer>
  </main>
</body>
</html>
```

## قواعد إلزامية للـHTML

- `<html lang="ar" dir="rtl">` دائماً.
- كل `<img>` بمسار نسبي: `images/...` — **ممنوع** `file:///` أو `/Users/...`.
- كل `<img>` يحوي `alt` عربياً وصفياً (للوصولية)، **ليس** البرومبت.
- **لا** تضع البرومبتات في تعليقات HTML. هي في `image_prompts.md` فقط.
- التذييل يحوي التوقيع `— Khaldoun A. Akramah` نصياً.
- Semantic HTML: `<main>`, `<article>`, `<section>`, `<figure>`, `<figcaption>`.

## الـCSS — الأساس

```css
:root {
  --syria-green-deep: #114845;
  --syria-green-soft: #A1B8A6;
  --ink: #1a1a1a;
  --paper: #f5f1ea;        /* أساس ترابي دافئ */
  --paper-dim: #ebe5d9;
  --muted: #6b6b6b;
  --rule: rgba(17, 72, 69, 0.18);

  --font-display: "Tajawal", "IBM Plex Sans Arabic", "Cairo", system-ui, sans-serif;
  --font-body:    "IBM Plex Sans Arabic", "Tajawal", "Cairo", system-ui, sans-serif;

  --max-w: 720px;
  --gutter: clamp(1rem, 4vw, 2rem);
}

* { box-sizing: border-box; }

html, body {
  margin: 0;
  padding: 0;
  background: var(--paper);
  color: var(--ink);
  font-family: var(--font-body);
  font-size: clamp(1rem, 1rem + 0.2vw, 1.125rem);
  line-height: 1.85;
  text-rendering: optimizeLegibility;
}

main {
  max-width: var(--max-w);
  margin: 0 auto;
  padding: var(--gutter);
}

h1, h2, h3 {
  font-family: var(--font-display);
  font-weight: 800;
  line-height: 1.25;
  color: var(--syria-green-deep);
}

h1 { font-size: clamp(1.8rem, 1.4rem + 2vw, 2.8rem); margin: 0 0 0.5em; }
h2 { font-size: clamp(1.4rem, 1.2rem + 1vw, 1.9rem); margin: 2.2em 0 0.4em; }
h3 { font-size: 1.15rem; margin: 1.6em 0 0.3em; color: var(--ink); }

p { margin: 0 0 1.2em; }

a {
  color: var(--syria-green-deep);
  text-decoration: underline;
  text-decoration-thickness: 1px;
  text-underline-offset: 3px;
}

img {
  max-width: 100%;
  height: auto;
  display: block;
}

.hero {
  margin: 0 0 3rem;
}
.hero img {
  width: 100%;
  border-radius: 2px;
  filter: contrast(1.02) saturate(0.95);  /* خفض لمعان AI */
}
.hero .caption {
  font-family: var(--font-display);
  font-size: 1.05rem;
  color: var(--muted);
  margin-top: 0.8em;
  border-inline-start: 3px solid var(--syria-green-soft);
  padding-inline-start: 0.9em;
}

article figure {
  margin: 2.2em 0;
}
article figure img {
  border-radius: 2px;
}
article figcaption {
  font-size: 0.92rem;
  color: var(--muted);
  margin-top: 0.5em;
  text-align: start;
}

hr {
  border: 0;
  border-top: 1px solid var(--rule);
  margin: 2.5em 0;
}

footer {
  margin-top: 4rem;
  padding-top: 1.5rem;
  border-top: 1px solid var(--rule);
  color: var(--muted);
  font-family: var(--font-display);
  font-size: 0.95rem;
  text-align: start;
}

/* تحسين عرض العربي على الموبايل */
@media (max-width: 480px) {
  html, body { font-size: 1rem; }
  main { padding: 1.1rem; }
}
```

## التيبوغرافيا

- **الخط الافتراضي:** Tajawal أو IBM Plex Sans Arabic أو Cairo (بهذا الترتيب).
- لا تستخدم خطوط رفيعة (`font-weight: 300`) للعناوين — العربي يضيع.
- العناوين بـ `700`–`800`.
- النص بـ `400`–`500`.
- `line-height: 1.85` للعربي (لا تقل عن 1.7).
- محاذاة النص: `text-align: start` (ليس `right`) — تحترم الـ RTL تلقائياً.

## ربط الخطوط (إن أردت Google Fonts)

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;800&display=swap" rel="stylesheet">
```
> اختياري. إذا أردت موقعاً مستقلاً تماماً، حمّل الخط محلياً في `output/fonts/`.

## البوستر — متى يكون صفحة منفصلة

- إذا النص قصير (منشور واحد) → ادمج البوستر كقسم Hero.
- إذا النص طويل (مقال متعدد الأقسام) → أنشئ `output/poster.html` مستقلاً بنسبة 2:3 صورة كاملة + caption.

## GitHub Pages — جاهزية

- كل المسارات نسبية → يعمل من أي subpath (`username.github.io/repo/output/`).
- لا اعتماد على build step. HTML خام + CSS + صور.
- لا JavaScript إلا عند الحاجة الحقيقية (لا analytics افتراضياً).

## فحوصات قبل التسليم

- [ ] `<html lang="ar" dir="rtl">` موجود؟
- [ ] لا مسارات مطلقة في أي مكان؟
- [ ] كل `<img>` لها `alt` عربي؟
- [ ] لا برومبت تسرَّب في HTML؟
- [ ] التوقيع `— Khaldoun A. Akramah` في footer؟
- [ ] التذييل عربي والتاريخ (إن وُجد) عربي؟
- [ ] الموقع يبدو سليماً على شاشة 360px؟
