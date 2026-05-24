# KhaldounVisualBuilder

مشروع دائم لتحويل أي نص إلى:
1. موقع عربي RTL متجاوب
2. مفهوم بوستر/غلاف
3. برومبتات صور لـ GPT Image
4. هيكل صور منظَّم
5. مخرج جاهز للنشر على GitHub Pages

النظام البصري: **Khaldoun cinematic documentary**.

---

## كيف تستخدمه

### 1. ضع نصك
افتح [`input.md`](input.md)، امسح المحتوى القديم، والصق نصك الجديد.

### 2. اطلب البناء
في Claude Code داخل مجلد المشروع، اكتب:
> ابنِ المشروع من `input.md`

سيقرأ الوكيل `AGENTS.md` و`skills/` ثم يولّد كل شيء داخل `output/`.

### 3. ولّد الصور
افتح `output/images/image_prompts.md`. كل برومبت موسوم باسم ملف الصورة المتوقع (`hero.png`, `scene-01.png`…). ولّدها في GPT Image واحفظها بنفس الأسماء داخل `output/images/`.

### 4. عاين محلياً
افتح `output/index.html` في المتصفح.

### 5. انشر على GitHub Pages
```bash
# من جذر المشروع
git init
git add output input.md AGENTS.md README.md skills
git commit -m "first build"
git branch -M main
git remote add origin <repo-url>
git push -u origin main
```
ثم في إعدادات GitHub → Pages → اختر مصدر النشر = مجلد `/output` على فرع `main`.

---

## بنية المشروع

```
KhaldounVisualBuilder/
├── input.md          ← المصدر الوحيد لأي نص
├── AGENTS.md         ← قواعد الوكلاء (اقرأ قبل البناء)
├── README.md         ← هذا الملف
├── skills/           ← قواعد خلدون البصرية واللغوية
└── output/           ← المخرج الجاهز للنشر
    └── images/       ← الصور + image_prompts.md (محلي فقط)
```

---

## قواعد ذهبية

- **لا** تضع برومبتات الصور داخل صفحات الموقع.
- **لا** تستخدم مسارات `file:///` أو `/Users/...`.
- **كل** الصور بمسارات نسبية (`images/...`).
- العربي + RTL افتراضي.

تفاصيل القواعد الكاملة في [`AGENTS.md`](AGENTS.md).
