# 04 — برومبتات الصور (GPT Image 2)

> **الأداة الحالية: GPT Image 2** (ليس Midjourney، ليس Nano Banana).
> صيغة البرومبت: **نثر وصفي مباشر بالإنجليزية فقط**.
> مصادر: `ABOUT_ME/about-me.md` (صيغة GPT Image 2) + `Visual_System/prompt-library.md` (نظام DNA) + `References/what-fails.md` (ما يفشل).

---

## ⚠️ ثلاث قواعد لا تُكسر

1. **البرومبت بالإنجليزية حصراً.** البرومبت العربي في GPT Image 2 يفشل أو ينتج صوراً عامة.
2. **لا معاملات Midjourney** (`--v 8`, `--style raw`, `--stylize`, `--ar`). GPT Image 2 يتجاهلها أو يُنتج خطأ.
3. **التوقيع `@𝓚𝓱𝓪𝓵𝓭𝓸𝓾𝓷𝓐𝓪𝓀𝓻𝓪𝓶𝓪𝓱` bottom-right** (ليس left).

---

## الصيغة المعيارية (نثر وصفي، لا أقواس)

ابنِ البرومبت كأنك تصف المشهد لمصوّر يقف أمامك. بهذا الترتيب:

```
[Documentary photograph / Fine art print / Photojournalism still — اختر نوعاً واحداً]

[Subject: human first — face, hands, body, expression, exact moment]

[Setting + Cultural lock — Syrian context details]

[Camera body + lens mm + film stock — named]

[Light: direction + Kelvin + shadow map + falloff]

[Layer 4 for every human surface visible: texture + sheen + tone_map + named substance]

[Negative space as compositional element — what's NOT in frame]

[Color palette with HEX if Syrian — #114845, #A1B8A6, etc.]

[Mood word — one or two words only]

[Anti-AI modifiers: film grain, no plastic skin, no perfect symmetry, no oversaturation, realistic imperfection]

[Signature line — copy-pasted verbatim from below]
```

لا أقواس في البرومبت النهائي. لا ترقيم. نص متدفّق طبيعي.

---

## سطر التوقيع (انسخه حرفياً)

اختر **واحداً** حسب نوع المشهد:

| النوع | الصيغة |
|------|--------|
| **الافتراضي** | `subtle artist signature "@𝓚𝓱𝓪𝓵𝓭𝓸𝓾𝓷𝓐𝓪𝓀𝓻𝓪𝓶𝓪𝓱" embedded bottom-right, very small, adaptive color, 25–35% opacity, realistically integrated into the scene texture, not a separate overlay` |
| **واقعي** | `subtle artist signature "@𝓚𝓱𝓪𝓵𝓭𝓸𝓾𝓷𝓐𝓪𝓀𝓻𝓪𝓶𝓪𝓱" naturally embedded into surface details (wall, dust, fabric), bottom-right, 25–35% opacity, physically integrated` |
| **سينمائي** | `faint signature "@𝓚𝓱𝓪𝓵𝓭𝓸𝓾𝓷𝓐𝓪𝓀𝓻𝓪𝓶𝓪𝓱" revealed through light falloff or grain, bottom-right, almost imperceptible, blended with shadows` |
| **تصميم نظيف** | `minimal micro-signature "@𝓚𝓱𝓪𝓵𝓭𝓸𝓾𝓷𝓐𝓪𝓀𝓻𝓪𝓶𝓪𝓱" bottom-right, aligned to grid, ultra small, low opacity 25–35%` |
| **Grunge/ملف** | `distressed signature "@𝓚𝓱𝓪𝓵𝓭𝓸𝓾𝓷𝓐𝓪𝓀𝓻𝓪𝓶𝓪𝓱" stamped bottom-right, partially worn, blended with texture noise` |

---

## بنية ملف `output/images/image_prompts.md`

```markdown
# Image Prompts — <اسم المشروع>

> **التصنيف البصري:** [1 ثقيل / 2 رسمي / 3 خفيف / 4 شاعري] — <الاسم>
> **اللوحة اللونية:** <وصف + HEX>
> **عدد الصور:** <N>
> **DNA الهدف:** <TYPE>-<SUBJECT>-<EMOTION>-<LIGHT>-<TEXTURE>-<REALISM>-<FRAME>-<MOTION>-<SYMBOL>-<AESTHETIC>

---

## hero.png

**الموقع في الموقع:** قسم Hero في `index.html`
**نسبة العرض المقترحة:** 2:3 (بوستر) أو 16:9 (ويب)
**Caption_energy (يظهر في الموقع):**
> <جملة عربية أدبية واحدة>

**Prompt (GPT Image 2 — English prose):**
```
<البرومبت كاملاً بالإنجليزية، نثر متدفّق، بدون معاملات>
```

---

## scene-01.png
...
```

---

## ترميز DNA (لتتبّع التوازن عبر مشاريع متعددة)

اختياري لكل برومبت، إجباري لو ولّدت ≥ 5 صور:

```
[TYPE]-[SUBJECT]-[EMOTION]-[LIGHT]-[T]-[R]-[FRAME]-[MOTION]-[S]-[A]
```

| الحقل | القيم |
|------|-------|
| **TYPE** | DOC / PJ / FA / CIN |
| **SUBJECT** | HUM / OBJ / ENV / SYM |
| **EMOTION** | STR / GRF / HOP / RES / ISO / TEN |
| **LIGHT** | CHR / HRD / DIF / LOW / RIM / FOG |
| **TEXTURE** | T1 / T2 / T3 |
| **REALISM** | R1 / R2 / R3 |
| **FRAME** | ISO / MAC / MED / WID / LAY / AER |
| **MOTION** | STL / ACT / IMP |
| **SYMBOL** | S0 / S1 / S2 / S3 |
| **AESTHETIC** | A1 / A2 / A3 (لا يُحفَظ تحت A2) |

**Target DNA الافتراضي:** `DOC-ENV-STR-DIF-T3-R3-WID-ACT-S3-A3`

**قواعد التوازن عبر المجموعة:**
- HUM ≤ 60% من المجموع
- S3 يظهر كل 5 صور على الأقل
- CHR + HRD ≤ 60% (الباقي DIF/FOG/RIM)
- 3 صور متتالية بنفس TYPE+SUBJECT+FRAME → الرابعة تكسر واحدة منها

---

## Layer 4 — لكل سطح بشري ظاهر

كل وجه أو يد أو ذراع في الصورة يحتاج 4 طبقات:
1. **texture** — مسامات، شعيرات، تجاعيد
2. **sheen** — لمعان طبيعي على جسر الأنف، الجبين
3. **tone_map** — انتقالات لونية (دفء/برودة) عبر السطح
4. **named substance** — غبار، عرق، تربة، رماد، حبر

مثال:
```
skin: visible pores, micro-hair on cheekbones, oil-sheen on nose bridge,
warm undertone fading to cool on temples, fine dust particles caught in eyebrow hair
```

---

## كاميرات وعدسات وأفلام (مرجع سريع)

للتفاصيل الكاملة: `Visual_System/CAMERA.md` في Drive (40KB). إليك نواة عملية:

| المشهد | الجسم | العدسة | الفيلم |
|--------|------|--------|--------|
| وثائقي وجوه | Arri Alexa Mini | 35mm Zeiss Master Prime | Kodak Vision3 500T |
| photojournalism حدث | Leica M11 | 50mm Summilux | Kodak Tri-X 400 |
| Fine Art ساكن | Hasselblad 907X | 80mm XCD | Portra 400 |
| Cinematic ليلي | Sony Venice | 65mm Cooke S7/i | Vision3 250D pushed |
| Macro forensic | Phase One IQ4 | 120mm Schneider Macro | Provia 100F |

**اكتبها مُسمَّاة دائماً:** "shot on Arri Alexa Mini, 35mm Zeiss Master Prime, Kodak Vision3 500T emulation".

---

## ملاحظات GPT Image 2 الخاصة

- **النص العربي داخل الصورة:** `Arabic text reads: "<النص>" in a heavy serif Arabic typeface, integrated naturally into the scene`
- **نسبة العرض:** اطلبها وصفياً: `tall vertical 2:3 frame` أو `wide cinematic 16:9 frame`
- **الرفض الناعم:** لو رفض المشهد، أعد الصياغة بنبرة وثائقية بدلاً من درامية.

---

## محظورات البرومبت (من `References/what-fails.md`)

- ❌ `beautiful lighting` بدون مصدر مُحدَّد.
- ❌ `Syrian flag` بدون "green, white, and black with three red stars".
- ❌ `cinematic` لوحدها كصفة — كليشيه. استبدلها بكاميرا + ضوء + فيلم.
- ❌ `4K, ultra HD, award-winning, stunning, breathtaking` — حشو لا يستجيب له GPT Image 2.
- ❌ البرومبت بالعربية — يفشل.
- ❌ `--v 8 --style raw` — معاملات Midjourney، تُهمَل.
- ❌ بناء المشهد من البيئة بدون إنسان كشاهد (راجع `03-visual-system.md`).

---

## تسمية ملفات الصور (إجبارية)

- `hero.png` — الصورة الرئيسية (Hero قسم العنوان)
- `poster.png` — البوستر المستقل (نسبة 2:3) إن وُجد
- `scene-01.png`, `scene-02.png`, … — الصور الداخلية بالترتيب
- اللاحقة: `.png` افتراضياً
- اسم الملف **يتطابق حرفياً** مع رأس البرومبت في `image_prompts.md`
