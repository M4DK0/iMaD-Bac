# 🎓 رفيق البكالوريا — مذاكرة بذكاء

موقع تعليمي جاهز للنشر مباشرة على **GitHub Pages** — رابط عام، مجاني، وتظهر معه صورة معاينة (Preview Image) عند مشاركة الرابط في واتساب/فيسبوك/تيليجرام/تويتر.

## 📦 محتوى الحزمة

| الملف | الوظيفة |
|---|---|
| `index.html` | الموقع كامل (نفس ملفك الأصلي + وسوم SEO/Open Graph مُضافة) |
| `og-image.jpg` | صورة المعاينة اللي بتظهر لما حد يفتح الرابط في تطبيق آخر |
| `.nojekyll` | ملف فارغ يمنع GitHub من معالجة الموقع كـ Jekyll (ضروري) |
| `README.md` | هذا الملف |

## 🚀 خطوات الرفع على GitHub Pages

### 1. أنشئ مستودع (Repository) جديد
- روح لـ https://github.com/new
- اختار اسم للمستودع (مثلاً: `baccalaureate-companion`)
- خليه **Public**
- ما تضيفش README من عند GitHub (عندك واحد جاهز)

### 2. ارفع الملفات
أسهل طريقة بدون Terminal:
- افتح المستودع اللي أنشأته
- اضغط **Add file → Upload files**
- اسحب كل الملفات الأربعة (`index.html`, `og-image.jpg`, `.nojekyll`, `README.md`) وارفعهم
- اضغط **Commit changes**

> إذا تفضل سطر الأوامر:
> ```bash
> git init
> git add .
> git commit -m "أول نشر للموقع"
> git branch -M main
> git remote add origin https://github.com/USERNAME/REPO-NAME.git
> git push -u origin main
> ```

### 3. فعّل GitHub Pages
- روح لـ **Settings → Pages** (في المستودع نفسه)
- تحت **Build and deployment → Source** اختار **Deploy from a branch**
- اختار البرانش `main` والمجلد `/ (root)`
- اضغط **Save**
- استنى دقيقة أو دقيقتين، رح يظهرلك رابط شبيه بـ:
  ```
  https://USERNAME.github.io/REPO-NAME/
  ```

### 4. ⚠️ خطوة مهمة جداً — فعّل صورة المعاينة
افتح ملف `index.html` عدّل فيه (من GitHub مباشرة بالضغط على القلم ✏️، أو محلياً):

ابحث عن الكلمة `PAGE_URL_HERE` (بتلاقيها 3 مرات في رأس الملف) واستبدلها **بالكامل** برابط موقعك الحقيقي من الخطوة السابقة، **مع خط `/` في الآخر**، مثال:

```
PAGE_URL_HERE  →  https://USERNAME.github.io/REPO-NAME/
```

بعد الاستبدال، السطر يصير هكذا تلقائياً وصحيح:
```html
<meta property="og:image" content="https://USERNAME.github.io/REPO-NAME/og-image.jpg">
```

اعمل Commit للتعديل، واستنى دقيقة عشان GitHub Pages يحدّث الموقع.

## ✅ تأكيد إن كل شي تمام
اختبر رابطك في أداة فحص Facebook (تشتغل مع أغلب التطبيقات):
👉 https://developers.facebook.com/tools/debug/

الصق رابط موقعك واضغط **Debug** — إذا ظهرت الصورة والعنوان والوصف، كل شي جاهز. إذا الموقع كان مخزّن (Cached) من قبل، اضغط **Scrape Again**.

## 🖌️ تغيير صورة المعاينة أو النصوص لاحقاً
- لتغيير الصورة: استبدل ملف `og-image.jpg` بأي صورة أخرى بنفس الاسم (يفضل بمقاس 1200×630).
- لتغيير العنوان/الوصف الظاهرين عند المشاركة: عدّل محتوى `og:title` و `og:description` و `twitter:title` و `twitter:description` في رأس `index.html`.
