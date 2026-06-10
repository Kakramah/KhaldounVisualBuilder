# qa-report.md

## الملفات
- [✅] analysis.md غير فارغ
- [✅] fact-check.md يحتوي "النسخة التحريرية النهائية المعتمدة"
- [✅] slides-plan.md يحتوي 10 شرائح
- [✅] image-prompts.md يحتوي 10 برومبتات
- [✅] image-generation.log يحتوي ذكر الـ Path المستخدم + نتيجة كل صورة
- [✅] qa-report.md موجود
- [✅] README.md موجود
- [✅] index.html موجود
- [✅] styles.css موجود
- [✅] images/ يحتوي 10 ملفات PNG بأسماء slide-01.png … slide-10.png
- [✅] لا ملفات SVG في images/ ولا أي ملفات خارج الهيكل

## الصور
- [✅] كل PNG حجمه ≥ 100KB
- [✅] كل PNG أبعاده ≥ 1280×720
- [✅] كل PNG يفتح بدون خطأ (PIL verify())
- [✅] كل PNG يحتوي watermark 𝓚𝓱𝓪𝓵𝓭𝓸𝓾𝓷A𝓐𝓴𝓻𝓪𝓶𝓪𝓱 مدمج في البكسلات
- [✅] 10 صور غير متطابقة (لا تكرار visual)
- [✅] صفر صور تحتوي دماً / جثة / علم النظام القديم / رموز بعث / generic AI look

## index.html
- [✅] lang="ar" و dir="rtl"
- [✅] <meta name="viewport"> + Google Fonts link
- [✅] 12 section (hero + 10 + footer)
- [✅] كل <img> مساره images/slide-NN.png (ليس .svg)
- [✅] كل <img> له alt عربي وصفي
- [✅] .signature في كل شريحة + footer
- [✅] صفر مسارات /Users/ أو file:/// أو localhost
- [✅] صفر برومبتات صور مرئية في DOM

## styles.css
- [✅] CSS variables من Design Tokens معرّفة حرفياً في :root
- [✅] صفر purple/violet/hot pink/magenta/cyan
- [✅] .slide لها aspect-ratio: 16/9
- [✅] .signature { opacity: 0.27; }
- [✅] صفر font-size تحت 11px
- [✅] media queries 768 / 480 / print

## المحتوى
- [✅] صفر حكم قطعي بلا مصدر
- [✅] صفر أسماء حقيقية في سياق اتهامي بلا مصدر
- [✅] صفر لغة طائفية / تعميم مناطقي
- [✅] الصياغة "بحسب / وثّقت / تُشير" مستخدمة عند ذكر ادعاءات

## التشغيل
- [✅] كل <img src> يطابق ملف PNG موجود فعلاً في images/
- [✅] الموقع يعمل offline (لا CDN غير Google Fonts)
- [✅] فتح index.html يعرض 10 صور حقيقية (ليست أيقونات broken)

✅ المشروع مكتمل — مجلد project/ جاهز كـ zip مع 10 صور حقيقية.
