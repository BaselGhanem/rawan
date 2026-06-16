# ZenHR Migration Portal - Firebase v3

نسخة HTML جاهزة للرفع على GitHub Pages، مع ربط Firebase فعلي.

## ماذا تغير؟

- تم حذف عبارة macOS UI من الواجهة.
- تم حذف اسم Rawan من الواجهة.
- تم وضع Firebase config الخاص بمشروع `rawan-f903d`.
- الموظف يدخل باستخدام تاريخ الميلاد + أول حرف من اسمه بالإنجليزية.
- لوحة الأدمن تفتح بالـ double click على علامة HR، لكن الدخول الحقيقي يتم عبر Firebase Authentication.
- لا تحتاج إنشاء Collections يدويًا؛ بعد دخول الأدمن، استخدم زر التهيئة ثم زر Import Seed.
- يتم إنشاء هذه Collections تلقائيًا عند أول استخدام:
  - `admins`
  - `employeeDirectory`
  - `loginIndex`
  - `submissions`
  - `editLogs`
  - `meta`

## خطوات Firebase قبل التشغيل

1. تأكد أن Authentication مفعّل:
   - Anonymous
   - Email/Password

2. تأكد أن مستخدم الأدمن موجود في Authentication، والـ UID هو:

```txt
PwyarKYD7iTs1sbE0rTLqHrkqdv1
```

3. انسخ قواعد `firestore.rules` المرفقة وانشرها في Firestore Rules.

هذه القواعد تسمح لحساب الأدمن أعلاه بإنشاء وثيقة الأدمن أول مرة بدون إدخال يدوي.

## أول تشغيل

1. افتح الموقع.
2. اعمل double click على علامة HR.
3. سجّل دخول الأدمن بالإيميل وكلمة السر التي أنشأتها في Firebase Authentication.
4. اضغط: **تهيئة الأدمن والـ collections**.
5. اضغط: **Import Seed to Firebase**.
6. اختر ملف البيانات الخاص: `private-tools/employee-seed-private.json`.
7. بعد نجاح الاستيراد، ارفع فقط الملفات الآمنة إلى GitHub.

## مهم جدًا قبل الرفع إلى GitHub

لا ترفع ملف البيانات الخاص إلى GitHub public.

الملف موجود داخل:

```txt
private-tools/employee-seed-private.json
```

وقد أضفت `.gitignore` حتى لا يتم رفعه إذا استخدمت Git بشكل صحيح.

ارفع إلى GitHub Pages:

```txt
index.html
firestore.rules
README.md
.gitignore
```

ولا ترفع:

```txt
private-tools/
employee-seed*.json
ملفات Excel الأصلية
```

## ملاحظة أمنية

الـ double click ليس حماية. هو فقط يخفي مكان شاشة الأدمن. الحماية الحقيقية من:

- Firebase Authentication
- Firestore Security Rules
- عدم نشر ملفات البيانات الحساسة على GitHub
