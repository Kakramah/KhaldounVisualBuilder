# KhaldounVisualBuilder

مشروع دائم لتحويل أي نص إلى **موقع HTML احترافي بهوية خلدون البصرية**، جاهز للنشر على GitHub Pages.

النظام البصري: **Khaldoun cinematic documentary** (وثائقي سينمائي واقعي، عربي RTL، Anti-AI).

> **النطاق:** هذا المشروع يبني HTML/CSS فقط. توليد الصور يتم في جلسة منفصلة (GPT Image 2 عند خلدون)، والصور تُوضع في `output/images/` يدوياً.

---

## كيف تستخدمه

### 1. ضع نصك
افتح [`input.md`](input.md)، امسح القالب القديم، الصق نصك الجديد.

### 2. ضع صورك (إن وُجدت)
ضع `hero.png` + `scene-01.png` + ... في `output/images/` بالأسماء التي ستستخدمها في HTML.

### 3. اطلب البناء
في Claude Code داخل مجلد المشروع، اكتب:
> ابنِ موقعاً من `input.md`

الوكيل سيقرأ `AGENTS.md` ثم `skills/` ثم يختار قالباً مناسباً من `templates/` (أو ينشئ بنية جديدة)، ويولّد `output/index.html` + `output/style.css` + اختياري `output/poster.html`.

### 4. عاين محلياً
افتح `output/index.html` في المتصفح. لا تحتاج server.

### 5. انشر على GitHub Pages
```bash
git add output input.md AGENTS.md README.md skills templates examples
git commit -m "build: <عنوان الموقع>"
git push -u origin main
```
في إعدادات GitHub → Pages → اختر مصدر النشر = مجلد `/output` على فرع `main`.

---

## بنية المشروع

```
KhaldounVisualBuilder/
├── input.md         ← المصدر الوحيد لنص أي مشروع
├── AGENTS.md        ← دستور الوكلاء (اقرأ قبل البناء)
├── README.md        ← هذا الملف
├── skills/          ← قواعد خلدون اللغوية والبصرية (snapshot من Drive)
├── templates/       ← قوالب HTML+CSS+README جاهزة للنسخ
├── examples/        ← أعمال سابقة كاملة كمرجع وإلهام
└── output/          ← البناء الفعلي الحالي (يُنشر)
    └── images/      ← صور المشروع (تأتي يدوياً)
```

---

## القوالب المتاحة

| # | اسم | متى |
|---|-----|-----|
| 01 | **manifesto** | إعلان موقف بضربة افتتاحية + جسم + ضربة نهاية |

> القوالب الأخرى (memorial, archive-entry, document, single-statement, event) تُبنى عند الطلب الفعلي، لا مسبقاً.

## الأمثلة المتاحة

| المثال | النوع |
|--------|------|
| `examples/hareetan/` | منشور أرشيفي إحياء ذكرى — ١٦ أيار ٢٠١٤ |

---

## قواعد ذهبية

- **عربي + RTL** افتراضي (`<html lang="ar" dir="rtl">`).
- **كل** الصور بمسارات نسبية (`images/...`). ممنوع `file:///` أو `/Users/...`.
- **التوقيع** `— Khaldoun A. Akramah` في footer كل صفحة.
- **كل `<img>`** لها `alt` عربي وصفي.
- **Semantic HTML5** (`<main>`, `<article>`, `<section>`, `<figure>`).
- **لا** تنشر تلقائياً — `git push` يبقى يدوياً.

تفاصيل القواعد الكاملة في [`AGENTS.md`](AGENTS.md).

---

## للمساهمين أو الوكلاء الجدد

اقرأ بالترتيب:
1. [`AGENTS.md`](AGENTS.md) — كيف يعمل النظام
2. [`skills/00-index.md`](skills/00-index.md) — خريطة قواعد خلدون
3. [`templates/01-manifesto/README.md`](templates/01-manifesto/README.md) — مثال على بنية قالب
4. [`examples/hareetan/index.html`](examples/hareetan/index.html) — مثال على بناء كامل
